# Checklist аудита блоков 01–03

Рабочий список к [AUDIT_REPORT_01_03.md](./AUDIT_REPORT_01_03.md). Каждый файл имеет один статус: **не начат** → **прочитан** → **проверен** (утверждения и код сверены) → **исправлен** (внесены правки) → **перепроверен** (правки прочитаны повторно, ссылки и связанные файлы сверены). Дополнительный статус **просмотрен выборочно** — файл не читался целиком: по нему выполнен целевой поиск рискованных утверждений (версии, движок, RN-рендерер, strict mode, сборка), найденные места прочитаны и сверены. Статус введён после просьбы ускорить аудит; такие файлы не считаются проверенными полностью.

## 01-javascript

| Файл | Статус | Замечания |
|---|---|---|
| `01-javascript/README.md` | исправлен | #5 (план 1.3); структура 25 уроков (12/11/2) сверена |
| `01-javascript/01-variables-and-scope/README.md` | проверен | навигация и ссылки |
| `01-javascript/01-variables-and-scope/theory.md` | исправлен | #1–3 |
| `01-javascript/01-variables-and-scope/practice.md` | исправлен | #1–3 |
| `01-javascript/02-data-types-and-the-js-native-boundary/README.md` | проверен | навигация и ссылки |
| `01-javascript/02-data-types-and-the-js-native-boundary/theory.md` | исправлен | #4 |
| `01-javascript/02-data-types-and-the-js-native-boundary/practice.md` | проверен | замечаний нет |
| `01-javascript/03-coercion-and-comparison/README.md` | проверен | навигация и ссылки |
| `01-javascript/03-coercion-and-comparison/theory.md` | исправлен | #5, #6 |
| `01-javascript/03-coercion-and-comparison/practice.md` | исправлен | #5, #6 |
| `01-javascript/04-objects-copying-and-identity/README.md` | проверен | навигация и ссылки |
| `01-javascript/04-objects-copying-and-identity/theory.md` | исправлен | #9, #10 |
| `01-javascript/04-objects-copying-and-identity/practice.md` | исправлен | #9, #10 |
| `01-javascript/05-arrays-order-identity-mutation/README.md` | проверен | навигация и ссылки |
| `01-javascript/05-arrays-order-identity-mutation/theory.md` | исправлен | #11, #33 |
| `01-javascript/05-arrays-order-identity-mutation/practice.md` | проверен | замечаний нет |
| `01-javascript/06-array-methods/README.md` | проверен | навигация и ссылки |
| `01-javascript/06-array-methods/theory.md` | исправлен | #12–14 |
| `01-javascript/06-array-methods/practice.md` | исправлен | #12–14 |
| `01-javascript/07-destructuring/README.md` | проверен | навигация и ссылки |
| `01-javascript/07-destructuring/theory.md` | проверен | замечаний нет |
| `01-javascript/07-destructuring/practice.md` | проверен | замечаний нет |
| `01-javascript/08-spread-and-rest/README.md` | проверен | навигация и ссылки |
| `01-javascript/08-spread-and-rest/theory.md` | исправлен | #15, #16 |
| `01-javascript/08-spread-and-rest/practice.md` | исправлен | #15, #16 |
| `01-javascript/09-modern-js-syntax/README.md` | проверен | навигация и ссылки |
| `01-javascript/09-modern-js-syntax/theory.md` | исправлен | #5, #17 |
| `01-javascript/09-modern-js-syntax/practice.md` | исправлен | #5, #17 |
| `01-javascript/10-modules-esm-cjs-metro/README.md` | проверен | навигация и ссылки |
| `01-javascript/10-modules-esm-cjs-metro/theory.md` | исправлен | #18–20 |
| `01-javascript/10-modules-esm-cjs-metro/practice.md` | исправлен | #18–20 |
| `01-javascript/11-error-handling/README.md` | проверен | навигация и ссылки |
| `01-javascript/11-error-handling/theory.md` | исправлен | #21 |
| `01-javascript/11-error-handling/practice.md` | проверен | замечаний нет |
| `01-javascript/12-references-and-referential-equality/README.md` | проверен | навигация и ссылки |
| `01-javascript/12-references-and-referential-equality/theory.md` | проверен | замечаний нет |
| `01-javascript/12-references-and-referential-equality/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `01-javascript/13-mutation-and-immutability/README.md` | проверен | навигация и ссылки |
| `01-javascript/13-mutation-and-immutability/theory.md` | исправлен | #22 |
| `01-javascript/13-mutation-and-immutability/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `01-javascript/14-closures/README.md` | проверен | навигация и ссылки |
| `01-javascript/14-closures/theory.md` | исправлен | #23 |
| `01-javascript/14-closures/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `01-javascript/15-execution-context-and-scope-chain/README.md` | проверен | навигация и ссылки |
| `01-javascript/15-execution-context-and-scope-chain/theory.md` | исправлен | #24 |
| `01-javascript/15-execution-context-and-scope-chain/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `01-javascript/16-this/README.md` | проверен | навигация и ссылки |
| `01-javascript/16-this/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `01-javascript/16-this/practice.md` | исправлен | #29 |
| `01-javascript/17-prototypes-vs-classes/README.md` | проверен | навигация и ссылки |
| `01-javascript/17-prototypes-vs-classes/theory.md` | исправлен | #25, #29 |
| `01-javascript/17-prototypes-vs-classes/practice.md` | исправлен | #25, #29 |
| `01-javascript/18-promises/README.md` | проверен | навигация и ссылки |
| `01-javascript/18-promises/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `01-javascript/18-promises/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `01-javascript/19-async-await/README.md` | проверен | навигация и ссылки |
| `01-javascript/19-async-await/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `01-javascript/19-async-await/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `01-javascript/20-event-loop/README.md` | проверен | навигация и ссылки |
| `01-javascript/20-event-loop/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `01-javascript/20-event-loop/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `01-javascript/21-microtasks-and-macrotasks/README.md` | проверен | навигация и ссылки |
| `01-javascript/21-microtasks-and-macrotasks/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `01-javascript/21-microtasks-and-macrotasks/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `01-javascript/22-memory-and-reachability/README.md` | проверен | навигация и ссылки |
| `01-javascript/22-memory-and-reachability/theory.md` | исправлен | #26 |
| `01-javascript/22-memory-and-reachability/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `01-javascript/23-garbage-collection/README.md` | проверен | навигация и ссылки |
| `01-javascript/23-garbage-collection/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `01-javascript/23-garbage-collection/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `01-javascript/24-synthesis/README.md` | проверен | навигация и ссылки |
| `01-javascript/24-synthesis/theory.md` | исправлен | #27, #28 |
| `01-javascript/24-synthesis/practice.md` | исправлен | #27, #28 |
| `01-javascript/25-numbers-dates-and-strings/README.md` | проверен | навигация и ссылки |
| `01-javascript/25-numbers-dates-and-strings/theory.md` | исправлен | #7, #8 |
| `01-javascript/25-numbers-dates-and-strings/practice.md` | проверен | замечаний нет |

