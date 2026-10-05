# 1.1 Variables и scope 🟢

**Блок:** [01 — JavaScript Refresh & Internals](../)
**Уровень:** 🟢 REFRESH
**Prerequisites:** нет
**Следующий урок:** [1.2 Data types и граница JS↔native](../02-data-types-and-the-js-native-boundary/)

## Цель

Уверенно предсказывать, какое значение видит переменная в любой точке кода — включая асинхронные колбэки, где интуиция подводит чаще всего.

## Материалы урока

- [theory.md](./theory.md) — refresh и RN relevance
- [practice.md](./practice.md) — проверка понимания и задание

## Что внутри

`var` / `let` / `const` и их области видимости · hoisting и temporal dead zone · блочная область видимости · `const` не означает иммутабельность · shadowing · почему `const` по умолчанию, а `let` по необходимости.

## Связи

**Опирается на:** —

**Готовит:** [1.14 Closures](../) · [1.15 Execution context и scope chain](../) · правила зависимостей хуков (3.4).

**RN Academy (P1).** Задать соглашение по объявлению переменных в модулях домена: `const` по умолчанию.

**Из банка вопросов.** —
