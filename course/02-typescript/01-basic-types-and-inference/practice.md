# 2.1 Базовые типы и вывод типов — practice

## Проверка понимания

Цель — не оценка, а обнаружение пробела. У каждого вопроса указано, что вскрывает неверный ответ.

---

**1. Почему эти два объявления получают разные типы и что из этого следует при вызове `scroll`?**

```ts
type Direction = 'up' | 'down';
function scroll(d: Direction) {}

const a = 'up';
let b = 'up';
```

<details>
<summary>Ответ</summary>

`a` имеет тип `"up"` — литеральный. `b` имеет тип `string`: переменную, объявленную через `let`, можно переприсвоить, поэтому компилятор расширяет тип литерала до базового (widening). `scroll(a)` компилируется, `scroll(b)` — нет: `string` не присваивается `Direction`.

**Ответ «типы одинаковые, оба `string`»** вскрывает отсутствие модели литеральных типов. Практическое следствие: любой union из строк — состояние компонента, имя маршрута, платформенный ключ — перестанет работать, как только значение пройдёт через `let` или через поле объектного литерала, и причина ошибки будет выглядеть случайной.

**Ответ «надо добавить `: Direction` переменной `b`»** конкретный вызов чинит, но вскрывает рецепт вместо механизма: если то же значение приходит не из `let`, а из поля объекта (`config.direction`), «дописать аннотацию переменной» не применимо — нужен `as const` или аннотация самого объекта.

**Ответ «потому что `const` неизменяемый»** вскрывает смешение с 1.1: `const` фиксирует связь имени со значением, и именно из этого факта следует отсутствие widening. Для объекта под `const` widening полей по-прежнему происходит — `const config = { direction: 'up' }` даёт `{ direction: string }`.
</details>

---

**2. Что произойдёт с типом ключей после аннотации и как это проявится при опечатке?**

```ts
const screenTitles = {
  lesson: 'Урок',
  courseList: 'Курсы',
};

const annotated: Record<string, string> = {
  lesson: 'Урок',
  courseList: 'Курсы',
};

screenTitles.lessson;  // ?
annotated.lessson;     // ?
```

<details>
<summary>Ответ</summary>

У `screenTitles` выведен тип `{ lesson: string; courseList: string }` — ключи известны, и `screenTitles.lessson` не компилируется.

`Record<string, string>` означает «любой строковый ключ сопоставлен строке». Аннотация проверила форму объекта и стёрла знание о конкретных ключах: `annotated.lessson` имеет тип `string` и компилируется, а в рантайме вернёт `undefined`.

**Ответ «разницы нет, оба объекта одинаковые»** вскрывает чтение аннотации как документации: предполагается, что она описывает то, что уже выведено. На деле аннотация заменяет выведенный тип, и `Record<string, …>` — самый частый способ потерять ключи.

**Ответ «`Record` нужен, чтобы объект проверялся»** вскрывает отсутствие различия между проверкой объекта и точностью его типа. Проверка нужна, точность нужна тоже, и выбирать между ними не требуется — но инструмент для этого (`satisfies`) появляется в 2.7, а до него задача решается выводом без аннотации.
</details>

---

**3. В каком случае явная аннотация возвращаемого типа меняет результат проверки, а не просто документирует его?**

<details>
<summary>Ответ</summary>

Когда тело функции расходится с намерением. Без аннотации возвращаемый тип выводится из тела, поэтому несоответствия быть не может по определению: что функция вернула, то и объявлено. С аннотацией сигнатура становится утверждением, и несовпадающая ветвь `return` — ошибка в той строке, где она написана.

Типичные случаи: забытый `return` в одной ветви (выводится `T | undefined` вместо `T`), возврат `undefined` там, где контракт обещает `null`, возврат расширенного типа (`string`) там, где обещан union, и асинхронная функция, в которой потеряли `await` (выводится `Promise<Promise<T>>`-подобная форма вместо `Promise<T>`).

**Ответ «аннотация ничего не меняет, вывод всегда верный»** вскрывает подмену понятий: выведенный тип верно описывает код, но ничего не говорит о том, правилен ли код. Практическая цена — ошибка всплывает у вызывающего, иногда через несколько слоёв, и строка-источник в сообщении не фигурирует.

