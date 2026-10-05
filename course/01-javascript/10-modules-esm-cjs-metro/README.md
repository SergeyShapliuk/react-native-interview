# 1.10 Modules: ESM, CJS и как это видит Metro 🟢

**Блок:** [01 — JavaScript Refresh & Internals](../)
**Уровень:** 🟢 REFRESH
**Prerequisites:** [1.1 Variables и scope](../01-variables-and-scope/)
**Следующий урок:** [1.11 Error handling: try/catch и асинхронность](../11-error-handling/)

## Цель

Понимать, как файлы превращаются в граф модулей и что из этого попадает в бандл — чтобы уметь объяснить `undefined` вместо импорта, рост бандла после «безобидного» рефакторинга и расхождение поведения между iOS и Android.

## Материалы урока

- [theory.md](./theory.md) — refresh и RN relevance
- [practice.md](./practice.md) — проверка понимания и задание

## Что внутри

`import` / `export`, named и default · CommonJS и `require` · статический анализ импортов против динамического `require` · циклические зависимости и их проявления · barrel-файлы (`index.ts`, реэкспорт) · модуль как singleton: код верхнего уровня выполняется один раз · модуль в терминах Metro: цепочка `resolver → module resolution → transformation → dependency graph → bundling`.

## Связи

**Опирается на:** [1.1 Variables и scope](../01-variables-and-scope/) — модульный scope и время жизни значений верхнего уровня.

**Готовит:** 4.4 Metro: resolver, граф модулей, бандл · 5.6 Bundle size и TTI · 8.2 Границы модулей и правила зависимостей · 8.6 Path aliases и их синхронизация.

**RN Academy (P1).** Структура модулей домена; правило «никаких side effect на верхнем уровне»; сознательный отказ от barrel-файлов на границах фич.

**Из банка вопросов.** V3 §3 «Metro bundler vs Webpack» — вводная часть; основной разбор в 4.4.
