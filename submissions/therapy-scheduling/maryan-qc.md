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
- UAT — специфікації (C): AC-INS-01 https://github.com/maryan-qc/therapy-scheduling/blob/79b490bbcfbb7bb6a91c6444046627277be464af/tests/e2e/insurance.spec.ts#L80, AC-INS-02 https://github.com/maryan-qc/therapy-scheduling/blob/79b490bbcfbb7bb6a91c6444046627277be464af/tests/e2e/insurance.spec.ts#L102, AC-INS-03 https://github.com/maryan-qc/therapy-scheduling/blob/79b490bbcfbb7bb6a91c6444046627277be464af/tests/e2e/insurance.spec.ts#L145, AC-INS-04 https://github.com/maryan-qc/therapy-scheduling/blob/79b490bbcfbb7bb6a91c6444046627277be464af/tests/e2e/insurance.spec.ts#L210, AC-INS-05 https://github.com/maryan-qc/therapy-scheduling/blob/79b490bbcfbb7bb6a91c6444046627277be464af/tests/e2e/insurance.spec.ts#L237, AC-INS-06 https://github.com/maryan-qc/therapy-scheduling/blob/79b490bbcfbb7bb6a91c6444046627277be464af/tests/e2e/insurance.spec.ts#L290 — по тесту на кожен AC; у звіті — розділ і кадри на кожен AC-INS-01…06
- UAT — звіт на проді (C): https://github.com/maryan-qc/therapy-scheduling/blob/79b490bbcfbb7bb6a91c6444046627277be464af/docs/qa/uat/2026-11-09/report.md — PASS 6 з 6
- UAT — PR зі звітом і відео (C): https://github.com/maryan-qc/therapy-scheduling/pull/48 — відео кожного AC (AC-INS-01…06.webm) — ассети pre-release https://github.com/maryan-qc/therapy-scheduling/releases/tag/uat-2026-11-09, посилання по AC у таблиці опису PR (як у здачі WS8)
- UAT — негативний контроль (C): https://github.com/maryan-qc/therapy-scheduling/pull/48, розділ «Негативний контроль»: NC-1 → FAIL, NC-2 → NEEDS-HUMAN, NC-3 (AC-INS-01) → FAIL
- QA proof pack (C): https://github.com/maryan-qc/therapy-scheduling/blob/79b490bbcfbb7bb6a91c6444046627277be464af/docs/qa/proof-pack.md
- Не перевірено (C): порядок «тест до коду» (maker ≠ checker) для AC-INS-01…06 — тести написано тією самою сесією агента після коду; сила тестів відмов доведена мутантами C10–C13 і NC-3
- Відхилення від PM (C): не надходило
- Рядки `docs/conformance.md` (D): https://github.com/maryan-qc/therapy-scheduling/blob/79b490bbcfbb7bb6a91c6444046627277be464af/docs/conformance.md
- Акаунти для нових ролей зрізу 3 (D): нових ролей немає
- Ретро «що взяти з фабрики» (D): https://github.com/maryan-qc/therapy-scheduling/blob/79b490bbcfbb7bb6a91c6444046627277be464af/docs/qa/proof-pack.md#ретро-що-б-ми-взяли-з-фабрики-у-свій-звичайний-процес

## Бонус

### Фабрика в двійнику (розробник)

- Репо двійника: https://github.com/maryan-qc/therapy-scheduling-factory
- SHA двійника: 2ccc9cc9ca3068fe8847d76257a2015313a76e6a
- Прод двійника: https://therapy-scheduling-twin-mq-factory.vercel.app — `/api/health` https://therapy-scheduling-twin-mq-factory.vercel.app/api/health. Коміт злиття PR фабрики `db7c95d98ecb29517fc6806bb7b3f3ec8bf5aa51` health показував перед UAT. Зараз там `"sha"` = SHA двійника вище, `"db":"ok"`. Свої Supabase і Vercel; секрет `SUPABASE_DB_URL` у environment `production`; змінна `PROD_URL`; ruleset `factory-main` з обов'язковими `spec`, `app`, `conformance`, `db-check`
- Тег `ws9-base` в основному репо: https://github.com/maryan-qc/therapy-scheduling/tree/ws9-base (`d4dc4e7`, до зрізу 3)
- Фабрика й імпортер:
  - курс-редакція `koldovsky/2026-quitcode-09-factory` на https://github.com/koldovsky/2026-quitcode-09-factory/commit/1280bc62cb001ded1fa31f15f45057d8b51f45f3;
  - адаптер імпортера https://github.com/maryan-qc/2026-quitcode-09-factory/commit/74b0864fa6c4d70fb1559229a692ec846076fcda (гілка `team/therapy-scheduling` форку). Змінено лише точку розширення 5: імпортер не бере рядки-приклади з коментаря HTML у `docs/conformance.md` у pass-to-pass. Є 2 тести на знімку вимоги PM #33: без правки тест червоний, з нею зелений
