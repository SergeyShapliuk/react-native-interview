# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

A documentation-only repository holding **two separate bodies of material** in Russian. There is no application code, no package manifest, no build/lint/test tooling. Work here is editing Markdown.

1. **Interview question bank** at the repo root — `V1.md`, `V2.md`, `V3.md`.
2. **A course** under `course/` — "React Native Developer — From Experienced Developer to Senior", for a developer who already ships RN apps.

The two are deliberately not merged — see the "Course" section below for the rules that govern `course/`.

## Structure: the question bank

Three independent, parallel documents — **not** a versioned progression where only the newest matters. Each has a different shape and all three are kept:

- **V1.md** — "FINAL" long-form reference, 6 thematic sections (architecture, performance, state, native/build, testing & CI/CD, security & troubleshooting). Deepest answers, with fenced code blocks (YAML CI configs, shell, JS). Has a linked table of contents and a `## Заключение` with recommendations.
- **V2.md** — broader but shallower, 10 sections covering fundamentals (Bridge, New Architecture, CLI vs Expo, styling, platform-specific code, FlatList vs ScrollView, native modules, pros/cons). Uses Markdown tables for comparisons. Also has a linked TOC and `## Заключение`.
- **V3.md** — the widest in scope, 10 topic sections plus `## Практические задания (live coding)` and `## Вопросы про опыт`. No TOC. Marks where a Senior answer should go deeper than a Middle one.

## Conventions to preserve when editing

- **Language is Russian.** All prose, headings, and TOC entries. English is used only for technical terms kept in Latin script (`useEffect`, FlatList, Fabric, TurboModules, JSI, Hermes).
- **Q&A format differs per file.** V1 and V2 use `### В: <question>` followed by `**О:**` and the answer body. V3 uses a bold question line (`**<question>.**`) with the answer as the immediately following paragraph — no `В:`/`О:` markers. Match the host file.
- **Senior-level depth in V3** is flagged with a leading `**Senior: ...**` on the question line.
- **Headings and the TOC in V1/V2 are coupled.** Anchors are slugified Cyrillic (`#1-архитектура-react-native`). Adding, renaming, or reordering a `##` section means updating the `## Оглавление` list and its anchors in the same file. V2's TOC already drifts from its headings (`## 5. Стилилизация компонентов` vs the TOC's "Стилизация") — fix mismatches like this rather than copying them.
- Sections are separated by `---`, and V1/V2 carry a metadata block (Версия / Позиция / Уровень / Язык) right under the H1.
- Content overlaps deliberately across files (the Bridge, New Architecture, and FlatList optimization appear in more than one). When asked to add a question, check whether it already exists elsewhere and either extend the right file or keep the per-file depth distinct — do not merge the files.

## Course (`course/`)

`course/COURSE_ARCHITECTURE.md` is the authoritative design document — read it before touching anything under `course/`. It fixes the 12 blocks, the dependency graph, checkpoints, cross-cutting concerns, the Security Map, the Testing Progression and the Migration Map. `course/README.md` is the public-facing entry point. Lesson text is written for blocks 01 and 02 (each lesson has its own folder with `README.md`, `theory.md`, `practice.md`); a lesson folder appears only together with its text. Every `NN-*/README.md` holds that block's plan, which stays the source of truth for lessons not yet written.

Rules that are easy to break:

- **Lesson levels are 🟢 REFRESH / 🟡 DEEP DIVE / 🔴 SENIOR.** 🟢 lessons follow a fixed shape: short refresh → comprehension check → **RN relevance** (the last part is mandatory; without it a 🟢 lesson degrades into a beginner tutorial). 🟡/🔴 lessons follow the seven angles listed in architecture section 6. Do not make every lesson 🔴.
- **`course/01-javascript/README.md` is the reference implementation of the block format** (25 lessons, 12 fields each; 1.25 was added later and is taken after 1.3). When detailing blocks 02–12, copy that structure rather than inventing a new one.
- **`V1.md` / `V2.md` / `V3.md` are not edited** until the corresponding lesson text is actually written. The Migration Map is an architectural map only (`вопрос → блок → формат`). When migration does happen later, the source file keeps the question plus a reference to the lesson — files are never emptied or left ragged.
- **Do not mix formats.** The question bank uses `### В:` / `**О:**` (V1, V2) or a bold question line (V3). Course material uses lesson tables and the per-lesson field template. Never carry one format into the other.
- Material deliberately appears in exactly one block; several blocks carry explicit "не дублировать" notes (navigation performance belongs to 05, push/server events to 07, cache mechanics to 07, reducers/selectors to 06). Respect them instead of repeating content.
- Security practices are never presented as a mandatory checklist — they follow `threat → mitigation → limitations → trade-offs → decision`.
- Lesson counts are a guide, not a contract: the block plans currently add up to 173 lessons, a soft target recounted from the block tables. Lessons added after a block is written take the next free number (e.g. 1.25, 2.15, 2.16) instead of renumbering, and the block README states where they belong in the learning order.

## Git

- **No co-authorship or tool attribution in commits.** Do not add `Co-Authored-By:` trailers, "Generated with Claude Code" lines, or any similar attribution to commit messages or PR descriptions in this repository. Commit messages end with their own content.
- `.idea/` (JetBrains IDE) is untracked and not ignored at the repo root; only `.idea/.gitignore` exists. Keep IDE files out of commits.
