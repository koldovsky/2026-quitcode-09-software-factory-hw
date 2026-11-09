# Здача WS9

## Дані

- Роль: dev
- Команда: property-workflows
- GitHub-логін: vhrytsyndyshynquitcode
- Ваше репо: https://github.com/vhrytsyndyshynquitcode/property-workflows
- SHA: 8f3cdef234d0e6e6766722db4c8473c699a918b0
- Репо вимог PM: https://github.com/solomchaak/property-workflows-spec
- Прод-URL: https://property-workflows-one.vercel.app

## PM

—

## Розробник

### D0 — умова прийняття

- `/api/health`: https://property-workflows-one.vercel.app/api/health — `"db":"ok"`, `sha` = 8f3cdef234d0e6e6766722db4c8473c699a918b0
- Зелений прогін `smoke` на `main`: https://github.com/vhrytsyndyshynquitcode/property-workflows/actions/runs/42604222361 (після розгортання `8f3cdef`)
- `accounts.zip` на SHA: https://github.com/vhrytsyndyshynquitcode/property-workflows/blob/8f3cdef234d0e6e6766722db4c8473c699a918b0/accounts.zip
- Ролі тестових акаунтів: адміністратор — pm-admin@example.test; менеджер — pm-manager@example.test; вендор — pm-vendor@example.test
- Версія `next`: next@16.4.3

### Зріз 3 звичайним способом

