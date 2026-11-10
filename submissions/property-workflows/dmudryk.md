# Здача WS9

## Дані

- Роль: dev
- Команда: property-workflows
- GitHub-логін: dmudryk
- Ваше репо: https://github.com/dmudryk/property-workflows
- SHA: b46689782230707c9db53759753d155c40cdf7a2
- Репо вимог PM: https://github.com/solomchaak/property-workflows-spec
- Прод-URL: https://property-workflows-bravo16.vercel.app

## PM

—

## Розробник

### D0 — умова прийняття

- `/api/health`: https://property-workflows-bravo16.vercel.app/api/health
- Зелений прогін `smoke` на `main`: https://github.com/dmudryk/property-workflows/actions/runs/42827275480
- `accounts.zip` на SHA: https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/accounts.zip
- Ролі тестових акаунтів: менеджер — manager.a@example.test, manager.b@example.test, manager.c@example.test; адміністратор — admin@example.test; вендор — vendor@example.test. Паролі — лише в accounts.zip
- Версія `next`: next@16.4.3

### Зріз 3 звичайним способом

- AC зрізу 3: AC-VENDOR-01, AC-VENDOR-02, AC-VENDOR-03, AC-VENDOR-04, AC-VENDOR-05, AC-VENDOR-06, AC-VENDOR-07, AC-VENDOR-08, AC-VENDOR-09, AC-VENDOR-10 (приймання WS9 — текст до оновлення PM 10.11). Після уточнень PM 10.11 також реалізовано й доведено UAT: AC-VENDOR-11 … AC-VENDOR-18, AC-TASK-19
- `/requirements-sync` — PR «Оновлення вимог» (A): https://github.com/dmudryk/property-workflows/pull/30
- Спека `add-<зріз3>` і план — PR «Специфікація» (A): https://github.com/dmudryk/property-workflows/pull/33 (спека `add-ws8-vendor`), https://github.com/dmudryk/property-workflows/pull/37 (план `impl-ws8-vendor`)
- Після уточнень PM (A): https://github.com/dmudryk/property-workflows/pull/48 (`/requirements-sync` 2026-11-10), https://github.com/dmudryk/property-workflows/pull/49 (`clarify-ws8-vendor` — ADDED AC-VENDOR-11…18, AC-TASK-19, MODIFIED AC-VENDOR-07, 08; план `impl-clarify-ws8-vendor`)
- Питання PM (A): https://github.com/solomchaak/property-workflows-spec/issues/41, https://github.com/solomchaak/property-workflows-spec/issues/44 (мої Q1–Q3 вже поставили колеги команди — посилання в Open questions і `docs/spec-reading.md`, без дублікатів)
- PR задач «Реалізація» (B): https://github.com/dmudryk/property-workflows/pull/35, https://github.com/dmudryk/property-workflows/pull/42, https://github.com/dmudryk/property-workflows/pull/47, https://github.com/dmudryk/property-workflows/pull/50, https://github.com/dmudryk/property-workflows/pull/51
- Тести відмов здатні впасти (B): AC-VENDOR-06 → SQL-мутант V5 KILLED — https://github.com/dmudryk/property-workflows/pull/42; AC-VENDOR-07 → V6 KILLED — https://github.com/dmudryk/property-workflows/pull/42, V13 KILLED — https://github.com/dmudryk/property-workflows/pull/50, V11 (`completes_run`) KILLED — https://github.com/dmudryk/property-workflows/pull/47; AC-VENDOR-08 → V7 KILLED і Stryker `roles.ts` 14/24 → 24/24 — https://github.com/dmudryk/property-workflows/pull/42, тест рендеру червоний на сторінках до #50 — https://github.com/dmudryk/property-workflows/pull/46 (вивід в описі); AC-VENDOR-09 → V8 KILLED і Stryker `roles.ts` 24/24 — https://github.com/dmudryk/property-workflows/pull/42; AC-VENDOR-14 → тест рендеру червоний на сторінках до #50 — https://github.com/dmudryk/property-workflows/pull/46 (вивід в описі); AC-VENDOR-15 → V12 KILLED — https://github.com/dmudryk/property-workflows/pull/51 (V6, V9, V12–V14 на останньому визначенні `mark_task_done`, вивід в описі)
- Ворота й `db-deploy` на `main` (B): зелений quality https://github.com/dmudryk/property-workflows/actions/runs/42827215320; зелений db-deploy https://github.com/dmudryk/property-workflows/actions/runs/42817160629 («Applying migration 20261110121936_vendor_run_not_found_status.sql»), https://github.com/dmudryk/property-workflows/actions/runs/42813494892 («Applying migration 20261110095932_vendor_refusals.sql»), https://github.com/dmudryk/property-workflows/actions/runs/41461574408 (`20261102133247_vendor_role.sql`)
- UAT — специфікації (C): [AC-VENDOR-01](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/vendor-assign-at-launch.spec.ts), [AC-VENDOR-02](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/vendor-assignee-picker.spec.ts), [AC-VENDOR-03](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/vendor-runs-list.spec.ts), [AC-VENDOR-04](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/vendor-run-page.spec.ts), [AC-VENDOR-05](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/vendor-mark-done.spec.ts), [AC-VENDOR-06](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/vendor-foreign-run.spec.ts), [AC-VENDOR-07](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/vendor-foreign-task-direct.spec.ts), [AC-VENDOR-08](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/vendor-templates-forbidden.spec.ts), [AC-VENDOR-09](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/vendor-launch-direct.spec.ts), [AC-VENDOR-10](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/vendor-runs-empty.spec.ts), [AC-VENDOR-11](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/vendor-run-title.spec.ts), [AC-VENDOR-12](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/vendor-runs-row.spec.ts), [AC-VENDOR-13](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/vendor-sign-in.spec.ts), [AC-VENDOR-14](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/vendor-template-pages-forbidden.spec.ts), [AC-VENDOR-15](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/vendor-foreign-run-task-direct.spec.ts), [AC-VENDOR-16](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/vendor-completed-optional.spec.ts), [AC-VENDOR-17](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/vendor-direct-own-tasks.spec.ts), [AC-VENDOR-18](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/vendor-direct-foreign-data.spec.ts), [AC-TASK-19](https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/tests/e2e/task-completed-optional.spec.ts)
- UAT — звіт на проді (C): https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/docs/qa/uat/2026-11-10/report.md (19/19 PASS, код `bd52859`); також https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/docs/qa/uat/2026-11-09/report.md (AC-VENDOR-01…10, 10/10 PASS)
- UAT — PR зі звітом і відео (C): https://github.com/dmudryk/property-workflows/pull/43, https://github.com/dmudryk/property-workflows/pull/52
- UAT — негативний контроль (C): https://github.com/dmudryk/property-workflows/pull/43 — `npm run uat:nc`: NC-1 → FAIL (R1), NC-2 → NEEDS-HUMAN (R3), звіт https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/docs/qa/uat/2026-11-09-nc/report.md
- QA proof pack (C): https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/docs/qa/proof-pack.md
- Не перевірено (C): AC-TASK-19 — в UAT замість задачі «Order a part» необов'язкова задача «Read the meters» (на проді «Order a part» немає; точну назву доводить тест бази); AC-VENDOR-07, 09, 15, 17, 18 — сам запит «напряму» не на відео (Node `fetch` з токеном вендора), відповідь перевіряють твердження; назва й версія шаблону свого запуску вендору доступні запитом напряму (матриця прав, AC у PM немає) — деталі в розділі «Не перевірено» proof pack
- Відхилення від PM (C): не надходило
- Рядки `docs/conformance.md` (D): https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/docs/conformance.md
- Акаунти для нових ролей зрізу 3 (D): вендор — vendor@example.test, https://github.com/dmudryk/property-workflows/pull/39
- Ретро «що взяти з фабрики» (D): https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/docs/qa/proof-pack.md#ретро-що-б-ми-взяли-з-фабрики-у-свій-звичайний-процес

