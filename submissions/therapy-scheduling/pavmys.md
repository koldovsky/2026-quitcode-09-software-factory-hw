# Здача WS9

## Дані

- Роль: dev
- Команда: therapy-scheduling
- GitHub-логін: pavmys
- Ваше репо: https://github.com/pavmys/therapy-scheduling
- SHA: ec115d650f2560869491222a04c5916ad17d1c38
- Репо вимог PM: https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling-spec
- Прод-URL: https://therapy-scheduling-three.vercel.app

## PM

—

## Розробник

### D0 — умова прийняття

- `/api/health`: https://therapy-scheduling-three.vercel.app/api/health
- Зелений прогін `smoke` на `main`: https://github.com/pavmys/therapy-scheduling/actions/runs/42686844410
- `accounts.zip` на SHA: https://github.com/pavmys/therapy-scheduling/blob/ec115d650f2560869491222a04c5916ad17d1c38/accounts.zip
- Ролі тестових акаунтів: адміністратор — pm-admin@example.test; планувальник — pm-scheduler@example.test; терапевт — pm-therapist@example.test
- Версія `next`: next@16.4.3

### Зріз 3 звичайним способом

- AC зрізу 3: AC-INS-01, AC-INS-02, AC-INS-03, AC-INS-04, AC-INS-05, AC-INS-06
- `/requirements-sync` — PR «Оновлення вимог» (A): https://github.com/pavmys/therapy-scheduling/pull/43
- Спека `add-<зріз3>` і план — PR «Специфікація» (A): https://github.com/pavmys/therapy-scheduling/pull/44
- Після уточнень PM (A): /requirements-sync 2026-11-09: вимоги актуальні — PM AC зрізу 3 не змінював (issue #33 востаннє змінено 2026-11-06)
- Питання PM (A): питань не було
- PR задач «Реалізація» (B): https://github.com/pavmys/therapy-scheduling/pull/45, https://github.com/pavmys/therapy-scheduling/pull/46, https://github.com/pavmys/therapy-scheduling/pull/47, https://github.com/pavmys/therapy-scheduling/pull/48
- Тести відмов здатні впасти (B): AC-INS-04 → TS-мутант I4 KILLED, AC-INS-05 → SQL-мутант I1 KILLED і TS-мутант I2 KILLED, AC-INS-06 → TS-мутант I3 KILLED — https://github.com/pavmys/therapy-scheduling/pull/46; заборона «Not set» (AC-INS-02) → SQL-мутант I5 KILLED — https://github.com/pavmys/therapy-scheduling/pull/48
- Ворота й `db-deploy` на `main` (B): зелений quality https://github.com/pavmys/therapy-scheduling/actions/runs/42686790835; зелений db-deploy https://github.com/pavmys/therapy-scheduling/actions/runs/42686790506 (міграцію зрізу застосовано в https://github.com/pavmys/therapy-scheduling/actions/runs/42623601881)
- UAT — специфікації (C): https://github.com/pavmys/therapy-scheduling/blob/ec115d650f2560869491222a04c5916ad17d1c38/tests/e2e/insurance-status.spec.ts
- UAT — звіт на проді (C): https://github.com/pavmys/therapy-scheduling/blob/ec115d650f2560869491222a04c5916ad17d1c38/docs/qa/uat/2026-11-09/report.md
- UAT — PR зі звітом і відео (C): https://github.com/pavmys/therapy-scheduling/pull/49 (звіт прогону після #48 і відео AC-INS-01…06 — вкладеннями в описі; перший звіт — https://github.com/pavmys/therapy-scheduling/pull/47)
- UAT — негативний контроль (C): https://github.com/pavmys/therapy-scheduling/pull/49: npm run uat:nc на проді — NC-1 → FAIL, NC-2 → NEEDS-HUMAN (https://github.com/pavmys/therapy-scheduling/blob/ec115d650f2560869491222a04c5916ad17d1c38/docs/qa/uat/2026-11-09/negative-controls/report.md)
- QA proof pack (C): https://github.com/pavmys/therapy-scheduling/blob/ec115d650f2560869491222a04c5916ad17d1c38/docs/qa/proof-pack.md
- Не перевірено (C): AC-INS-01…06 — у UAT на проді синтетичні картки замість сідових client6/client7 (статус «Not set» не повернути на спільному проді); негативний контроль — на AC-CARD-16, бо всі тести AC-INS пишуть у базу; код задачі 1 (#45) CodeRabbit не рецензував через ліміт
- Відхилення від PM (C): не надходило
- Рядки `docs/conformance.md` (D): https://github.com/pavmys/therapy-scheduling/blob/ec115d650f2560869491222a04c5916ad17d1c38/docs/conformance.md
- Акаунти для нових ролей зрізу 3 (D): нових ролей немає
- Ретро «що взяти з фабрики» (D): https://github.com/pavmys/therapy-scheduling/blob/ec115d650f2560869491222a04c5916ad17d1c38/docs/qa/proof-pack.md#ретро-що-б-ми-взяли-з-фабрики-у-свій-звичайний-процес

## Бонус

—
