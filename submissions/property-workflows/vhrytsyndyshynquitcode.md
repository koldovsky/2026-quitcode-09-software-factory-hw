# Здача WS9

## Дані

- Роль: dev
- Команда: property-workflows
- GitHub-логін: vhrytsyndyshynquitcode
- Ваше репо: https://github.com/vhrytsyndyshynquitcode/property-workflows
- SHA: f76d3f6b639474e188b3715187b92ca7bae6d68f
- Репо вимог PM: https://github.com/solomchaak/property-workflows-spec
- Прод-URL: https://property-workflows-one.vercel.app

## PM

—

## Розробник

### D0 — умова прийняття

- `/api/health`: https://property-workflows-one.vercel.app/api/health — `"db":"ok"`, `sha` = f76d3f6b639474e188b3715187b92ca7bae6d68f
- Зелений прогін `smoke` на `main`: https://github.com/vhrytsyndyshynquitcode/property-workflows/actions/runs/42601477311 (після розгортання `f76d3f6`)
- `accounts.zip` на SHA: https://github.com/vhrytsyndyshynquitcode/property-workflows/blob/f76d3f6b639474e188b3715187b92ca7bae6d68f/accounts.zip
- Ролі тестових акаунтів: адміністратор — pm-admin@example.test; менеджер — pm-manager@example.test; вендор — pm-vendor@example.test
- Версія `next`: next@16.4.3

### Зріз 3 звичайним способом

- AC зрізу 3: AC-VENDOR-01, AC-VENDOR-02, AC-VENDOR-03, AC-VENDOR-04, AC-VENDOR-05, AC-VENDOR-06, AC-VENDOR-07, AC-VENDOR-08, AC-VENDOR-09, AC-VENDOR-10
- `/requirements-sync` — PR «Оновлення вимог» (A): https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/40
- Спека `add-<зріз3>` і план — PR «Специфікація» (A): https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/41 (add-vendor-access, archive), https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/44 (план impl-vendor-access: design і tasks)
- Після уточнень PM (A): /requirements-sync 2026-11-09: Вимоги актуальні (PM AC зрізу 3 не змінював; знімок 2026-11-02)
- Питання PM (A): https://github.com/solomchaak/property-workflows-spec/issues/47 (моє); ті самі питання колеги — https://github.com/solomchaak/property-workflows-spec/issues/41, https://github.com/solomchaak/property-workflows-spec/issues/44 (не дублював); журнал — https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/43
- PR задач «Реалізація» (B): https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/45, https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/46, https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/47, https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/48 — усі злиті; рев'ю CodeRabbit з відповіддю на кожну з 5 знахідок — #47; на #45, #46, #48 CodeRabbit до злиття не відрецензував (запит `@coderabbitai review` — «Review skipped/failed»)
- Тести відмов здатні впасти (B): SQL-мутанти `scripts/mutants.mjs` — V01 (AC-VENDOR-01), V02 (AC-VENDOR-02), V04 (AC-VENDOR-04), V06 (AC-VENDOR-06), V07 (AC-VENDOR-07), V08 (AC-VENDOR-08), V09 (AC-VENDOR-09) — 7 з 7 KILLED: https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/45, https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/47
- Ворота й `db-deploy` на `main` (B): зелений quality https://github.com/vhrytsyndyshynquitcode/property-workflows/actions/runs/42601429495; db-deploy з «Apply migrations» — success: https://github.com/vhrytsyndyshynquitcode/property-workflows/actions/runs/42589905094
- UAT — специфікації (C): https://github.com/vhrytsyndyshynquitcode/property-workflows/blob/f76d3f6b639474e188b3715187b92ca7bae6d68f/tests/e2e/vendor.spec.ts (на кожен AC-VENDOR)
- UAT — звіт на проді (C): https://github.com/vhrytsyndyshynquitcode/property-workflows/blob/f76d3f6b639474e188b3715187b92ca7bae6d68f/docs/qa/uat/2026-11-09/report.md — 13 з 13 PASS (R6), з них усі 10 AC-VENDOR
- UAT — PR зі звітом і відео (C): https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/47
- UAT — негативний контроль (C): https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/47 — NC-1 (AC-EDITOR-07, хибний текст у твердженні) → FAIL (R1); NC-2 → NEEDS-HUMAN (R3)
- QA proof pack (C): https://github.com/vhrytsyndyshynquitcode/property-workflows/blob/f76d3f6b639474e188b3715187b92ca7bae6d68f/docs/qa/proof-pack.md
- Не перевірено (C): AC-VENDOR-10 — «здатен упасти»: порожній стан без правила бази (доведено unit і UAT); рішення до відповідей PM (#41, #44, #47) — зроблено за рекомендованими варіантами
- Відхилення від PM (C): не надходило
- Рядки `docs/conformance.md` (D): https://github.com/vhrytsyndyshynquitcode/property-workflows/blob/f76d3f6b639474e188b3715187b92ca7bae6d68f/docs/conformance.md — AC-VENDOR-01 … AC-VENDOR-10: реалізовано
- Акаунти для нових ролей зрізу 3 (D): вендор — pm-vendor@example.test (створено на проді `npm run users:demo` 09.11.2026), https://github.com/vhrytsyndyshynquitcode/property-workflows/pull/45 (`supabase/demo-users.json`); у `accounts.zip` на цьому SHA рядка вендора ще немає (перешифрування паролем курсу — окремим PR), пароль вендора той самий, що в pm-admin і pm-manager
- Ретро «що взяти з фабрики» (D): https://github.com/vhrytsyndyshynquitcode/property-workflows/blob/f76d3f6b639474e188b3715187b92ca7bae6d68f/docs/qa/retro-ws9.md

## Бонус

—
