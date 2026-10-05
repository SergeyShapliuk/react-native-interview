# 1.4 Objects: копирование и идентичность 🟢

**Блок:** [01 — JavaScript Refresh & Internals](../)
**Уровень:** 🟢 REFRESH
**Prerequisites:** [1.2 Data types](../02-data-types-and-the-js-native-boundary/), [1.3 Coercion и сравнения](../03-coercion-and-comparison/)
**Следующий урок:** [1.5 Arrays: порядок, идентичность, мутирующие методы](../05-arrays-order-identity-mutation/)

## Цель

Отличать «новый объект» от «изменённый объект» и понимать, кто это замечает.

## Материалы урока

- [theory.md](./theory.md) — refresh и RN relevance
- [practice.md](./practice.md) — проверка понимания и задание

## Что внутри

Свойства и доступ · shallow copy через spread и `Object.assign` · вложенность и почему shallow copy её не защищает · `Object.keys` / `entries` / `values` · идентичность объекта как отдельное свойство, не связанное с содержимым · `Object.freeze` и его границы.

## Связи

**Опирается на:** 1.2 (примитивы и объекты), 1.3 (сравнение).

**Готовит:** 1.12 references · 1.13 immutability · 3.7 referential equality · 6.4 редьюсеры.

**RN Academy (P1).** Иммутабельное обновление прогресса: вложенная структура «курс → урок → прогресс».

**Из банка вопросов.** —