## Бонус

### Фабрика в двійнику (розробник)

- Репо двійника: https://github.com/dmudryk/property-workflows-factory
- SHA двійника: 942e7049a1c684b4200918813175de95abfea2e4
- Прод двійника: https://property-workflows-factory-gamma.vercel.app — https://property-workflows-factory-gamma.vercel.app/api/health (код фабрики — злиття PR #5, `86b6eee`; `db-deploy` https://github.com/dmudryk/property-workflows-factory/actions/runs/42811270300)
- Тег `ws9-base` в основному репо: https://github.com/dmudryk/property-workflows/tree/ws9-base
- Фабрика й імпортер: курс-редакція у fork https://github.com/dmudryk/2026-quitcode-09-factory (гілка `team/property-workflows`): https://github.com/dmudryk/2026-quitcode-09-factory/commit/15bdc66 (видалення робочої теки з junction `node_modules` у Git для Windows), https://github.com/dmudryk/2026-quitcode-09-factory/commit/f5da556 (тест імпортера на знімку issue PM); адаптер не знадобився
- Формат вимог PM: issues «Вимога» з полями форми, AC рядками `- AC-…: Given … When … Then …` (знімок `requirements/` від `/requirements-sync`) — формат «рядки» (lines), імпортер без змін
- Червоні тести (`tests-first`): https://github.com/dmudryk/property-workflows-factory/tree/ws9-red (T1 vendor-db: AC-VENDOR-01, 02, 06, 07, 09), https://github.com/dmudryk/property-workflows-factory/tree/ws9-red-2 (T2 vendor-pages: AC-VENDOR-03, 04, 05, 08, 10; у PR фабрики #5 — той самий коміт, перенесений на новий main: https://github.com/dmudryk/property-workflows-factory/commit/fe0bdb5)
- Приховані сценарії: набір `vendor-db` — 18 сценаріїв (AC-VENDOR-01: 5, 02: 3, 06: 3, 07: 4, 09: 3); набір `vendor-pages` — 21 (AC-VENDOR-03: 4, 04: 5, 05: 5, 08: 4, 10: 3); обидва запечатано, файли лише в теці контролю `C:pfcontrolholdouts*.json.enc`, не в git
- AC, які доводить лише UAT: немає (кожен AC-VENDOR-01…10 — видимий червоний тест + набір прихованих сценаріїв)
- Прогони фабрики: run-20261109210917-8b8b23 (vendor-db) — released → delivered; run-20261109214913-0cd73b (vendor-pages) — needs-human (нестабільний таймаут шаблонного тесту, лишено); run-20261110105855-97a2af (vendor-pages) — released → delivered
- Пакети доказів: `e9a1285f2eaf9563dd34fdbb1b369324c5587dde00a8cc0d362108d273a4053c` (T1) — опис https://github.com/dmudryk/property-workflows-factory/pull/3; `073ecaf80b65c9998cc36f4e90e39698cd7b2f75fe75358d2ca2442f5629076d` (T2) — опис https://github.com/dmudryk/property-workflows-factory/pull/5
- PR фабрики з автозлиттям: https://github.com/dmudryk/property-workflows-factory/pull/3, https://github.com/dmudryk/property-workflows-factory/pull/5 — злиті GitHub-ом після обов'язкових перевірок; db-deploy двійника https://github.com/dmudryk/property-workflows-factory/actions/runs/42701641052 (T1), https://github.com/dmudryk/property-workflows-factory/actions/runs/42811270300 (T2)
- UAT на проді двійника: https://github.com/dmudryk/property-workflows-factory/blob/942e7049a1c684b4200918813175de95abfea2e4/docs/qa/uat/2026-11-10/report.md — 10/10 PASS (ті самі приймальні специфікації, що й в основному репо; PR https://github.com/dmudryk/property-workflows-factory/pull/6)
- Звіт порівняння: https://github.com/dmudryk/property-workflows/blob/b46689782230707c9db53759753d155c40cdf7a2/docs/qa/factory-comparison.md
- Втручання людини й ліміти: 14 дій — 7 схвалень (config ×2, intent ×2, plan ×3), 1 `answer`, 2 `resume --recover` (ключ печатки введено з помилкою), 2 ручні коміти (twin #4 — таймаут нестабільного шаблонного тесту; `f4a9c2e` у PR #5 — тест `requireActor` для обов'язкового порогу покриття CI), 2 `deliver`. Ліміти вистачило: $2.26 за три прогони

### PM

—
