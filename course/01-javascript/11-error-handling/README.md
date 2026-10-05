# 1.11 Error handling: try/catch и асинхронность 🟢

**Блок:** [01 — JavaScript Refresh & Internals](../)
**Уровень:** 🟢 REFRESH
**Prerequisites:** [1.1 Variables и scope](../01-variables-and-scope/)
**Следующий урок:** [1.12 References и referential equality](../12-references-and-referential-equality/) — первый урок части 2 (Internals)

## Цель

Не терять ошибки и понимать, где `try/catch` не сработает — до того, как это выяснится из отчёта о краше из продакшена.

## Материалы урока

- [theory.md](./theory.md) — refresh и RN relevance
- [practice.md](./practice.md) — проверка понимания и задание

## Что внутри

`throw` и объект `Error` · `try` / `catch` / `finally` · почему `try/catch` не ловит ошибку из колбэка, выполненного позже · ошибка в промисе и `unhandledRejection` · ошибка в `setTimeout` · своя иерархия ошибок вместо строк · что значит «ошибка проглочена».

## Связи

**Опирается на:** [1.1 Variables и scope](../01-variables-and-scope/).

**Готовит:** 1.18 Promises · 1.19 async/await · 1.20 Event loop (все — [часть 2](../)) · Error Boundaries (3.16) · ошибки, retry, backoff и таймауты (7.3) · Sentry / Crashlytics и symbolication (10.6) · postmortem (12.10).

**Концерн курса.** Это первое появление concern «Error Handling»: 1.11 → 3.16 → 7.3 → 10.6 → 12.10.

**RN Academy (P1).** Типы ошибок разбора входных данных и явное поведение при некорректных данных.

**Из банка вопросов.** —