## 02-typescript

| Файл | Статус | Замечания |
|---|---|---|
| `02-typescript/README.md` | просмотрен выборочно | структура 16 уроков (3/9/4) сверена |
| `02-typescript/01-basic-types-and-inference/README.md` | проверен | навигация и ссылки |
| `02-typescript/01-basic-types-and-inference/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/01-basic-types-and-inference/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/02-generics/README.md` | проверен | навигация и ссылки |
| `02-typescript/02-generics/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/02-generics/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/03-utility-types/README.md` | проверен | навигация и ссылки |
| `02-typescript/03-utility-types/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/03-utility-types/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/04-unknown-type-guards-assertions/README.md` | проверен | навигация и ссылки |
| `02-typescript/04-unknown-type-guards-assertions/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/04-unknown-type-guards-assertions/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/05-discriminated-unions-and-narrowing/README.md` | проверен | навигация и ссылки |
| `02-typescript/05-discriminated-unions-and-narrowing/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/05-discriminated-unions-and-narrowing/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/06-interface-vs-type/README.md` | проверен | навигация и ссылки |
| `02-typescript/06-interface-vs-type/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/06-interface-vs-type/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/07-satisfies-and-template-literal-types/README.md` | проверен | навигация и ссылки |
| `02-typescript/07-satisfies-and-template-literal-types/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/07-satisfies-and-template-literal-types/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/08-strict-flags/README.md` | проверен | навигация и ссылки |
| `02-typescript/08-strict-flags/theory.md` | исправлен | #30 |
| `02-typescript/08-strict-flags/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/09-declaration-files-and-module-augmentation/README.md` | проверен | навигация и ссылки |
| `02-typescript/09-declaration-files-and-module-augmentation/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/09-declaration-files-and-module-augmentation/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/10-conditional-types-and-infer/README.md` | проверен | навигация и ссылки |
| `02-typescript/10-conditional-types-and-infer/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/10-conditional-types-and-infer/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/11-typing-polymorphic-api-layer/README.md` | проверен | навигация и ссылки |
| `02-typescript/11-typing-polymorphic-api-layer/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/11-typing-polymorphic-api-layer/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/12-runtime-validation-at-the-boundary/README.md` | проверен | навигация и ссылки |
| `02-typescript/12-runtime-validation-at-the-boundary/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/12-runtime-validation-at-the-boundary/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/13-type-safety-at-system-boundaries/README.md` | проверен | навигация и ссылки |
| `02-typescript/13-type-safety-at-system-boundaries/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/13-type-safety-at-system-boundaries/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/14-typing-react-native-components-and-hooks/README.md` | проверен | навигация и ссылки |
| `02-typescript/14-typing-react-native-components-and-hooks/theory.md` | исправлен | #32 |
| `02-typescript/14-typing-react-native-components-and-hooks/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/15-typescript-in-the-rn-build/README.md` | проверен | навигация и ссылки |
| `02-typescript/15-typescript-in-the-rn-build/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/15-typescript-in-the-rn-build/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/16-branded-types/README.md` | проверен | навигация и ссылки |
| `02-typescript/16-branded-types/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `02-typescript/16-branded-types/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |

## 03-react

| Файл | Статус | Замечания |
|---|---|---|
| `03-react/README.md` | просмотрен выборочно | структура 19 уроков сверена, заявленный стенд проверки |
| `03-react/01-reconciliation-and-fiber/README.md` | проверен | навигация и ссылки |
| `03-react/01-reconciliation-and-fiber/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/01-reconciliation-and-fiber/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/02-keys/README.md` | проверен | навигация и ссылки |
| `03-react/02-keys/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/02-keys/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/03-update-path/README.md` | проверен | навигация и ссылки |
| `03-react/03-update-path/theory.md` | исправлен | #31 |
| `03-react/03-update-path/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/04-lifecycle-and-strict-mode/README.md` | проверен | навигация и ссылки |
| `03-react/04-lifecycle-and-strict-mode/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/04-lifecycle-and-strict-mode/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/05-rules-of-hooks-and-dependencies/README.md` | проверен | навигация и ссылки |
| `03-react/05-rules-of-hooks-and-dependencies/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/05-rules-of-hooks-and-dependencies/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/06-useeffect-vs-uselayouteffect/README.md` | проверен | навигация и ссылки |
| `03-react/06-useeffect-vs-uselayouteffect/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/06-useeffect-vs-uselayouteffect/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/07-when-an-effect-is-not-needed/README.md` | проверен | навигация и ссылки |
| `03-react/07-when-an-effect-is-not-needed/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/07-when-an-effect-is-not-needed/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/08-usestate-vs-usereducer/README.md` | проверен | навигация и ссылки |
| `03-react/08-usestate-vs-usereducer/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/08-usestate-vs-usereducer/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/09-refs/README.md` | проверен | навигация и ссылки |
| `03-react/09-refs/theory.md` | исправлен | #32 |
| `03-react/09-refs/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/10-referential-equality/README.md` | проверен | навигация и ссылки |
| `03-react/10-referential-equality/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/10-referential-equality/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/11-memo-usememo-usecallback/README.md` | проверен | навигация и ссылки |
| `03-react/11-memo-usememo-usecallback/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/11-memo-usememo-usecallback/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/12-custom-hooks/README.md` | проверен | навигация и ссылки |
| `03-react/12-custom-hooks/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/12-custom-hooks/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/13-composition/README.md` | проверен | навигация и ссылки |
| `03-react/13-composition/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/13-composition/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/14-context-and-its-cost/README.md` | проверен | навигация и ссылки |
| `03-react/14-context-and-its-cost/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/14-context-and-its-cost/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/15-controlled-vs-uncontrolled/README.md` | проверен | навигация и ссылки |
| `03-react/15-controlled-vs-uncontrolled/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/15-controlled-vs-uncontrolled/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/16-error-boundaries/README.md` | проверен | навигация и ссылки |
| `03-react/16-error-boundaries/theory.md` | исправлен | #24 |
| `03-react/16-error-boundaries/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/17-suspense-and-concurrent-features/README.md` | проверен | навигация и ссылки |
| `03-react/17-suspense-and-concurrent-features/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/17-suspense-and-concurrent-features/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/18-react-compiler/README.md` | проверен | навигация и ссылки |
| `03-react/18-react-compiler/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/18-react-compiler/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/19-usesyncexternalstore-and-tearing/README.md` | проверен | навигация и ссылки |
| `03-react/19-usesyncexternalstore-and-tearing/theory.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |
| `03-react/19-usesyncexternalstore-and-tearing/practice.md` | просмотрен выборочно | целевой поиск по рискованным утверждениям |

