# Здача WS9

## Дані

- Роль: dev
- Команда: therapy-scheduling
- GitHub-логін: HryhoriiHaponiukQuitCode
- Ваше репо: https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling
- SHA: f5cd1f69df37a46b6c9d250b822fb0d96a8adbe3
- Репо вимог PM: https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling-spec
- Прод-URL: https://therapy-scheduling-two.vercel.app

## PM

—

## Розробник

### D0 — умова прийняття

- `/api/health`: https://therapy-scheduling-two.vercel.app/api/health — 16.11.2026: `{"ok":true,"sha":"f5cd1f69df37a46b6c9d250b822fb0d96a8adbe3","env":"production","db":"ok"}`
- Зелений прогін `smoke` на `main`: https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/actions/runs/43898552834
- `accounts.zip` на SHA: https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/blob/f5cd1f69df37a46b6c9d250b822fb0d96a8adbe3/accounts.zip
- Ролі тестових акаунтів: адміністратор — admin1@example.test; планувальник — scheduler1@example.test, scheduler2@example.test; терапевт — therapist1@example.test, therapist2@example.test
- Версія `next`: next@16.4.3

### Зріз 3 звичайним способом

- AC зрізу 3: AC-INS-01, AC-INS-02, AC-INS-03, AC-INS-04, AC-INS-05, AC-INS-06
- `/requirements-sync` — PR «Оновлення вимог» (A): https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/pull/50
- Спека `add-<зріз3>` і план — PR «Специфікація» (A): https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/pull/51 (спека `add-insurance-status`), https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/pull/52 (план `impl-insurance-status`)
- Після уточнень PM (A): «/requirements-sync 2026-11-13: Вимоги актуальні» — issue PM #33 не змінювався після знімка 2026-11-06 (proof pack, розділ A)
- Питання PM (A): питань не було
- PR задач «Реалізація» (B): https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/pull/53, https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/pull/54, https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/pull/55, https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/pull/56 (UAT), https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/pull/57 (proof pack, негативний контроль, archive плану) — усі злиті
- Тести відмов здатні впасти (B): AC-INS-05 → SQL-мутант I1 KILLED, AC-INS-02 → I2 KILLED (https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/pull/55, вивід `npm run mutation:sql` в описі); AC-INS-06 → I3 KILLED (https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/pull/57); AC-INS-04 — лише заява про абляцію в описі #55, у «Не перевірено»
- Ворота й `db-deploy` на `main` (B): зелений quality https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/actions/runs/43898439522; db-deploy з міграціями зрізу 3 — https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/actions/runs/42402369147 (#53), https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/actions/runs/43281936922 (#55)
- UAT — специфікації (C): https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/blob/f5cd1f69df37a46b6c9d250b822fb0d96a8adbe3/tests/e2e/client-insurance.spec.ts (AC-INS-01…06)
- UAT — звіт на проді (C): https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/blob/f5cd1f69df37a46b6c9d250b822fb0d96a8adbe3/docs/qa/uat/2026-11-12/report.md
- UAT — PR зі звітом і відео (C): https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/pull/56 (відео прогону 5 — у коментарі https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/pull/56#issuecomment-6835166282)
- UAT — негативний контроль (C): https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/pull/56 — https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/blob/f5cd1f69df37a46b6c9d250b822fb0d96a8adbe3/docs/qa/uat/2026-11-12/negative-controls/report.md: NC-1 → FAIL, NC-2 → NEEDS-HUMAN; NC-3 на AC-INS-06 — https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/pull/57
- QA proof pack (C): https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/blob/f5cd1f69df37a46b6c9d250b822fb0d96a8adbe3/docs/qa/proof-pack.md
- Не перевірено (C): AC-INS-06 на проді лише GET картки без входу; AC-INS-05 на проді одна пряма спроба через API; «здатен упасти» для AC-INS-01, 03, 04 — лише заяви в описах PR; правило «повернути Not set не можна» без власного AC; статус у розкладі терапевта без тесту; стан форми після чужої зміни без тесту; відео прогонів 1–2; PR #54 без рев'ю CodeRabbit (ліміт) — подробиці в розділі «Не перевірено» proof pack
- Відхилення від PM (C): не надходило (issues «Відхилення від вимог» у репо немає)
- Приймання PM (C): самоприймання: PM і розробник одна людина (PM передано 03.11), оцінку має підтвердити викладач. Підпис PM: https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/pull/56#issuecomment-6922886029 (16.11.2026): AC-INS-01…06 ✅, кадри «Тоді» звіту UAT переглянуто, вердикт агента (PASS) збігається з кадрами. Таблиця приймання PM: вкладка therapy-scheduling, AC-INS-01…06 — оцінка 3, «прийнято»
- Рядки `docs/conformance.md` (D): https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/blob/f5cd1f69df37a46b6c9d250b822fb0d96a8adbe3/docs/conformance.md — AC-INS-01…06 «реалізовано»
- Акаунти для нових ролей зрізу 3 (D): нових ролей немає
- Ретро «що взяти з фабрики» (D): https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling/blob/f5cd1f69df37a46b6c9d250b822fb0d96a8adbe3/docs/qa/retro-ws9.md

## Бонус

—