- Формат вимог PM: issues «Вимога» в репо PM, знімок у `requirements/` через `/requirements-sync`. Критерії — рядками «- AC-INS-01: Дано … Коли … Тоді …», тож імпортер читає їх без змін (`--format lines`): 6 AC → 6 вимог, ID і текст дослівно
- Червоні тести (`tests-first`): https://github.com/maryan-qc/therapy-scheduling-factory/tree/ws9-red (`b61f3d2`). 12 тестів у 6 файлах `tests/insurance/`, червоні для AC-INS-01, AC-INS-02, AC-INS-03, AC-INS-04, AC-INS-05, AC-INS-06. Писала окрема сесія з тексту AC і контракту людини, а не з основного репо
- Приховані сценарії: набір `ins`, 27 сценаріїв — AC-INS-01: 4, AC-INS-02: 6, AC-INS-03: 4, AC-INS-04: 4, AC-INS-05: 5, AC-INS-06: 4. Запечатано (AES-256-GCM), файл лише в теці контролю, не в git. Писала окрема сесія
- AC, які доводить лише UAT: немає, усі 6 AC є в задачі фабрики. Частину AC-INS-06 «бачить лише сторінку входу» ворота фабрики не перевіряють (видимі тести й приховані сценарії стосуються бази) — її доводить тільки UAT
- Прогони фабрики:
  - `run-20261118095441-806406` — needs-human за 17 с, $0. На macOS фабрика прибирає змінну `USER`, і Claude Code відповідав «Not logged in». Обхід без зміни коду фабрики — обгортка в `agent.executable` + нове `approve config`;
  - `run-20261118101125-a92daa` — released: 2/3 спроби, $0.65, усі 9 воріт PASS, приховані 27/27, мутанти 4/4
- Пакети доказів: `run-20261118101125-a92daa`, дайджест `e2df8417cbd673ccdd850334e897a27f0ac01c35978c273178b399d3eb8fe8e9`. Лежить у https://github.com/maryan-qc/therapy-scheduling-factory/blob/db7c95d98ecb29517fc6806bb7b3f3ec8bf5aa51/docs/factory/run-20261118101125-a92daa.md і в описі PR фабрики. Додаток UAT: https://github.com/maryan-qc/therapy-scheduling-factory/blob/2ccc9cc9ca3068fe8847d76257a2015313a76e6a/docs/factory/run-20261118101125-a92daa.uat.md
- PR фабрики з автозлиттям: https://github.com/maryan-qc/therapy-scheduling-factory/pull/4 — `factory deliver` (push + PR + автозлиття squash), злито після CI. `db-deploy` двійника https://github.com/maryan-qc/therapy-scheduling-factory/actions/runs/44340064185 застосував `20261118100000_insurance_status.sql`
- UAT на проді двійника: https://github.com/maryan-qc/therapy-scheduling-factory/blob/2ccc9cc9ca3068fe8847d76257a2015313a76e6a/docs/qa/uat/2026-11-18/report.md — 6/6 PASS (R6), по кадру на кожен AC-INS-01…06. Прогін `factory uat`, рецензент записів Haiku. Сценарії — https://github.com/maryan-qc/therapy-scheduling-factory/blob/2ccc9cc9ca3068fe8847d76257a2015313a76e6a/tests/e2e/insurance.spec.ts
- Звіт порівняння: https://github.com/maryan-qc/therapy-scheduling-factory/blob/2ccc9cc9ca3068fe8847d76257a2015313a76e6a/docs/qa/factory-comparison.md
- Втручання людини й ліміти:
  - **Втручань 11:**
    - `approve config` ×2 (друге — через обгортку macOS), `approve intent` ×1, `approve plan` ×1;
    - «так» перед `factory deliver` ×1;
    - ручних комітів у двійнику 6: PR #1–#3 до прогону, коміт tests-first, PR #5 з UAT, PR #6 зі smoke і README.
  - `answer` і `resume` — 0, `approve release` — 0 (рівень auto).
  - Лімітів вистачило: $0.65 з бюджету $8 на прогін. Частковим прогін не був
