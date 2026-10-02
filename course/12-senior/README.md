# 12 — Senior Engineering & System Design

**Prerequisites:** все предыдущие блоки
**Статус:** уроки не написаны

## Цель блока

Работать на уровне решений и их последствий, а не на уровне реализации.

Блок **не является «всем, что осталось»**. Внутри него четыре самостоятельных направления, и capstone — их логическое завершение, а не ещё одна тема:

```
12 Senior Engineering
    ├── 12.A Technical decisions      — trade-offs, ADR, технический долг, выбор между альтернативами
    ├── 12.B Production incidents     — investigation, postmortem, blast radius, алертинг
    ├── 12.C System Design            — проектирование и защита решения, threat modeling, scalability
    └── 12.D Technical Leadership     — code review как инструмент, обоснование решений
            ↓
         Capstone
```

## 12.A — Technical decisions

| # | Тема | Уровень | Ключевой вопрос урока |
|---|---|---|---|
| 12.1 | Стратегии рефакторинга без остановки разработки | 🟡 | как менять то, что одновременно развивают |
| 12.2 | Технический долг: когда платить, когда занимать | 🔴 | как считать проценты по долгу |
| 12.3 | Выбор между альтернативами при неполных данных | 🔴 | какое решение останется верным при любом исходе неизвестного |
| 12.4 | Миграция на New Architecture | 🔴 senior case | аудит зависимостей, этапы, риски, критерий отката |

## 12.B — Production incidents

| # | Тема | Уровень | Ключевой вопрос урока |
|---|---|---|---|
| 12.5 | Investigation: от алерта к root cause | 🔴 | как не починить симптом вместо причины |
| 12.6 | Performance investigation в инциденте | 🔴 | та же методика из блока 05, но под давлением времени |
| 12.7 | Blast radius и приоритизация | 🔴 | кого затронуло и что делать первым |
| 12.8 | Postmortem | 🔴 | как написать так, чтобы по нему приняли решение |

## 12.C — System Design

| # | Тема | Уровень | Ключевой вопрос урока |
|---|---|---|---|
| 12.9 | Scalability: приложение из 40+ feature-модулей | 🟡 | что ломается от размера, а не от сложности |
| 12.10 | Threat modeling | 🔴 | от чего мы защищаемся и от чего сознательно нет |
| 12.11 | Security architecture и security trade-offs | 🔴 | цена защиты и как её обосновать |
| 12.12 | System design сессии | 🔴 | offline-first мессенджер · лента с медиа · оффлайн-первый commerce |

## 12.D — Technical Leadership

| # | Тема | Уровень | Ключевой вопрос урока |
|---|---|---|---|
| 12.13 | Code review как инструмент развития команды | 🟡 | ревью, которое учит, а не контролирует |
| 12.14 | Обоснование решения перед командой и бизнесом | 🔴 | как говорить о trade-offs с теми, кто не пишет код |
| 12.15 | Документирование решений | 🔴 | как сделать, чтобы решение жило без автора |

## Capstone

Сквозная задача: спроектировать систему, защитить решение через trade-offs, описать риски, план поэтапного внедрения и критерий отката. Capstone собирает все четыре направления: решение (12.A), его наблюдаемость и поведение при сбое (12.B), архитектура и угрозы (12.C), защита перед командой (12.D).

## Что должно быть получено

- Провожу system design сессию и защищаю решение через trade-offs, а не через предпочтения.
- Разбираю инцидент от алерта до root cause и пишу postmortem, по которому принимают решение.
- Провожу threat modeling и обосновываю, от чего мы сознательно не защищаемся.
- Обосновываю техническое решение перед нетехническим собеседником.

## Упражнения

- **System design exercises:** три сессии из 12.12, каждая с защитой решения.
- **Code review exercises:** PR с race condition (продолжение из блока 07); PR, где корректный код принимает неверное архитектурное решение.
- **Senior case studies:** production incident от первого алерта до postmortem · threat modeling: что решили не защищать · миграция на New Architecture · самый сложный performance-баг.

## Cross-cutting concerns в этом блоке

| Concern | Как затрагивается |
|---|---|
| Security | Senior-уровень: threat modeling, security architecture, trade-offs |
| Observability | Senior-уровень: алертинг, SLO, postmortem |
| Debugging | Senior-уровень: investigation от симптома к root cause |
| Performance | Senior-уровень: performance investigation в инциденте |
| Documentation | Senior-уровень: RFC, design doc, защита решения |
| Code Review | Senior-уровень: ревью как инструмент лидерства |
| Testing | стратегия тестирования и код-ревью как процесс в команде |
| Accessibility | audit и приоритизация |
| Error Handling | blast radius, postmortem |

## Спиральные возвраты, которые закрываются здесь

- event loop (01) → JS thread (04) → бюджет кадра (05) → профилирование (05) → **investigation в инциденте (12.5, 12.6)**
- Promise (01) → API (07) → кэш (07) → offline-first (07) → **распределённая синхронизация (12.12)**
- error handling (01) → Error Boundaries (03) → сетевые ошибки (07) → crash reporting (10) → **postmortem (12.8)**
- bridge (04) → JSI и TurboModules (04) → «нужен ли native layer» (08) → модуль (09) → **миграция на New Architecture (12.4)**
- security: auth (07) → permissions (09) → production security (10) → **threat modeling и security architecture (12.10, 12.11)**

## Материал из банка вопросов

| Источник | Тема | Формат |
|---|---|---|
| V1 | диагностика падений в продакшене (совместно с 10) | deep dive + senior case |
| V2 | ограничения React Native | reference + system design |
| V3 §10 | алертинг и метрики (совместно с 10) | deep dive |
| V3 live | ревью PR с race condition (совместно с 07) | code review |
| V3 behav | миграция на New Architecture | senior case |
| V3 behav | самый сложный performance-баг (совместно с 05) | senior case |
| V3 behav | процесс код-ревью и тестирования в команде (совместно с 11) | reference |
