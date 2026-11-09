# Здача WS9

## Дані

- Роль: dev
- Команда: leave-portal
- GitHub-логін: lukian-tomochko
- Ваше репо: https://github.com/lukian-tomochko/leave-portal
- SHA: 29b11b3ac87c6d48b66e8cbea1e3c2dde7ad12a9
- Репо вимог PM: https://github.com/mkozlovskyi-ops/course-staff-management-spec
- Прод-URL: https://leave-portal-blush.vercel.app

## PM

—

## Розробник

### D0 — умова прийняття

- `/api/health`: https://leave-portal-blush.vercel.app/api/health — `{"ok":true,"sha":"29b11b3ac87c6d48b66e8cbea1e3c2dde7ad12a9","env":"production","db":"ok","reason":""}` (sha збігається з `main` на момент здачі)
- Зелений прогін `smoke` на `main`: https://github.com/lukian-tomochko/leave-portal/actions/runs/42613704874
- `accounts.zip` на SHA: https://github.com/lukian-tomochko/leave-portal/blob/29b11b3ac87c6d48b66e8cbea1e3c2dde7ad12a9/accounts.zip
- Ролі тестових акаунтів: працівник — teacher1@example.test, teacher2@example.test; менеджер — manager1@example.test, manager2@example.test; адміністратор — admin@example.test. Паролі — лише в accounts.zip
- Версія `next`: next@16.4.3

### Зріз 3 звичайним способом

- AC зрізу 3: AC-CAL-01, AC-CAL-02, AC-CAL-03, AC-CAL-04, AC-CAL-05, AC-CAL-06, AC-CAL-07, AC-CAL-08, AC-CAL-09, AC-CAL-10, AC-CAL-11, AC-CAL-12, AC-CAL-13, AC-CAL-14, AC-CAL-15, AC-LEAVE-22
- `/requirements-sync` — PR «Оновлення вимог» (A): https://github.com/lukian-tomochko/leave-portal/pull/44
- Спека `add-school-calendar` і план — PR «Специфікація» (A): https://github.com/lukian-tomochko/leave-portal/pull/45
- Після уточнень PM (A): `/requirements-sync` 2026-11-09: Вимоги актуальні (останній коміт PM у репо вимог — 03.11.2026, знімок 07.11 його містить), clarify-зміна не потрібна
- Питання PM (A): власних питань до PM не було; питання іншого розробника враховано в Open questions і AC-CAL-07/AC-LEAVE-22: https://github.com/mkozlovskyi-ops/course-staff-management-spec/issues/20, https://github.com/mkozlovskyi-ops/course-staff-management-spec/issues/21, https://github.com/mkozlovskyi-ops/course-staff-management-spec/issues/22, https://github.com/mkozlovskyi-ops/course-staff-management-spec/issues/23, https://github.com/mkozlovskyi-ops/course-staff-management-spec/issues/24
- PR задач «Реалізація» (B): https://github.com/lukian-tomochko/leave-portal/pull/46, https://github.com/lukian-tomochko/leave-portal/pull/47, https://github.com/lukian-tomochko/leave-portal/pull/48, https://github.com/lukian-tomochko/leave-portal/pull/49, https://github.com/lukian-tomochko/leave-portal/pull/50, https://github.com/lukian-tomochko/leave-portal/pull/51 (UAT, правки й виправлення: https://github.com/lukian-tomochko/leave-portal/pull/52, https://github.com/lukian-tomochko/leave-portal/pull/53, https://github.com/lukian-tomochko/leave-portal/pull/54, https://github.com/lukian-tomochko/leave-portal/pull/55, https://github.com/lukian-tomochko/leave-portal/pull/56). Відповіді на знахідки CodeRabbit: у PR #45–#48 їх дано після злиття (11 тредів), слушні виправлено в #56 — це описано в proof pack
- Тести відмов здатні впасти (B): AC-CAL-03 → SQL-мутанти S14, S15 KILLED; AC-CAL-05 → S16, S17 KILLED; AC-CAL-07 → S9, S13 KILLED; AC-CAL-10 → S11 KILLED; AC-CAL-11 → S12 KILLED; AC-CAL-13 → S6, S8 KILLED (`npm run mutation:sql`: 17 з 18 вбито, S1b — прийнятий еквівалентний): https://github.com/lukian-tomochko/leave-portal/pull/56 і https://github.com/lukian-tomochko/leave-portal/pull/47. AC-CAL-12 і AC-CAL-14 доводить лише e2e, мутанта на гейт сторінки й proxy немає — у «Не перевірено»
- Ворота й `db-deploy` на `main` (B): зелений quality https://github.com/lukian-tomochko/leave-portal/actions/runs/42613605086; зелений db-deploy на останньому SHA https://github.com/lukian-tomochko/leave-portal/actions/runs/42613605195; міграції зрізу застосовано db-deploy у PR #46, #47, #48: https://github.com/lukian-tomochko/leave-portal/actions/runs/42561617305, https://github.com/lukian-tomochko/leave-portal/actions/runs/42564652490, https://github.com/lukian-tomochko/leave-portal/actions/runs/42578142619
- UAT — специфікації (C): https://github.com/lukian-tomochko/leave-portal/blob/29b11b3ac87c6d48b66e8cbea1e3c2dde7ad12a9/tests/e2e/calendar.spec.ts
- UAT — звіт на проді (C): https://github.com/lukian-tomochko/leave-portal/blob/29b11b3ac87c6d48b66e8cbea1e3c2dde7ad12a9/docs/qa/uat/2026-11-09/report.md — 19 AC: PASS 17, FAIL 0, NEEDS-HUMAN 2 (AC-CAL-05, AC-CAL-13)
- UAT — PR зі звітом і відео (C): https://github.com/lukian-tomochko/leave-portal/pull/57 (відео — вкладенням в описі)
- UAT — негативний контроль (C): https://github.com/lukian-tomochko/leave-portal/pull/57 — NC-1 → FAIL (R1), NC-2 → NEEDS-HUMAN (R3)
- QA proof pack (C): https://github.com/lukian-tomochko/leave-portal/blob/29b11b3ac87c6d48b66e8cbea1e3c2dde7ad12a9/docs/qa/proof-pack.md
- Не перевірено (C): AC-CAL-12 (мутант на роль на сторінці не робили; роль у базі доводить AC-CAL-13), AC-CAL-14 (мутант на proxy не робили), AC-CAL-15 (мутант на текст повідомлення не робили); усі три пройшли UAT PASS, нижчий лише рівень доказу «здатен упасти». NEEDS-HUMAN у звіті: AC-CAL-05 і AC-CAL-13 — вирішує PM
- Відхилення від PM (C): не надходило станом на 2026-11-09 (issues «Відхилення від вимог» у репо немає). Виправлення після здачі — коментарем «Виправлено» з посиланням на PR і прогін UAT у тому ж issue до кінця Сб 14.11
- Рядки `docs/conformance.md` (D): https://github.com/lukian-tomochko/leave-portal/blob/29b11b3ac87c6d48b66e8cbea1e3c2dde7ad12a9/docs/conformance.md — усі 83 AC зі статусом «реалізовано», зокрема 16 AC зрізу 3
- Акаунти для нових ролей зрізу 3 (D): нових ролей немає (адміністратор admin@example.test існує з WS7)
- Ретро «що взяти з фабрики» (D): https://github.com/lukian-tomochko/leave-portal/blob/29b11b3ac87c6d48b66e8cbea1e3c2dde7ad12a9/docs/qa/retro-ws9.md

## Бонус

—