**Ответ «аннотация нужна везде»** вскрывает отсутствие границы между внешним контрактом и внутренней реализацией. На локальных функциях-хелперах аннотация даёт шум и ещё одно место для правки при изменении, на экспортируемых — фиксирует контракт модуля.
</details>

---

**4. Функция ниже компилируется. Где здесь дыра и почему в коде нет слова `any`?**

```ts
async function loadLesson(id: string): Promise<Lesson> {
  const response = await fetch(`/lessons/${id}`);
  const data = await response.json();
  return data;
}
```

<details>
<summary>Ответ</summary>

`response.json()` объявлен как `Promise<any>`. `data` получает тип `any`, а `any` присваивается чему угодно, в том числе `Lesson`. Компилятор не возражает, и дальше по приложению значение ходит как полноценный `Lesson`, хотя никто не проверял ни одного поля. Слова `any` в коде проекта нет — он пришёл из типов стандартной библиотеки.

**Ответ «всё в порядке, возвращаемый тип аннотирован»** вскрывает чтение аннотации как проверки. Аннотация проверяет тело функции по правилам типов, а `any` эти правила снимает — аннотация осталась, гарантии нет.

**Ответ «надо написать `return data as Lesson`»** вскрывает смешение утверждения и проверки: `as` сообщает компилятору вывод, который тот обязан принять, и ничего не выполняет в рантайме. Это то же самое место, только написанное явно; явность полезна, но дыру не закрывает.

**Ответ «значит, типам нельзя верить вообще»** — противоположная крайность. Внутри кодовой базы типы проверяются; дыра возникает ровно на границе, где значение приходит извне. Как выглядит корректная замена `any` на границе — 2.4, как сделать проверку настоящей — 2.12.
</details>

---

## Задание

**Дано.** Модуль домена из P1 — чистый JavaScript, без React. Он отбирает уроки и считает прогресс курса.

```js
// domain/progress.js
export const LESSON_STATES = {
  locked: 'locked',
  available: 'available',
  done: 'done',
};

export function createProgress(courseId) {
  return { courseId, completed: [], updatedAt: null };
}

export function markDone(progress, lessonId) {
  if (progress.completed.includes(lessonId)) return progress;
  return {
    ...progress,
    completed: [...progress.completed, lessonId],
    updatedAt: Date.now(),
  };
}

export function lessonState(lesson, progress) {
  if (progress.completed.includes(lesson.id)) return LESSON_STATES.done;
  if (lesson.requires && !progress.completed.includes(lesson.requires)) {
    return LESSON_STATES.locked;
  }
  return LESSON_STATES.available;
}

export function summarize(lessons, progress) {
  const total = lessons.length;
  const done = lessons.filter((l) => progress.completed.includes(l.id)).length;
  return { total, done, ratio: total === 0 ? 0 : done / total };
}
```

**Требуется.**

1. Перенести модуль на TypeScript, аннотируя только публичную границу: типы данных (`Lesson`, `Progress`) и сигнатуры экспортируемых функций. Внутри тел функций аннотаций не ставить.
2. Добиться, чтобы `lessonState` возвращала union из трёх литералов, а не `string`. Назвать строку, из-за которой без вмешательства получается `string`, и указать, что именно её чинит.
3. Пройти по получившемуся файлу и выписать аннотации, которые ничего не добавляют к выводу или его ухудшают. Для каждой — сказать, какой тип компилятор выводит без неё.
4. Ответить: что в этом модуле типы гарантируют, а что — нет, если `progress` пришёл из `AsyncStorage` после обновления приложения. Решение не писать — оно в 2.12.

---

<details>
<summary>Разбор</summary>

**1. Граница модуля.**

