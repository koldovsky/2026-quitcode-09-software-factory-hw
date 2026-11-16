# Здача WS9

## Дані

- Роль: dev
- Команда: school-purchasing
- GitHub-логін: kdeineko-tech
- Ваше репо: https://github.com/kdeineko-tech/school-purchasing
- SHA: a72065cfe2bb2a3636fe6b547ad127470c276597
- Репо вимог PM: https://github.com/ValiaBihun/2026-quitcode-dream-team
- Прод-URL: https://school-purchasing-lemon.vercel.app

## PM

—

## Розробник

### D0 — умова прийняття

- `/api/health`: https://school-purchasing-lemon.vercel.app/api/health — `"db":"ok"`, `"sha":"a72065cfe2bb2a3636fe6b547ad127470c276597"`
- Зелений прогін `smoke` на `main`: https://github.com/kdeineko-tech/school-purchasing/actions/runs/43715862836
- `accounts.zip` на SHA: https://github.com/kdeineko-tech/school-purchasing/blob/a72065cfe2bb2a3636fe6b547ad127470c276597/accounts.zip
- Ролі тестових акаунтів: заявник — pm-requester@example.test; схвалювач відділу — pm-approver@example.test; адміністратор — pm-admin@example.test
- Версія `next`: next@16.4.3

### Зріз 3 звичайним способом

- AC зрізу 3: AC-DEC-01, AC-DEC-04, AC-DEC-06, AC-DEC-07, AC-HIST-01, AC-HIST-02, AC-HIST-06, AC-HIST-10, AC-LANG-09
- `/requirements-sync` — PR «Оновлення вимог» (A): https://github.com/kdeineko-tech/school-purchasing/pull/44
- Спека `add-decision-history` і план — PR «Специфікація» (A): https://github.com/kdeineko-tech/school-purchasing/pull/45, https://github.com/kdeineko-tech/school-purchasing/pull/46
- Після уточнень PM (A): «Оновлення вимог» https://github.com/kdeineko-tech/school-purchasing/pull/47, https://github.com/kdeineko-tech/school-purchasing/pull/62, https://github.com/kdeineko-tech/school-purchasing/pull/66; «Специфікація» https://github.com/kdeineko-tech/school-purchasing/pull/51, https://github.com/kdeineko-tech/school-purchasing/pull/52, https://github.com/kdeineko-tech/school-purchasing/pull/63, https://github.com/kdeineko-tech/school-purchasing/pull/64
- Питання PM (A): https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/65, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/66, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/67, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/68, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/69, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/73, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/74, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/75
- PR задач «Реалізація» (B): https://github.com/kdeineko-tech/school-purchasing/pull/65, https://github.com/kdeineko-tech/school-purchasing/pull/67, https://github.com/kdeineko-tech/school-purchasing/pull/68, https://github.com/kdeineko-tech/school-purchasing/pull/69
- Тести відмов здатні впасти (B): AC-HIST-10 → червоний прогін https://github.com/kdeineko-tech/school-purchasing/actions/runs/42651649578, SQL-мутанти H2 і H3 KILLED https://github.com/kdeineko-tech/school-purchasing/pull/67; AC-DEC-06 → червоний прогін https://github.com/kdeineko-tech/school-purchasing/actions/runs/43061134000, SQL-мутант R1 KILLED https://github.com/kdeineko-tech/school-purchasing/pull/69; AC-DEC-07 (подає знову лише автор) → червоний прогін https://github.com/kdeineko-tech/school-purchasing/actions/runs/43061134000, SQL-мутант R2 KILLED https://github.com/kdeineko-tech/school-purchasing/pull/69
- Ворота й `db-deploy` на `main` (B): зелений quality https://github.com/kdeineko-tech/school-purchasing/actions/runs/43420786352; зелений CI з db-deploy https://github.com/kdeineko-tech/school-purchasing/actions/runs/43420786439 (остання міграція зрізу 3 застосована в https://github.com/kdeineko-tech/school-purchasing/actions/runs/43086890907)
- UAT — специфікації (C): https://github.com/kdeineko-tech/school-purchasing/blob/a72065cfe2bb2a3636fe6b547ad127470c276597/tests/e2e/numbers.spec.ts, https://github.com/kdeineko-tech/school-purchasing/blob/a72065cfe2bb2a3636fe6b547ad127470c276597/tests/e2e/history.spec.ts, https://github.com/kdeineko-tech/school-purchasing/blob/a72065cfe2bb2a3636fe6b547ad127470c276597/tests/e2e/partial-approval.spec.ts, https://github.com/kdeineko-tech/school-purchasing/blob/a72065cfe2bb2a3636fe6b547ad127470c276597/tests/e2e/return-for-revision.spec.ts, https://github.com/kdeineko-tech/school-purchasing/blob/a72065cfe2bb2a3636fe6b547ad127470c276597/tests/e2e/status-labels.spec.ts
- UAT — звіт на проді (C): https://github.com/kdeineko-tech/school-purchasing/blob/a72065cfe2bb2a3636fe6b547ad127470c276597/docs/qa/uat/2026-11-13/report.md — 9 AC: 8 PASS, 1 NEEDS-HUMAN (AC-HIST-06), 0 FAIL
- UAT — PR зі звітом і відео (C): https://github.com/kdeineko-tech/school-purchasing/pull/73 (прогін 13.11 з чистого дерева); перший звіт — https://github.com/kdeineko-tech/school-purchasing/pull/70
- UAT — негативний контроль (C): https://github.com/kdeineko-tech/school-purchasing/pull/73 — NC-1 (AC-APR-04, навмисно хибний текст) → FAIL (R1); також у https://github.com/kdeineko-tech/school-purchasing/pull/70 і в розділі C proof pack
- QA proof pack (C): https://github.com/kdeineko-tech/school-purchasing/blob/a72065cfe2bb2a3636fe6b547ad127470c276597/docs/qa/proof-pack.md
- Не перевірено (C): AC-LANG-09 «в історії» — поза WS9 за рішенням PM (ValiaBihun/2026-quitcode-dream-team#75); AC-HIST-01 «PUR-1» і «PUR-2» буквально на проді — на проді вже є заявки (PM прийняв «номери підряд», #73); AC-HIST-06, AC-HIST-10, AC-DEC-01, AC-DEC-04, AC-DEC-06: «Дано» з відділом «Початкова школа» (в AC-HIST-10 — ще й «Офіс») — UAT пише лише в синтетичні відділи «UAT» і «UAT-2»; AC-HIST-10 «історії не показано» й «статус не змінився» — лише прихованими твердженнями
- Відхилення від PM (C): не надходило — PM прийняла всі 9 AC з оцінкою 3: https://github.com/kdeineko-tech/school-purchasing/pull/70#issuecomment-6827375459
- Рядки `docs/conformance.md` (D): https://github.com/kdeineko-tech/school-purchasing/blob/a72065cfe2bb2a3636fe6b547ad127470c276597/docs/conformance.md — 9 AC зрізу 3 «реалізовано»
- Акаунти для нових ролей зрізу 3 (D): нових ролей немає — заявник, схвалювач відділу й адміністратор ті самі, що в зрізі 2; `accounts.zip` без змін (https://github.com/kdeineko-tech/school-purchasing/pull/50)
- Ретро «що взяти з фабрики» (D): https://github.com/kdeineko-tech/school-purchasing/blob/a72065cfe2bb2a3636fe6b547ad127470c276597/docs/qa/retro-ws9.md

## Бонус

—
