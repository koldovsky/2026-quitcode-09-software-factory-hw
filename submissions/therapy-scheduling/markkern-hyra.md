# Здача WS9

## Дані

- Роль: dev
- Команда: therapy-scheduling
- GitHub-логін: markkern-hyra
- Ваше репо: https://github.com/markkern-hyra/therapy-scheduling
- SHA: 77116dc0eeb0ada0dd3abf6144835dfd5716fce8
- Репо вимог PM: https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling-spec
- Прод-URL: https://therapy-scheduling-theta.vercel.app

## PM

—

## Розробник

### D0 — умова прийняття

- `/api/health`: https://therapy-scheduling-theta.vercel.app/api/health
- Зелений прогін `smoke` на `main`: https://github.com/markkern-hyra/therapy-scheduling/actions/runs/42729206331
- `accounts.zip` на SHA: https://github.com/markkern-hyra/therapy-scheduling/blob/77116dc0eeb0ada0dd3abf6144835dfd5716fce8/accounts.zip
- Ролі тестових акаунтів: адміністратор — admin1@example.test; планувальник — scheduler1@example.test, scheduler2@example.test; терапевт — therapist1@example.test, therapist2@example.test; без ролі — newuser1@example.test
- Версія `next`: next@16.4.3

### Зріз 3 звичайним способом

