# Здача WS9

## Дані

- Роль: dev
- Команда: therapy-scheduling
- GitHub-логін: maryan-qc
- Ваше репо: https://github.com/maryan-qc/therapy-scheduling
- SHA: 79b490bbcfbb7bb6a91c6444046627277be464af
- Репо вимог PM: https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling-spec
- Прод-URL: https://therapy-scheduling-sigma.vercel.app

## PM

—

## Розробник

### D0 — умова прийняття

- `/api/health`: https://therapy-scheduling-sigma.vercel.app/api/health — `"sha":"79b490bbcfbb7bb6a91c6444046627277be464af"`, `"db":"ok"`
- Зелений прогін `smoke` на `main`: https://github.com/maryan-qc/therapy-scheduling/actions/runs/42592657770
- `accounts.zip` на SHA: https://github.com/maryan-qc/therapy-scheduling/blob/79b490bbcfbb7bb6a91c6444046627277be464af/accounts.zip
- Ролі тестових акаунтів: адміністратор — admin1@example.test, pm-admin@example.test; планувальник — scheduler1@example.test, scheduler2@example.test, pm-scheduler@example.test; терапевт — therapist1@example.test, therapist2@example.test, pm-therapist@example.test; без ролі — newuser1@example.test. Паролі — лише в accounts.zip
- Версія `next`: next@16.4.3

### Зріз 3 звичайним способом

- AC зрізу 3: AC-INS-01, AC-INS-02, AC-INS-03, AC-INS-04, AC-INS-05, AC-INS-06 (вимога HryhoriiHaponiukQuitCode/therapy-scheduling-spec#33; вимогу #34 з AC-DOC-01…11 PM 2026-11-06 переніс на пізніший зріз — «у WS9 не реалізуємо»)
- `/requirements-sync` — PR «Оновлення вимог» (A): https://github.com/maryan-qc/therapy-scheduling/pull/42
- Спека `add-<зріз3>` і план — PR «Специфікація» (A): https://github.com/maryan-qc/therapy-scheduling/pull/43 (спека `add-insurance-consent`), https://github.com/maryan-qc/therapy-scheduling/pull/44 (план `impl-insurance-consent`)
- Після уточнень PM (A): https://github.com/maryan-qc/therapy-scheduling/pull/47 — `/requirements-sync` 2026-11-08 (PM переніс #34, AC не змінено; `clarify-<зріз3>` не потрібен; рядки AC-DOC — «відкладено (рішення PM…)» у #44)
- Питання PM (A): питань не було
- PR задач «Реалізація» (B): https://github.com/maryan-qc/therapy-scheduling/pull/45 (статус страхування, AC-INS-01…06), https://github.com/maryan-qc/therapy-scheduling/pull/48 (UAT зрізу 3, мутанти, proof pack, archive плану). Реалізацію документів згоди https://github.com/maryan-qc/therapy-scheduling/pull/46 закрито без злиття за рішенням PM
- Тести відмов здатні впасти (B): AC-INS-05 → SQL-мутанти C10 (без перевірки ролі), C11 (прямий update дозволено), C12 («Not set» повертається) — KILLED; AC-INS-06 → SQL-мутант C13 (anon має доступ до функції) — KILLED: https://github.com/maryan-qc/therapy-scheduling/pull/48, https://github.com/maryan-qc/therapy-scheduling/blob/79b490bbcfbb7bb6a91c6444046627277be464af/scripts/mutants.mjs#L90
- Ворота й `db-deploy` на `main` (B): quality https://github.com/maryan-qc/therapy-scheduling/actions/runs/42592601067; db-deploy з міграцією статусу страхування https://github.com/maryan-qc/therapy-scheduling/actions/runs/42527688004 (злиття #45)
- UAT — специфікації (C): https://github.com/maryan-qc/therapy-scheduling/blob/79b490bbcfbb7bb6a91c6444046627277be464af/tests/e2e/insurance.spec.ts
- UAT — звіт на проді (C): https://github.com/maryan-qc/therapy-scheduling/blob/79b490bbcfbb7bb6a91c6444046627277be464af/docs/qa/uat/2026-11-09/report.md — PASS 6 з 6
- UAT — PR зі звітом і відео (C): https://github.com/maryan-qc/therapy-scheduling/pull/48 (відео — ассети pre-release https://github.com/maryan-qc/therapy-scheduling/releases/tag/uat-2026-11-09, посилання в описі PR)
- UAT — негативний контроль (C): https://github.com/maryan-qc/therapy-scheduling/pull/48, розділ «Негативний контроль»: NC-1 → FAIL, NC-2 → NEEDS-HUMAN, NC-3 (AC-INS-01) → FAIL
- QA proof pack (C): https://github.com/maryan-qc/therapy-scheduling/blob/79b490bbcfbb7bb6a91c6444046627277be464af/docs/qa/proof-pack.md
- Не перевірено (C): порядок «тест до коду» (maker ≠ checker) для AC-INS-01…06 — тести написано тією самою сесією агента після коду; сила тестів відмов доведена мутантами C10–C13 і NC-3
- Відхилення від PM (C): не надходило
- Рядки `docs/conformance.md` (D): https://github.com/maryan-qc/therapy-scheduling/blob/79b490bbcfbb7bb6a91c6444046627277be464af/docs/conformance.md
- Акаунти для нових ролей зрізу 3 (D): нових ролей немає
- Ретро «що взяти з фабрики» (D): https://github.com/maryan-qc/therapy-scheduling/blob/79b490bbcfbb7bb6a91c6444046627277be464af/docs/qa/proof-pack.md#ретро-що-б-ми-взяли-з-фабрики-у-свій-звичайний-процес

## Бонус

—
