# Здача WS9

## Дані

- Роль: dev
- Команда: therapy-scheduling
- GitHub-логін: SnatchPlay
- Ваше репо: https://github.com/SnatchPlay/therapy-scheduling
- SHA: ea1f73252f9081bbe97068627eeaa90296a74050
- Репо вимог PM: https://github.com/HryhoriiHaponiukQuitCode/therapy-scheduling-spec
- Прод-URL: https://therapy-scheduling-weld.vercel.app

## PM

—

## Розробник

### D0 — умова прийняття

- `/api/health`: https://therapy-scheduling-weld.vercel.app/api/health — відповідь `{"ok":true,"sha":"ea1f73252f9081bbe97068627eeaa90296a74050","env":"production","db":"ok","reason":""}` (запит `curl` 13.11.2026 після злиття PR #75)
- Зелений прогін `smoke` на `main`: https://github.com/SnatchPlay/therapy-scheduling/actions/runs/43403484219
- `accounts.zip` на SHA: https://github.com/SnatchPlay/therapy-scheduling/blob/ea1f73252f9081bbe97068627eeaa90296a74050/accounts.zip
- Ролі тестових акаунтів: адміністратор — admin@example.test; планувальники — scheduler1@example.test, scheduler2@example.test; терапевти — therapist1@example.test, therapist2@example.test. Нових ролей у зрізі 3 немає. Паролі — лише в accounts.zip
- Версія `next`: next@16.4.3

### Зріз 3 звичайним способом