- AC зрізу 3: AC-INS-01, AC-INS-02, AC-INS-03, AC-INS-04, AC-INS-05, AC-INS-06
- `/requirements-sync` — PR «Оновлення вимог» (A): https://github.com/markkern-hyra/therapy-scheduling/pull/40
- Спека `add-<зріз3>` і план — PR «Специфікація» (A): https://github.com/markkern-hyra/therapy-scheduling/pull/41
- Після уточнень PM (A): /requirements-sync 2026-11-09: Вимоги актуальні (знімок PR #40 — після останньої зміни PM 2026-11-06; на 2026-11-10 issues PM не змінювались)
- Питання PM (A): питань не було
- PR задач «Реалізація» (B): https://github.com/markkern-hyra/therapy-scheduling/pull/42, https://github.com/markkern-hyra/therapy-scheduling/pull/43, https://github.com/markkern-hyra/therapy-scheduling/pull/44
- Тести відмов здатні впасти (B): AC-INS-04 → SQL-мутант I6 KILLED (https://github.com/markkern-hyra/therapy-scheduling/pull/42), мутант «форма без canMark» — тест рендеру червоний (https://github.com/markkern-hyra/therapy-scheduling/pull/43); AC-INS-05 → SQL-мутанти I1, I2, I3 KILLED (https://github.com/markkern-hyra/therapy-scheduling/pull/42), TS-мутант I8 KILLED (https://github.com/markkern-hyra/therapy-scheduling/pull/43); AC-INS-06 → SQL-мутанти I4, I5 KILLED (https://github.com/markkern-hyra/therapy-scheduling/pull/42)
- Ворота й `db-deploy` на `main` (B): quality https://github.com/markkern-hyra/therapy-scheduling/actions/runs/42729158433; db-deploy (міграція зрізу 3) https://github.com/markkern-hyra/therapy-scheduling/actions/runs/42708818507
- UAT — специфікації (C): https://github.com/markkern-hyra/therapy-scheduling/blob/77116dc0eeb0ada0dd3abf6144835dfd5716fce8/tests/e2e/insurance.spec.ts
- UAT — звіт на проді (C): https://github.com/markkern-hyra/therapy-scheduling/blob/77116dc0eeb0ada0dd3abf6144835dfd5716fce8/docs/qa/uat/2026-11-10/report.md
- UAT — PR зі звітом і відео (C): https://github.com/markkern-hyra/therapy-scheduling/pull/44
- UAT — негативний контроль (C): https://github.com/markkern-hyra/therapy-scheduling/pull/44 — npm run uat:nc: NC-1 → FAIL (R1), NC-2 → NEEDS-HUMAN (R3)
- QA proof pack (C): https://github.com/markkern-hyra/therapy-scheduling/blob/77116dc0eeb0ada0dd3abf6144835dfd5716fce8/docs/qa/proof-pack.md
- Не перевірено (C): немає — кожен AC-INS-01…06 має тест і UAT PASS (R6) на проді. Поза AC (розділ «Не перевірено» proof pack): повний Stryker на коді зрізу 3 не запускали (є TS-мутант I8 і SQL-мутанти I1–I7, усі KILLED); одночасна позначка двома працівниками в AC не задана; приймання PM — після 10.11
- Відхилення від PM (C): не надходило
- Рядки `docs/conformance.md` (D): https://github.com/markkern-hyra/therapy-scheduling/blob/77116dc0eeb0ada0dd3abf6144835dfd5716fce8/docs/conformance.md
- Акаунти для нових ролей зрізу 3 (D): нових ролей немає
- Ретро «що взяти з фабрики» (D): https://github.com/markkern-hyra/therapy-scheduling/blob/77116dc0eeb0ada0dd3abf6144835dfd5716fce8/docs/qa/retro-ws9.md

## Бонус

### Фабрика в двійнику (розробник)

- Репо двійника: https://github.com/markkern-hyra/therapy-scheduling-factory
- SHA двійника: 4e4d3598a8f7d02de1e330ea5f1cacb0c80840a4
- Прод двійника: https://therapy-scheduling-factory.vercel.app — https://therapy-scheduling-factory.vercel.app/api/health (sha 4e4d359, db ok; код фабрики — злиття 4652f92)
- Тег `ws9-base` в основному репо: https://github.com/markkern-hyra/therapy-scheduling/tree/ws9-base
- Фабрика й імпортер: курс-редакція https://github.com/koldovsky/2026-quitcode-09-factory на коміті 1280bc62cb001ded1fa31f15f45057d8b51f45f3, без змін коду; імпортер tools/ac-to-task.mjs без адаптера
- Формат вимог PM: issue «Вимога» з розділом «Критерії приймання» → знімок requirements/33-planuvalnyk-poznachaie-status-perevirky.md (/requirements-sync, рядки «- AC-…: Дано … Коли … Тоді …»); імпорт `node tools/ac-to-task.mjs --file <двійник>/requirements/33-….md --ac AC-INS-01,…,AC-INS-06 --id insurance-status --holdout insurance-status --target <двійник> --size medium` — формат lines, імпортер без змін, адаптера немає
- Червоні тести (`tests-first`): https://github.com/markkern-hyra/therapy-scheduling-factory/tree/ws9-red — AC-INS-01, AC-INS-02, AC-INS-03, AC-INS-04, AC-INS-05, AC-INS-06
- Приховані сценарії: набір insurance-status — 23 сценарії (AC-INS-01 ×3, AC-INS-02 ×5, AC-INS-03 ×4, AC-INS-04 ×3, AC-INS-05 ×4, AC-INS-06 ×4), запечатано; файл лише в теці контролю, не в git
- AC, які доводить лише UAT: частини AC-INS-04 («змінити не запропоновано» на сторінці) і AC-INS-06 («лише сторінка входу»); самі AC є в задачі через базу й серверну дію
- Прогони фабрики: run-20261109210000-45bc64 — needs-human ($0, claude без входу на macOS: scrubEnv прибирає USER); run-20261109210921-ec46cc — released, delivered, UAT PASS (2/3 спроби, $0.72)
- Пакети доказів: run-20261109210921-ec46cc — дайджест a7ee64964551a7ae8cd0aa2e025d94cf3334b8077f192b284937fcd4119d7f39, https://github.com/markkern-hyra/therapy-scheduling-factory/blob/4e4d3598a8f7d02de1e330ea5f1cacb0c80840a4/docs/factory/run-20261109210921-ec46cc.md і опис https://github.com/markkern-hyra/therapy-scheduling-factory/pull/1
- PR фабрики з автозлиттям: https://github.com/markkern-hyra/therapy-scheduling-factory/pull/1 (автозлиття після required checks); db-deploy двійника https://github.com/markkern-hyra/therapy-scheduling-factory/actions/runs/42701236909 («Applying migration 20261109210000_client_insurance.sql»)
- UAT на проді двійника: https://github.com/markkern-hyra/therapy-scheduling-factory/blob/4e4d3598a8f7d02de1e330ea5f1cacb0c80840a4/docs/qa/uat/2026-11-09/report.md — AC-INS-01…06 PASS
- Звіт порівняння: https://github.com/markkern-hyra/therapy-scheduling/blob/77116dc0eeb0ada0dd3abf6144835dfd5716fce8/docs/qa/factory-comparison.md
- Втручання людини й ліміти: approve config ×2, approve intent ×2, approve plan ×1, resume ×1, answer 0; ручні коміти в двійнику — 3 (вимоги й специфікація, червоні тести, специфікації UAT) і PR звіту UAT; лімітів вистачило ($0.72 з $8 на прогін)

### PM

—
