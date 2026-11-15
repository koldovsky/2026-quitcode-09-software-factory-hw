# Здача WS9

## Дані

- Роль: dev
- Команда: leave-portal
- GitHub-логін: rhutsul
- Ваше репо: https://github.com/rhutsul/leave-portal
- SHA: a0a63b4ee3a1af1e3c9d282fd6f38830820d604c
- Репо вимог PM: https://github.com/mkozlovskyi-ops/course-staff-management-spec
- Прод-URL: https://leave-portal-olive.vercel.app

## PM

—

## Розробник

### D0 — умова прийняття

- `/api/health`: https://leave-portal-olive.vercel.app/api/health
- Зелений прогін `smoke` на `main`: https://github.com/rhutsul/leave-portal/actions/runs/43761470874
- `accounts.zip` на SHA: https://github.com/rhutsul/leave-portal/blob/a0a63b4ee3a1af1e3c9d282fd6f38830820d604c/accounts.zip
- Ролі тестових акаунтів: адміністратор — admin@example.test; менеджер — manager1@example.test, manager2@example.test; працівник — teacher1@example.test, teacher2@example.test
- Версія `next`: next@16.4.3

### Зріз 3 звичайним способом

- AC зрізу 3: AC-CAL-01, AC-CAL-02, AC-CAL-03, AC-CAL-04, AC-CAL-05, AC-CAL-06, AC-CAL-07, AC-CAL-08, AC-CAL-09, AC-CAL-10, AC-CAL-11, AC-CAL-12, AC-CAL-13, AC-CAL-14, AC-CAL-15, AC-CAL-16, AC-CAL-17, AC-CAL-18, AC-CAL-19, AC-CAL-20 (16–20 — після відповідей PM 13.11)
- `/requirements-sync` — PR «Оновлення вимог» (A): https://github.com/rhutsul/leave-portal/pull/47; після відповідей PM — https://github.com/rhutsul/leave-portal/pull/73 (знімок 2026-11-13, коміт PM `2f07791`)
- Спека `add-<зріз3>` і план — PR «Специфікація» (A): https://github.com/rhutsul/leave-portal/pull/61 (спека `add-school-calendar`), https://github.com/rhutsul/leave-portal/pull/62 (план `impl-school-calendar`)
- Після уточнень PM (A): PM відповів 13.11 на #22–#24 (наші) і #25, #26 (колеги) і додав AC-CAL-16…20 — `/requirements-sync` https://github.com/rhutsul/leave-portal/pull/73, спека `clarify-school-calendar` (ADDED і MODIFIED, ID AC PM ті самі) https://github.com/rhutsul/leave-portal/pull/74
- Питання PM (A): https://github.com/mkozlovskyi-ops/course-staff-management-spec/issues/22, https://github.com/mkozlovskyi-ops/course-staff-management-spec/issues/23, https://github.com/mkozlovskyi-ops/course-staff-management-spec/issues/24
- PR задач «Реалізація» (B): https://github.com/rhutsul/leave-portal/pull/63 (задача 1 — закриття), https://github.com/rhutsul/leave-portal/pull/64 (задача 2 — заявка в закритий і скорочений день), https://github.com/rhutsul/leave-portal/pull/65 (задача 3 — UAT), https://github.com/rhutsul/leave-portal/pull/66 (задача 4 — proof pack, ретро, архів плану); вигляд календаря понад AC — https://github.com/rhutsul/leave-portal/pull/67, https://github.com/rhutsul/leave-portal/pull/68; після відповідей PM — https://github.com/rhutsul/leave-portal/pull/75 (AC-CAL-16…20: код, міграція, тести) і https://github.com/rhutsul/leave-portal/pull/76 (UAT на проді, мутанти, proof pack); за рев'ю WS9 — https://github.com/rhutsul/leave-portal/pull/81 (план `impl-school-calendar-fixes`, питання PM Q13), https://github.com/rhutsul/leave-portal/pull/82 (сума часток дати ≤ 1.00, вид закриття в `add_school_closure`, міграція `20261115122625_day_share_cap_and_closure_kind.sql`), https://github.com/rhutsul/leave-portal/pull/83 (синтетичний працівник UAT для AC-CAL-06/16/20, UAT лише з чистого дерева, NC-3), https://github.com/rhutsul/leave-portal/pull/85 (повний UAT AC-CAL-01…20 на проді, proof pack, архів плану)
- Тести відмов здатні впасти (B):
  - AC-CAL-07 → SQL-мутанти S12 і S14 KILLED (https://github.com/rhutsul/leave-portal/pull/63);
  - AC-CAL-10 → S15 KILLED (#63);
  - AC-CAL-11 → S16 KILLED (#63);
  - AC-CAL-12 → Stryker `calendar/manage/access.ts`: 9 з 9 мутантів убито (https://github.com/rhutsul/leave-portal/pull/66);
  - AC-CAL-13 → S17 KILLED (#63);
  - AC-CAL-14 → S18 KILLED (#63);
  - AC-CAL-03 і AC-CAL-05 → S20, S21, S22 KILLED і Stryker `calendar.ts` 98,92 % (https://github.com/rhutsul/leave-portal/pull/64);
  - AC-CAL-16 … AC-CAL-20 → S23–S27 KILLED; S12–S17, S20, S22 переведено на нову міграцію, що перекрила функції, — 13 з 13 KILLED (https://github.com/rhutsul/leave-portal/pull/76);
  - за рев'ю WS9 → S28 (без `least` у `fix_day_share`), S29 (без `least` у `record_share`), S30 (без «Enter the closing time» у базі), S31 (`v_paid := null`, гілка «Sick leave»), S32 (назва через `btrim`) KILLED; разом 32 з 32 — таблиця https://github.com/rhutsul/leave-portal/blob/a0a63b4ee3a1af1e3c9d282fd6f38830820d604c/docs/qa/mutation-sql.md (https://github.com/rhutsul/leave-portal/pull/82, https://github.com/rhutsul/leave-portal/pull/83).
- Ворота й `db-deploy` на `main` (B): `quality` — https://github.com/rhutsul/leave-portal/actions/runs/43761419945; `db-deploy` останньої міграції зрізу (`20261115122625_day_share_cap_and_closure_kind.sql`) — https://github.com/rhutsul/leave-portal/actions/runs/43740399693/job/132892451803
- UAT — специфікації (C): https://github.com/rhutsul/leave-portal/blob/a0a63b4ee3a1af1e3c9d282fd6f38830820d604c/tests/e2e/calendar.spec.ts (один тест на кожен AC; AC-CAL-06, -16, -20 — на синтетичному працівнику `uat-…@example.test`)
- UAT — звіт на проді (C): https://github.com/rhutsul/leave-portal/blob/a0a63b4ee3a1af1e3c9d282fd6f38830820d604c/docs/qa/uat/2026-11-08/report.md (18 AC — PASS 18); після відповідей PM — https://github.com/rhutsul/leave-portal/blob/a0a63b4ee3a1af1e3c9d282fd6f38830820d604c/docs/qa/uat/2026-11-13/report.md (AC-CAL-17…20 — PASS 4); повний повторний прогін за рев'ю WS9 з `main @ edb808f`, чисте дерево, прод `edb808f` — https://github.com/rhutsul/leave-portal/blob/a0a63b4ee3a1af1e3c9d282fd6f38830820d604c/docs/qa/uat/2026-11-15/report.md (AC-CAL-01…20 — PASS 20, регрес WS8 — PASS 3; `manifest.json` з `gitDirty: false`)
- UAT — PR зі звітом і відео (C): https://github.com/rhutsul/leave-portal/pull/65 (звіт, кадри); відео прогону на проді — вкладенням в описі https://github.com/rhutsul/leave-portal/pull/66; повторний прогін 15.11 — https://github.com/rhutsul/leave-portal/pull/85, відео 20 AC-CAL одним файлом https://github.com/rhutsul/leave-portal/blob/a0a63b4ee3a1af1e3c9d282fd6f38830820d604c/docs/qa/uat/2026-11-15/uat-ac-cal.mp4
- UAT — негативний контроль (C): https://github.com/rhutsul/leave-portal/pull/65 — `npm run uat:nc`: NC-1 → FAIL, NC-2 → NEEDS-HUMAN; на зрізі 3 — NC-3 (AC-CAL-17, зворотний порядок частин) → FAIL, усі три в `manifest.negativeControls` звіту 15.11 разом із даними окремого прогону (https://github.com/rhutsul/leave-portal/pull/83, https://github.com/rhutsul/leave-portal/pull/85)
- QA proof pack (C): https://github.com/rhutsul/leave-portal/blob/a0a63b4ee3a1af1e3c9d282fd6f38830820d604c/docs/qa/proof-pack.md
- Не перевірено (C):
  - AC-CAL-01, -09, -15 — власного мутанта немає;
  - дзеркальний випадок частки дати (уже використано 0.65 іншим записом) — відкрите питання PM https://github.com/mkozlovskyi-ops/course-staff-management-spec/issues/28; поточну поведінку закріплює тест бази з позначкою «open question to PM»;
  - пароль синтетичного працівника потрапляє в трасу Playwright (траса не в git, пароль випадковий, користувача видаляють після прогону);
  - мутації в CI не запускаються — лише локально, таблиця в `docs/qa/mutation-sql.md`;
  - закрито за рев'ю WS9: AC-CAL-06, -16, -20 тепер на проді точно за «Дано»/«Тоді» (синтетичний працівник), NC на AC зрізу 3 (NC-3), таблиця мутацій у репо, мутант гілки «Sick leave» (S31), UAT лише з чистого дерева.
- Відхилення від PM (C): не надходило
- Рядки `docs/conformance.md` (D): https://github.com/rhutsul/leave-portal/blob/a0a63b4ee3a1af1e3c9d282fd6f38830820d604c/docs/conformance.md (AC-CAL-01…20 — «реалізовано»)
- Акаунти для нових ролей зрізу 3 (D): нових ролей немає
- Ретро «що взяти з фабрики» (D): https://github.com/rhutsul/leave-portal/blob/a0a63b4ee3a1af1e3c9d282fd6f38830820d604c/docs/qa/retro-ws9.md

## Бонус

—