- AC зрізу 3: AC-INS-01, AC-INS-02, AC-INS-03, AC-INS-04, AC-INS-05, AC-INS-06
- `/requirements-sync` — PR «Оновлення вимог» (A): https://github.com/SnatchPlay/therapy-scheduling/pull/67
- Спека `add-insurance-status` і план — PR «Специфікація» (A): https://github.com/SnatchPlay/therapy-scheduling/pull/68
- Після уточнень PM (A): уточнень PM до зрізу 3 не було; вимоги актуальні станом на знімок 2026-11-08 (PR https://github.com/SnatchPlay/therapy-scheduling/pull/67)
- Питання PM (A): питань не було
- PR задач «Реалізація» (B): https://github.com/SnatchPlay/therapy-scheduling/pull/69, https://github.com/SnatchPlay/therapy-scheduling/pull/70, https://github.com/SnatchPlay/therapy-scheduling/pull/71, https://github.com/SnatchPlay/therapy-scheduling/pull/73, https://github.com/SnatchPlay/therapy-scheduling/pull/74
- Тести відмов здатні впасти (B): AC-INS-04 → TS-мутант T9 KILLED, https://github.com/SnatchPlay/therapy-scheduling/pull/70; AC-INS-05 → SQL-мутант I1 KILLED, https://github.com/SnatchPlay/therapy-scheduling/pull/69, і TS-мутант T4 KILLED, https://github.com/SnatchPlay/therapy-scheduling/pull/70; AC-INS-06 → мутанта немає (Stryker не мутує `proxy.ts`), е2е-перевірка впала в негативному контролі NC-3 (FAIL, R1), https://github.com/SnatchPlay/therapy-scheduling/pull/75
- Ворота й `db-deploy` на `main` (B): зелений quality на SHA здачі https://github.com/SnatchPlay/therapy-scheduling/actions/runs/43403429894 (і на злитті зрізу 3: https://github.com/SnatchPlay/therapy-scheduling/actions/runs/42457667744); зелений db-deploy (у прогоні CI злиття міграції зрізу 3, PR #69) https://github.com/SnatchPlay/therapy-scheduling/actions/runs/42457667567; CI на SHA здачі https://github.com/SnatchPlay/therapy-scheduling/actions/runs/43403429927
- UAT — специфікації (C): https://github.com/SnatchPlay/therapy-scheduling/blob/ea1f73252f9081bbe97068627eeaa90296a74050/tests/e2e/insurance-status.spec.ts
- UAT — звіт на проді (C): https://github.com/SnatchPlay/therapy-scheduling/blob/ea1f73252f9081bbe97068627eeaa90296a74050/docs/qa/uat/2026-11-08/report.md
- UAT — PR зі звітом і відео (C): звіт і кадри — https://github.com/SnatchPlay/therapy-scheduling/pull/74; відео прогону записано (9 файлів), але до PR не прикріплено: за рішенням власника здаємо без відео, докази — кадри й звіт у репо
- UAT — негативний контроль (C): https://github.com/SnatchPlay/therapy-scheduling/pull/75: рядок звіту `npm run uat:nc` — NC-3 (AC-INS-06) → FAIL, а також NC-1 і NC-2 (AC-CARD-16) → FAIL (https://github.com/SnatchPlay/therapy-scheduling/blob/ea1f73252f9081bbe97068627eeaa90296a74050/docs/qa/uat/2026-11-08/negative-controls/report.md)
- QA proof pack (C): https://github.com/SnatchPlay/therapy-scheduling/blob/ea1f73252f9081bbe97068627eeaa90296a74050/docs/qa/proof-pack.md
- Не перевірено (C): AC-CARD-05 (зріз 2) — NEEDS-HUMAN, розбіжність акаунта в кадрі, рішення за PM; усі AC-INS-01…06 — приймання PM ще немає; частини «Тоді» поза кадром (scheduler2 бачить «Private pay» у AC-INS-03, прямий запит терапевта в AC-INS-05, scheduler1 після відмови в AC-INS-06) перевірені лише твердженнями Playwright
- Відхилення від PM (C): не надходило (за зрізом 3 issues «Відхилення від вимог» немає)
- Рядки `docs/conformance.md` (D): https://github.com/SnatchPlay/therapy-scheduling/blob/ea1f73252f9081bbe97068627eeaa90296a74050/docs/conformance.md
- Акаунти для нових ролей зрізу 3 (D): нових ролей немає
- Ретро «що взяти з фабрики» (D): https://github.com/SnatchPlay/therapy-scheduling/blob/ea1f73252f9081bbe97068627eeaa90296a74050/docs/qa/retro-ws9.md

## Бонус

Частковий прогін: двійник був лише локальним (без репо на GitHub, Supabase і Vercel), без поставки. Фабрика пройшла задачу бази, задачу інтерфейсу зупинили ворота.

### Фабрика в двійнику (розробник)

- Репо двійника: — (двійник лише локальний, на GitHub не створювався)
- SHA двійника: —
- Прод двійника: —
- Тег `ws9-base` в основному репо: https://github.com/SnatchPlay/therapy-scheduling/tree/ws9-base
- Фабрика й імпортер: курс-редакція koldovsky/2026-quitcode-09-factory, коміт `1280bc6`; імпортер без змін; єдина правка коду фабрики — список змінних оточення, https://github.com/SnatchPlay/therapy-scheduling/blob/ea1f73252f9081bbe97068627eeaa90296a74050/docs/qa/factory/factory-env-allowlist.patch.txt
- Формат вимог PM: вимоги PM — issues, їхній знімок у `requirements/` має рядки «Дано/Коли/Тоді» (lines), імпортер без змін
- Червоні тести (`tests-first`): у двійнику (лише локальний, тегів на GitHub немає): 19 червоних тестів бази для AC-INS-01, 02, 05 і 16 червоних тестів інтерфейсу для AC-INS-03, 04; самі файли не опубліковані
- Приховані сценарії: `insurance-db` — 16 сценаріїв разом на AC-INS-01, 02, 05 (розподіл по AC не збережено: набір видалено разом із двійником, пакет доказів фіксує лише «16/16»), `insurance-ui` — 21 сценарій (AC-INS-03: 13, AC-INS-04: 8); обидва набори запечатані, ключ у репо не потрапляв
- AC, які доводить лише UAT: AC-INS-06 (і потреба браузера для частин AC-INS-03, 04)
- Прогони фабрики: run-20261113071915-11de64 — needs-human («Not logged in»); run-20261113075354-8c1261 — needs-human («Not logged in»); run-20261113080551-ea8e5b — released; run-20261113081917-1e1f60 — released; run-20261113092653-5cbad1 (`insurance-ui`) — needs-human (ворота maintainability)
- Пакети доказів: run-20261113080551-ea8e5b — `ae7254422a49a4f328a289ad75b5121bd14141d0728629d2759004a3149eff80`, run-20261113081917-1e1f60 — `b304d0ffdf22ac661fc4fac3955911d84b5ea7a6ec98e4dded868c738a16ee62`, обидва в https://github.com/SnatchPlay/therapy-scheduling/tree/ea1f73252f9081bbe97068627eeaa90296a74050/docs/qa/factory; для зупиненого run-20261113092653-5cbad1 пакета немає, лише підсумок
- PR фабрики з автозлиттям: —
- UAT на проді двійника: —
- Звіт порівняння: https://github.com/SnatchPlay/therapy-scheduling/blob/ea1f73252f9081bbe97068627eeaa90296a74050/docs/qa/factory-comparison.md
- Втручання людини й ліміти: approve — 3 (конфіг і наміри двох задач), answer і resume — 0; ручні правки: послаблено 3 надто суворі твердження в червоних тестах, виправлено 2 приховані сценарії, оновлено один захищений тест, додано специфікацію й рядки матриці в двійник, правка змінних оточення фабрики; ліміту моделі вистачило

### PM

—
