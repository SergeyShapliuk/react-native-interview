# 2.3 Утилитарные типы: `Partial` / `Pick` / `Omit` / `Record` 🟢

**Блок:** [02 — TypeScript for Experienced Developers](../)
**Уровень:** 🟢 REFRESH
**Prerequisites:** [2.2 Generics](../02-generics/)
**Следующий урок:** [2.4 `unknown` vs `any`, type guards, assertion functions](../04-unknown-type-guards-assertions/)

## Цель

Описать модель один раз и выводить из неё остальные формы, не поддерживая несколько копий одного описания.

## Материалы урока

- [theory.md](./theory.md) — refresh и RN relevance
- [practice.md](./practice.md) — проверка понимания и задание

## Что внутри

`Partial` и почему он плохой тип состояния · `Pick` и `Omit`, и почему `Omit` хрупок при переименовании поля · `Record` против index signature · `Required`, `Readonly`, `NonNullable`, `ReturnType`, `Parameters` · комбинирование утилит и момент, когда выражение пора назвать типом · чем ручное дублирование полей расходится с моделью.

## Связи

**Опирается на:** [2.2 Generics](../02-generics/) · 2.1 базовые типы и вывод.

**Готовит:** 2.5 (discriminated union вместо `Partial` как типа состояния) · 2.6 `interface` vs `type` · 2.10 mapped и conditional types изнутри · 2.11 DTO против доменной модели · 2.14 типизация пропсов · 8.5 изоляция от формы ответа backend.

**RN Academy (P2).** Типы домена — курс, урок, прогресс — объявляются как единственный источник. Формы создания, обновления и элемента списка выводятся из них утилитами; добавление поля в модель требует правки в одном месте.

**Из банка вопросов.** V3 §1 «`Partial` / `Pick` / `Omit` / `Record`» (`lesson`).
