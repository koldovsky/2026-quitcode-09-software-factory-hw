# Здача WS9

## Дані

- Роль: dev
- Команда: school-purchasing
- GitHub-логін: YarynaPankivv
- Ваше репо: https://github.com/YarynaPankivv/school-purchasing
- SHA: 99469eb34443d75ac0cbe6cbfd5c19fdddb7e23b
- Репо вимог PM: https://github.com/ValiaBihun/2026-quitcode-dream-team
- Прод-URL: https://school-purchasing.vercel.app

## PM

—

## Розробник

### D0 — умова прийняття

- `/api/health`: https://school-purchasing.vercel.app/api/health — `"db":"ok"`, sha `99469eb34443d75ac0cbe6cbfd5c19fdddb7e23b`
- Зелений прогін `smoke` на `main`: https://github.com/YarynaPankivv/school-purchasing/actions/runs/43193018674
- `accounts.zip` на SHA: https://github.com/YarynaPankivv/school-purchasing/blob/99469eb34443d75ac0cbe6cbfd5c19fdddb7e23b/accounts.zip
- Ролі тестових акаунтів: admin — admin@example.test, pm-admin@example.test; approver — approver@example.test, pm-approver@example.test (схвалює Primary School); requester — member1@example.test, member2@example.test, pm-requester@example.test, pm-empty@example.test. Паролі — лише в accounts.zip
- Версія `next`: next@16.4.3

### Зріз 3 звичайним способом

- AC зрізу 3: AC-DEC-01, AC-DEC-04, AC-DEC-06, AC-DEC-07, AC-HIST-01, AC-HIST-02, AC-HIST-06, AC-HIST-10, AC-LANG-09
- `/requirements-sync` — PR «Оновлення вимог» (A): https://github.com/YarynaPankivv/school-purchasing/pull/63, https://github.com/YarynaPankivv/school-purchasing/pull/64
- Спека `add-dec-hist` і план — PR «Специфікація» (A): https://github.com/YarynaPankivv/school-purchasing/pull/65 (спека), https://github.com/YarynaPankivv/school-purchasing/pull/66 (план `impl-dec-hist`)
- Після уточнень PM (A): https://github.com/YarynaPankivv/school-purchasing/pull/67 (`/requirements-sync` 2026-11-09, знімок актуальний); PM AC зрізу 3 не змінював, тож `clarify` зрізу 3 не потрібен; уточнення AC-FRM-14 (зріз 2) — https://github.com/YarynaPankivv/school-purchasing/pull/79
- Питання PM (A): https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/65 … https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/75 (закриті відповідями PM; журнал — https://github.com/YarynaPankivv/school-purchasing/blob/99469eb34443d75ac0cbe6cbfd5c19fdddb7e23b/docs/spec-reading.md)
- PR задач «Реалізація» (B): https://github.com/YarynaPankivv/school-purchasing/pull/68, https://github.com/YarynaPankivv/school-purchasing/pull/69, https://github.com/YarynaPankivv/school-purchasing/pull/70, https://github.com/YarynaPankivv/school-purchasing/pull/71, https://github.com/YarynaPankivv/school-purchasing/pull/72, https://github.com/YarynaPankivv/school-purchasing/pull/73, https://github.com/YarynaPankivv/school-purchasing/pull/74, https://github.com/YarynaPankivv/school-purchasing/pull/75, https://github.com/YarynaPankivv/school-purchasing/pull/76, https://github.com/YarynaPankivv/school-purchasing/pull/77, https://github.com/YarynaPankivv/school-purchasing/pull/78, https://github.com/YarynaPankivv/school-purchasing/pull/80
- Тести відмов здатні впасти (B): AC-DEC-06 → SQL-мутанти D1 і D4 KILLED (https://github.com/YarynaPankivv/school-purchasing/pull/68); AC-HIST-10 → H1 KILLED (https://github.com/YarynaPankivv/school-purchasing/pull/71); AC-DEC-01 → D2 KILLED, AC-DEC-07 → D3 KILLED (https://github.com/YarynaPankivv/school-purchasing/pull/68); AC-HIST-06 → H2 KILLED, AC-HIST-01 → N1 KILLED (https://github.com/YarynaPankivv/school-purchasing/pull/76); `npm run mutation:sql`: 12 з 14 вбито, 2 еквівалентні (F1, D5) з поясненням у `scripts/mutants.mjs`
- Ворота й `db-deploy` на `main` (B): зелений quality https://github.com/YarynaPankivv/school-purchasing/actions/runs/43192954217; зелений db-deploy (в CI) https://github.com/YarynaPankivv/school-purchasing/actions/runs/43192954171 (міграцію зрізу 3 застосовано в https://github.com/YarynaPankivv/school-purchasing/actions/runs/42781618637)
- UAT — специфікації (C): https://github.com/YarynaPankivv/school-purchasing/blob/99469eb34443d75ac0cbe6cbfd5c19fdddb7e23b/tests/e2e/slice3.spec.ts (9 AC зрізу 3), https://github.com/YarynaPankivv/school-purchasing/blob/99469eb34443d75ac0cbe6cbfd5c19fdddb7e23b/tests/e2e/slice2.spec.ts (AC-FRM-09, AC-FRM-14, AC-APR-03)
- UAT — звіт на проді (C): https://github.com/YarynaPankivv/school-purchasing/blob/99469eb34443d75ac0cbe6cbfd5c19fdddb7e23b/docs/qa/uat/2026-11-12/report.md (прод `eaaf2fd`, 12 з 12 PASS)
- UAT — PR зі звітом і відео (C): https://github.com/YarynaPankivv/school-purchasing/pull/80 (відео — вкладенням в описі); перший звіт 10.11 — https://github.com/YarynaPankivv/school-purchasing/pull/75
- UAT — негативний контроль (C): https://github.com/YarynaPankivv/school-purchasing/pull/75: `npm run uat:nc` — NC-1 → FAIL (R1), NC-2 → NEEDS-HUMAN (R3); звіт NC лишається в `test-results/uat-report-nc/` (не в git)
- QA proof pack (C): https://github.com/YarynaPankivv/school-purchasing/blob/99469eb34443d75ac0cbe6cbfd5c19fdddb7e23b/docs/qa/proof-pack.md
- Не перевірено (C): AC-HIST-01 на проді (точні PUR-1 і PUR-2: нумерація на проді спільна, доведено в тесті бази); AC-DEC-04 без окремого SQL-мутанта; повний Stryker не гнали; приймання PM ще немає
- Відхилення від PM (C): не надходило
- Рядки `docs/conformance.md` (D): https://github.com/YarynaPankivv/school-purchasing/blob/99469eb34443d75ac0cbe6cbfd5c19fdddb7e23b/docs/conformance.md
- Акаунти для нових ролей зрізу 3 (D): нових ролей немає
- Ретро «що взяти з фабрики» (D): https://github.com/YarynaPankivv/school-purchasing/blob/99469eb34443d75ac0cbe6cbfd5c19fdddb7e23b/docs/qa/retro-ws9.md

## Бонус

—