```ts
export const LESSON_STATES = {
  locked: 'locked',
  available: 'available',
  done: 'done',
} as const;

export type LessonState = (typeof LESSON_STATES)[keyof typeof LESSON_STATES];
// "locked" | "available" | "done"

export type Lesson = {
  id: string;
  title: string;
  requires?: string;
};

export type Progress = {
  courseId: string;
  completed: string[];
  updatedAt: number | null;
};

export function createProgress(courseId: string): Progress {
  return { courseId, completed: [], updatedAt: null };
}

export function markDone(progress: Progress, lessonId: string): Progress {
  if (progress.completed.includes(lessonId)) return progress;
  return {
    ...progress,
    completed: [...progress.completed, lessonId],
    updatedAt: Date.now(),
  };
}

export function lessonState(lesson: Lesson, progress: Progress): LessonState {
  if (progress.completed.includes(lesson.id)) return LESSON_STATES.done;
  if (lesson.requires && !progress.completed.includes(lesson.requires)) {
    return LESSON_STATES.locked;
  }
  return LESSON_STATES.available;
}

export function summarize(lessons: Lesson[], progress: Progress) {
  const total = lessons.length;
  const done = lessons.filter((l) => progress.completed.includes(l.id)).length;
  return { total, done, ratio: total === 0 ? 0 : done / total };
}
```

Параметры аннотированы везде — выводить их не из чего. Возвращаемые типы аннотированы там, где они являются контрактом: `Progress` у двух функций и `LessonState` у `lessonState`. У `summarize` возвращаемый тип оставлен на выводе намеренно — это внутренняя агрегация, форма которой целиком определяется телом, и дублировать `{ total: number; done: number; ratio: number }` незачем. Если `summarize` станет частью публичного API экрана, аннотация появится — это решение, а не правило.

**2. Строка, из-за которой получается `string`.** Объявление `LESSON_STATES`. Без `as const` поля объектного литерала изменяемы, их типы расширяются до `string`, и каждое `return LESSON_STATES.done` возвращает `string`. `as const` запрещает widening, поля становятся `readonly` с литеральными типами, и `LessonState` выводится из самого объекта — описывать union вторым списком не нужно.

Альтернатива — написать `export type LessonState = 'locked' | 'available' | 'done'` отдельно и аннотировать объект этим типом. Это работает, но создаёт два описания одного множества, которые разъезжаются при добавлении четвёртого состояния.

Отдельно стоит проверить, что аннотация возвращаемого типа `: LessonState` действительно что-то делает. Делает: уберите `as const`, оставив аннотацию, — ошибка появится внутри `lessonState`, в строке `return`, а не у вызывающего.

**3. Аннотации, которые не нужны.** В предложенном варианте их не осталось, но в типичном переносе появляются такие:

- `const total: number = lessons.length` и `const done: number = ...` — `number` выводится;
- `const next: string[] = [...progress.completed, lessonId]` — выводится `string[]`;
- `(l: Lesson) => ...` в колбэке `filter` — тип параметра приходит контекстно из `Lesson[]`, ручная аннотация дублирует его и расходится с ним при смене типа массива;
- `const states: Record<string, string> = LESSON_STATES` — ухудшение: стирает и ключи, и литеральные значения, после чего `LESSON_STATES.don` компилируется.

Признак для проверки: удалить аннотацию и посмотреть выведенный тип. Если он совпал — аннотация была шумом, если стал точнее — вредила, если код перестал компилироваться — аннотация несла информацию и остаётся.

**4. Что типы гарантируют.** Внутри модуля — всё: `markDone` не примет число вместо `Progress`, `lessonState` не вернёт строку вне union, опечатка в `progress.complited` не скомпилируется.

Что не гарантируют: сам факт, что значение, пришедшее из `AsyncStorage`, является `Progress`. `JSON.parse` возвращает `any`, и присваивание `const progress: Progress = JSON.parse(raw)` проверки не выполняет. После обновления приложения, в котором `completed` стал массивом объектов вместо массива строк, старое сохранённое значение пройдёт в домен беспрепятственно, и `includes` будет молча возвращать `false` — прогресс пользователя выглядит сброшенным, ошибки нет ни одной.

Формулировка, которую стоит зафиксировать для всего блока: тип — утверждение, проверяемое компилятором внутри кодовой базы. На границе (хранилище, сеть, параметры экрана, нативный модуль) проверки нет, и там тип становится предположением. Что с этим делать — 2.12 и 2.13.

**Вклад в проект.** Модули домена P1 после этого задания существуют в TypeScript без изменения логики, и правило P2 зафиксировано: аннотируется публичная граница модуля, внутри полагаемся на вывод. Состояние урока сейчас — union из трёх строк; в 2.5 оно станет discriminated union, в котором невыразима комбинация «пройден, но заблокирован».
</details>
