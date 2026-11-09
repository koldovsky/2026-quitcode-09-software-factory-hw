# Здача WS9

## Дані

- Роль: dev
- Команда: leave-portal
- GitHub-логін: rhutsul
- Ваше репо: https://github.com/rhutsul/leave-portal
- SHA: 432b5a7dd10e51d9aa45a41790fc1435e52feb8b
- Репо вимог PM: https://github.com/mkozlovskyi-ops/course-staff-management-spec
- Прод-URL: https://leave-portal-olive.vercel.app

## PM

—

## Розробник

### D0 — умова прийняття

- `/api/health`: https://leave-portal-olive.vercel.app/api/health
- Зелений прогін `smoke` на `main`: https://github.com/rhutsul/leave-portal/actions/runs/42634781148
- `accounts.zip` на SHA: https://github.com/rhutsul/leave-portal/blob/432b5a7dd10e51d9aa45a41790fc1435e52feb8b/accounts.zip
- Ролі тестових акаунтів: адміністратор — admin@example.test; менеджер — manager1@example.test, manager2@example.test; працівник — teacher1@example.test, teacher2@example.test
- Версія `next`: next@16.4.3

### Зріз 3 звичайним способом

- AC зрізу 3: AC-CAL-01, AC-CAL-02, AC-CAL-03, AC-CAL-04, AC-CAL-05, AC-CAL-06, AC-CAL-07, AC-CAL-08, AC-CAL-09, AC-CAL-10, AC-CAL-11, AC-CAL-12, AC-CAL-13, AC-CAL-14, AC-CAL-15
- `/requirements-sync` — PR «Оновлення вимог» (A): https://github.com/rhutsul/leave-portal/pull/47
- Спека `add-<зріз3>` і план — PR «Специфікація» (A): https://github.com/rhutsul/leave-portal/pull/61 (спека `add-school-calendar`), https://github.com/rhutsul/leave-portal/pull/62 (план `impl-school-calendar`)
- Після уточнень PM (A): звірено 2026-11-09 — вимоги актуальні: останній коміт PM — `818bad5` від 03.11, що й у знімку #47. Питання #22–#24 ще без відповіді, AC не змінювались.
- Питання PM (A): https://github.com/mkozlovskyi-ops/course-staff-management-spec/issues/22, https://github.com/mkozlovskyi-ops/course-staff-management-spec/issues/23, https://github.com/mkozlovskyi-ops/course-staff-management-spec/issues/24
- PR задач «Реалізація» (B): https://github.com/rhutsul/leave-portal/pull/63 (задача 1 — закриття), https://github.com/rhutsul/leave-portal/pull/64 (задача 2 — заявка в закритий і скорочений день), https://github.com/rhutsul/leave-portal/pull/65 (задача 3 — UAT), https://github.com/rhutsul/leave-portal/pull/66 (задача 4 — proof pack, ретро, архів плану); вигляд календаря понад AC — https://github.com/rhutsul/leave-portal/pull/67, https://github.com/rhutsul/leave-portal/pull/68
- Тести відмов здатні впасти (B):
  - AC-CAL-07 → SQL-мутанти S12 і S14 KILLED (https://github.com/rhutsul/leave-portal/pull/63);
  - AC-CAL-10 → S15 KILLED (#63);
  - AC-CAL-11 → S16 KILLED (#63);
  - AC-CAL-12 → Stryker `calendar/manage/access.ts`: 9 з 9 мутантів убито (https://github.com/rhutsul/leave-portal/pull/66);
  - AC-CAL-13 → S17 KILLED (#63);
  - AC-CAL-14 → S18 KILLED (#63);
  - AC-CAL-03 і AC-CAL-05 → S20, S21, S22 KILLED і Stryker `calendar.ts` 98,92 % (https://github.com/rhutsul/leave-portal/pull/64).
- Ворота й `db-deploy` на `main` (B): `quality` — https://github.com/rhutsul/leave-portal/actions/runs/42634684141; `db-deploy` останньої міграції зрізу — https://github.com/rhutsul/leave-portal/actions/runs/42507186501/job/128812732567
- UAT — специфікації (C): https://github.com/rhutsul/leave-portal/blob/432b5a7dd10e51d9aa45a41790fc1435e52feb8b/tests/e2e/calendar.spec.ts (один тест на кожен з 15 AC)
- UAT — звіт на проді (C): https://github.com/rhutsul/leave-portal/blob/432b5a7dd10e51d9aa45a41790fc1435e52feb8b/docs/qa/uat/2026-11-08/report.md (18 AC — PASS 18)
- UAT — PR зі звітом і відео (C): https://github.com/rhutsul/leave-portal/pull/65 (звіт, кадри); відео прогону на проді — вкладенням в описі https://github.com/rhutsul/leave-portal/pull/66
- UAT — негативний контроль (C): https://github.com/rhutsul/leave-portal/pull/65 — `npm run uat:nc`: NC-1 → FAIL, NC-2 → NEEDS-HUMAN
- QA proof pack (C): https://github.com/rhutsul/leave-portal/blob/432b5a7dd10e51d9aa45a41790fc1435e52feb8b/docs/qa/proof-pack.md
- Не перевірено (C):
  - AC-CAL-06 — стартове «used 0.00» на проді не виконувалось (там 1.85), перевірено приріст +1.00; дослівно сценарій перевіряють CI e2e і тест бази;
  - AC-CAL-01, -09, -15 — власного мутанта немає;
  - негативний контроль — на AC зрізу 1, а не AC-CAL;
  - звіти мутацій — лише в описах PR, у CI мутації не запускаються.
- Відхилення від PM (C): не надходило
- Рядки `docs/conformance.md` (D): https://github.com/rhutsul/leave-portal/blob/432b5a7dd10e51d9aa45a41790fc1435e52feb8b/docs/conformance.md (AC-CAL-01…15 — «реалізовано»)
- Акаунти для нових ролей зрізу 3 (D): нових ролей немає
- Ретро «що взяти з фабрики» (D): https://github.com/rhutsul/leave-portal/blob/432b5a7dd10e51d9aa45a41790fc1435e52feb8b/docs/qa/retro-ws9.md

## Бонус

—