- AC зрізу 3: AC-VENDOR-01, AC-VENDOR-02, AC-VENDOR-03, AC-VENDOR-04, AC-VENDOR-05, AC-VENDOR-06, AC-VENDOR-07, AC-VENDOR-08, AC-VENDOR-09, AC-VENDOR-10
- `/requirements-sync` — PR «Оновлення вимог» (A): https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/40
- Спека `add-<зріз3>` і план — PR «Специфікація» (A): https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/41 (add-vendor-access, archive), https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/44 (план impl-vendor-access: design і tasks)
- Після уточнень PM (A): /requirements-sync 2026-11-09: Вимоги актуальні (PM AC зрізу 3 не змінював; знімок 2026-11-02)
- Питання PM (A): https://github.com/solomchaak/property-workflows-spec/issues/47 (моє); ті самі питання колеги — https://github.com/solomchaak/property-workflows-spec/issues/41, https://github.com/solomchaak/property-workflows-spec/issues/44 (не дублював); журнал — https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/43
- PR задач «Реалізація» (B): https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/45, https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/46, https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/47, https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/48, https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/49 — усі злиті; рев'ю CodeRabbit з відповіддю на кожну з 5 знахідок — #47; на #45, #46, #48, #49 CodeRabbit до злиття не відрецензував (запит `@coderabbitai review` — «Review skipped/failed»)
- Тести відмов здатні впасти (B): SQL-мутанти `scripts/mutants.mjs` — V01 (AC-VENDOR-01), V02 (AC-VENDOR-02), V04 (AC-VENDOR-04), V06 (AC-VENDOR-06), V07 (AC-VENDOR-07), V08 (AC-VENDOR-08), V09 (AC-VENDOR-09) — 7 з 7 KILLED: https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/45, https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/47
- Ворота й `db-deploy` на `main` (B): зелений quality https://github.com/vhrytsyndyshynquitcode/property-workflows/actions/runs/42604176702; db-deploy з «Apply migrations» — success: https://github.com/vhrytsyndyshynquitcode/property-workflows/actions/runs/42589905094
- UAT — специфікації (C): https://github.com/vhrytsyndyshynquitcode/property-workflows/blob/8f3cdef234d0e6e6766722db4c8473c699a918b0/tests/e2e/vendor.spec.ts (на кожен AC-VENDOR)
- UAT — звіт на проді (C): https://github.com/vhrytsyndyshynquitcode/property-workflows/blob/8f3cdef234d0e6e6766722db4c8473c699a918b0/docs/qa/uat/2026-11-09/report.md — 13 з 13 PASS (R6), з них усі 10 AC-VENDOR
- UAT — PR зі звітом і відео (C): https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/47
- UAT — негативний контроль (C): https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/47 — NC-1 (AC-EDITOR-07, хибний текст у твердженні) → FAIL (R1); NC-2 → NEEDS-HUMAN (R3)
- QA proof pack (C): https://github.com/vhrytsyndyshynquitcode/property-workflows/blob/8f3cdef234d0e6e6766722db4c8473c699a918b0/docs/qa/proof-pack.md
- Не перевірено (C): AC-VENDOR-10 — «здатен упасти»: порожній стан без правила бази (доведено unit і UAT); рішення до відповідей PM (#41, #44, #47) — зроблено за рекомендованими варіантами
- Відхилення від PM (C): не надходило
- Рядки `docs/conformance.md` (D): https://github.com/vhrytsyndyshynquitcode/property-workflows/blob/8f3cdef234d0e6e6766722db4c8473c699a918b0/docs/conformance.md — AC-VENDOR-01 … AC-VENDOR-10: реалізовано
- Акаунти для нових ролей зрізу 3 (D): вендор — pm-vendor@example.test (створено на проді `npm run users:demo` 09.11.2026), https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/45 (`supabase/demo-users.json`), `accounts.zip` з вендором — https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/49
- Ретро «що взяти з фабрики» (D): https://github.com/vhrytsyndyshynquitcode/property-workflows/blob/8f3cdef234d0e6e6766722db4c8473c699a918b0/docs/qa/retro-ws9.md

## Бонус

### Фабрика в двійнику (розробник)

- Репо двійника: https://github.com/vhrytsyndyshynquitcode/property-workflows-factory
- SHA двійника: a16b868073d6cd8ff8880ff0931192be97414932
- Прод двійника: https://property-workflows-factory.vercel.app — https://property-workflows-factory.vercel.app/api/health (`db: ok`, sha — коміт деплою `main`; злиття фабрики — c7bc8cc2568ee2fca056216b5851881e3eeaad2a)
- Тег `ws9-base` в основному репо: https://github.com/vhrytsyndyshynquitcode/property-workflows/tree/ws9-base
- Фабрика й імпортер: курс-редакція koldovsky/2026-quitcode-09-factory @ 1280bc62cb001ded1fa31f15f45057d8b51f45f3; адаптер імпортера — https://github.com/vhrytsyndyshynquitcode/2026-quitcode-09-factory/commit/71ea218fa706f8bb187ffe3bde1424c7706ae432 (гілка `team/property-workflows`)
- Формат вимог PM: issues «Вимога» з рядками `- AC-…: Дано … Коли … Тоді …` (lines); адаптер прибирає префікс «Requirement:» у назві задачі
- Червоні тести (`tests-first`): https://github.com/vhrytsyndyshynquitcode/property-workflows-factory/tree/ws9-red — AC-VENDOR-01 … AC-VENDOR-10 (з тексту AC, не з основного репо)
- Приховані сценарії: 4 набори (`vendor-role`, `vendor-access`, `vendor-run`, `vendor-lists`), 39 сценаріїв — по 4 на кожен AC (AC-VENDOR-05 — 3), запечатано; файли лише в теці контролю, не в git
- AC, які доводить лише UAT: немає окремих — але UAT на проді двійника не виконано (див. нижче)
- Прогони фабрики: run-20261109134056-955ac2 — released (5/5 спроб, $1.40); run-20261109142819-4b03ba — refused на допуску (AC вже виконано першим прогоном, $0)
- Пакети доказів: b1ace0fc9a37a89a7bd7843dd0bc471d8e3a9f3155fdd46fa368c79e802d824f — в описі https://github.com/vhrytsyndyshynquitcode/property-workflows-factory/pull/1
- PR фабрики з автозлиттям: https://github.com/vhrytsyndyshynquitcode/property-workflows-factory/pull/1 (`factory deliver` на справжньому репо, злито після required checks); db-deploy двійника — https://github.com/vhrytsyndyshynquitcode/property-workflows-factory/actions/runs/42634642583 (застосовано 20261109120000_vendor_role.sql)
- UAT на проді двійника: не виконано — для синтетичних акаунтів двійника потрібен секретний ключ Supabase двійника локально, його не внесено; приховані сценарії 38/39 на c7bc8cc (HV03a — хиба самого сценарію)
- Звіт порівняння: https://github.com/vhrytsyndyshynquitcode/property-workflows-factory/blob/a16b868073d6cd8ff8880ff0931192be97414932/docs/qa/factory-comparison.md
- Втручання людини й ліміти: approve config 1, approve intent 4, approve plan 1, answer 2, deliver 1, ручних комітів у код продукту — 0; лімітів вистачило ($1.40 з $8 на прогін). Знайдена вада: вендор закриває останню обов'язкову задачу без підтвердження (ворота не зловили, позначив рецензент фабрики)

### PM

—
