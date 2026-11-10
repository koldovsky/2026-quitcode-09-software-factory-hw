# Здача WS9

## Дані

- Роль: dev
- Команда: property-workflows
- GitHub-логін: vsmrnk
- Ваше репо: https://github.com/vsmrnk/property-workflows
- SHA: d7f967dd3793ab9b6dbe81e2de6d5ce2c4f64442
- Репо вимог PM: https://github.com/solomchaak/property-workflows-spec
- Прод-URL: https://property-workflows.vercel.app

## PM

—

## Розробник

### D0 — умова прийняття

- `/api/health`: https://property-workflows.vercel.app/api/health
- Зелений прогін `smoke` на `main`: https://github.com/vsmrnk/property-workflows/actions/runs/42811505903
- `accounts.zip` на SHA: https://github.com/vsmrnk/property-workflows/blob/d7f967dd3793ab9b6dbe81e2de6d5ce2c4f64442/accounts.zip
- Ролі тестових акаунтів: адміністратор — pm-admin@example.test; менеджер — pm-manager@example.test; постачальник (vendor) — pm-vendor@example.test. Паролі — лише в accounts.zip
- Версія `next`: next@16.4.3

### Зріз 3 звичайним способом

- AC зрізу 3: AC-VENDOR-01, AC-VENDOR-02, AC-VENDOR-03, AC-VENDOR-04, AC-VENDOR-05, AC-VENDOR-06, AC-VENDOR-07, AC-VENDOR-08, AC-VENDOR-09, AC-VENDOR-10
- `/requirements-sync` — PR «Оновлення вимог» (A): https://github.com/vsmrnk/property-workflows/pull/32
- Спека `add-<зріз3>` і план — PR «Специфікація» (A): https://github.com/vsmrnk/property-workflows/pull/42
- Після уточнень PM (A): /requirements-sync 2026-11-09: Вимоги актуальні (опис https://github.com/vsmrnk/property-workflows/pull/42); приймання WS9 — за текстом AC до 10.11 (PM, командний чат 10.11), тому оновлення вимог від 10.11 (AC-VENDOR-11 – AC-VENDOR-18, AC-TASK-19) не синхронізовано
- Питання PM (A): власних питань не ставив; неясні місця покривали наявні https://github.com/solomchaak/property-workflows-spec/issues/41, https://github.com/solomchaak/property-workflows-spec/issues/44, https://github.com/solomchaak/property-workflows-spec/issues/49
- PR задач «Реалізація» (B): https://github.com/vsmrnk/property-workflows/pull/43, https://github.com/vsmrnk/property-workflows/pull/44, https://github.com/vsmrnk/property-workflows/pull/46, https://github.com/vsmrnk/property-workflows/pull/47, https://github.com/vsmrnk/property-workflows/pull/49, https://github.com/vsmrnk/property-workflows/pull/50, https://github.com/vsmrnk/property-workflows/pull/48
- Тести відмов здатні впасти (B): AC-VENDOR-03 → SQL-мутанти V5, V11, V12, V14 KILLED; AC-VENDOR-04 → V3, V4, V10 KILLED; AC-VENDOR-06 → V5 KILLED; AC-VENDOR-07 → V6, V13 KILLED; AC-VENDOR-08 → V7 (SQL), V9 (TS) KILLED; AC-VENDOR-09 → V1 (SQL), V8 (TS) KILLED; таблиця «який тест упав» — https://github.com/vsmrnk/property-workflows/pull/48, TS-мутанти — https://github.com/vsmrnk/property-workflows/pull/44
- Ворота й `db-deploy` на `main` (B): зелений quality https://github.com/vsmrnk/property-workflows/actions/runs/42811452719; зелений db-deploy https://github.com/vsmrnk/property-workflows/actions/runs/42650177670 (міграція 20261109142910_vendor_role.sql)
- UAT — специфікації (C): https://github.com/vsmrnk/property-workflows/blob/d7f967dd3793ab9b6dbe81e2de6d5ce2c4f64442/tests/e2e/vendor-access.spec.ts (усі AC-VENDOR-01 – AC-VENDOR-10)
- UAT — звіт на проді (C): https://github.com/vsmrnk/property-workflows/blob/d7f967dd3793ab9b6dbe81e2de6d5ce2c4f64442/docs/qa/uat/2026-11-10/report.md
- UAT — PR зі звітом і відео (C): https://github.com/vsmrnk/property-workflows/pull/47
- UAT — негативний контроль (C): https://github.com/vsmrnk/property-workflows/pull/47: https://github.com/vsmrnk/property-workflows/blob/d7f967dd3793ab9b6dbe81e2de6d5ce2c4f64442/docs/qa/uat/2026-11-10/negative-controls/report.md — NC-1 → FAIL, NC-2 → FAIL (R1)
- QA proof pack (C): https://github.com/vsmrnk/property-workflows/blob/d7f967dd3793ab9b6dbe81e2de6d5ce2c4f64442/docs/qa/proof-pack.md
- Не перевірено (C): AC-VENDOR-01, 02 — повні адреси на кадрі обрізані (є в DOM-перевірці й трасі); AC-VENDOR-09 — «Дано» з версією 1 (на проді версія 3; версію 1 доводить тест бази); AC-VENDOR-04, 06, 08, 09 — payload RSC (межа — RLS, тести бази); зміна ролі під час сесії, телефон і темна тема, помилка бази на проді, збої `users:demo` в Auth
- Відхилення від PM (C): не надходило
- Рядки `docs/conformance.md` (D): https://github.com/vsmrnk/property-workflows/blob/d7f967dd3793ab9b6dbe81e2de6d5ce2c4f64442/docs/conformance.md
- Акаунти для нових ролей зрізу 3 (D): vendor — vendor-v@example.test, vendor-w@example.test, pm-vendor@example.test, https://github.com/vsmrnk/property-workflows/pull/43
- Ретро «що взяти з фабрики» (D): https://github.com/vsmrnk/property-workflows/blob/d7f967dd3793ab9b6dbe81e2de6d5ce2c4f64442/docs/qa/proof-pack.md#ретро-що-б-ми-взяли-з-фабрики-у-свій-звичайний-процес

## Бонус

—
