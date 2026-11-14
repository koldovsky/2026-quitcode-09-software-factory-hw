# Здача WS9

## Дані

- Роль: dev
- Команда: school-purchasing
- GitHub-логін: YarynaPankivv
- Ваше репо: https://github.com/YarynaPankivv/school-purchasing
- SHA: 4b7f65312705d4e87b890443fd1ef4148136bc9c
- Репо вимог PM: https://github.com/ValiaBihun/2026-quitcode-dream-team
- Прод-URL: https://school-purchasing.vercel.app

## PM

—

## Розробник

### D0 — умова прийняття

- `/api/health`: https://school-purchasing.vercel.app/api/health — `"db":"ok"`, sha `4b7f65312705d4e87b890443fd1ef4148136bc9c`
- Зелений прогін `smoke` на `main`: https://github.com/YarynaPankivv/school-purchasing/actions/runs/43631282937
- `accounts.zip` на SHA: https://github.com/YarynaPankivv/school-purchasing/blob/4b7f65312705d4e87b890443fd1ef4148136bc9c/accounts.zip
- Ролі тестових акаунтів: admin — admin@example.test, pm-admin@example.test; approver — approver@example.test, pm-approver@example.test (схвалює Primary School); requester — member1@example.test, member2@example.test, pm-requester@example.test, pm-empty@example.test. Паролі — лише в accounts.zip
- Версія `next`: next@16.4.3

### Зріз 3 звичайним способом

- AC зрізу 3: AC-DEC-01, AC-DEC-04, AC-DEC-06, AC-DEC-07, AC-HIST-01, AC-HIST-02, AC-HIST-06, AC-HIST-10, AC-LANG-09
- `/requirements-sync` — PR «Оновлення вимог» (A): https://github.com/YarynaPankivv/school-purchasing/pull/63, https://github.com/YarynaPankivv/school-purchasing/pull/64
- Спека `add-dec-hist` і план — PR «Специфікація» (A): https://github.com/YarynaPankivv/school-purchasing/pull/65 (спека), https://github.com/YarynaPankivv/school-purchasing/pull/66 (план `impl-dec-hist`)
- Після уточнень PM (A): https://github.com/YarynaPankivv/school-purchasing/pull/67 (`/requirements-sync` 2026-11-09, знімок актуальний); PM AC зрізу 3 не змінювала, тож `clarify` зрізу 3 не потрібен; уточнення AC-FRM-14 (зріз 2) — https://github.com/YarynaPankivv/school-purchasing/pull/79; за відгуком PM «Тоді» AC-LANG-09 у спеці дослівно за PM (зміна `clarify-dec-hist`) — https://github.com/YarynaPankivv/school-purchasing/pull/81
- Питання PM (A): https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/65 … https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/76 (закриті відповідями PM; журнал — https://github.com/YarynaPankivv/school-purchasing/blob/4b7f65312705d4e87b890443fd1ef4148136bc9c/docs/spec-reading.md)
- PR задач «Реалізація» (B): https://github.com/YarynaPankivv/school-purchasing/pull/68, https://github.com/YarynaPankivv/school-purchasing/pull/69, https://github.com/YarynaPankivv/school-purchasing/pull/70, https://github.com/YarynaPankivv/school-purchasing/pull/71, https://github.com/YarynaPankivv/school-purchasing/pull/72, https://github.com/YarynaPankivv/school-purchasing/pull/73, https://github.com/YarynaPankivv/school-purchasing/pull/74, https://github.com/YarynaPankivv/school-purchasing/pull/75, https://github.com/YarynaPankivv/school-purchasing/pull/76, https://github.com/YarynaPankivv/school-purchasing/pull/77, https://github.com/YarynaPankivv/school-purchasing/pull/78, https://github.com/YarynaPankivv/school-purchasing/pull/80, https://github.com/YarynaPankivv/school-purchasing/pull/82 (відгук PM і ментора: довжина тексту, прямий запис, мутанти, UAT-специфікації), https://github.com/YarynaPankivv/school-purchasing/pull/83 (повторний UAT 14.11, proof pack, негативні контролі, відео)
- Тести відмов здатні впасти (B): SQL- і TS-мутанти, 19 з 21 вбито, 2 еквівалентні (F1, D5) з поясненням у `scripts/mutants.mjs`; вивід — https://github.com/YarynaPankivv/school-purchasing/blob/4b7f65312705d4e87b890443fd1ef4148136bc9c/docs/qa/mutation/2026-11-13-mutants.md. AC-DEC-01 → D2, G1; AC-DEC-04 → D6; AC-DEC-06 → D1, D4, L1–L3; AC-DEC-07 → D3; AC-HIST-01 → N1; AC-HIST-02 → T1; AC-HIST-06 → H2; AC-HIST-10 → H1 (A1 і A2 ганяють і `dec-hist`); AC-LANG-09 → T2 — усі KILLED
- Ворота й `db-deploy` на `main` (B): зелений quality https://github.com/YarynaPankivv/school-purchasing/actions/runs/43631249327; зелений CI з `db-deploy` https://github.com/YarynaPankivv/school-purchasing/actions/runs/43631249420 (міграцію зрізу 3 застосовано в https://github.com/YarynaPankivv/school-purchasing/actions/runs/42781618637, міграцію довжини тексту з PR #82 — в https://github.com/YarynaPankivv/school-purchasing/actions/runs/43487236983)
- UAT — специфікації (C): https://github.com/YarynaPankivv/school-purchasing/blob/4b7f65312705d4e87b890443fd1ef4148136bc9c/tests/e2e/slice3.spec.ts (9 AC зрізу 3), https://github.com/YarynaPankivv/school-purchasing/blob/4b7f65312705d4e87b890443fd1ef4148136bc9c/tests/e2e/slice2.spec.ts (AC-FRM-09, AC-FRM-14, AC-APR-03)
- UAT — звіт на проді (C): https://github.com/YarynaPankivv/school-purchasing/blob/4b7f65312705d4e87b890443fd1ef4148136bc9c/docs/qa/uat/2026-11-14/report.md (прогін 14.11.2026 на чистому `82446df`, 12 з 12 PASS, R6; між `82446df` і поточним SHA змінено лише `docs/qa/**`, код ідентичний)
- UAT — PR зі звітом і відео (C): https://github.com/YarynaPankivv/school-purchasing/pull/83 (відео — вкладеннями в описі); попередній звіт 12.11 — https://github.com/YarynaPankivv/school-purchasing/pull/80
- UAT — негативні контролі (C): https://github.com/YarynaPankivv/school-purchasing/blob/4b7f65312705d4e87b890443fd1ef4148136bc9c/docs/qa/uat/2026-11-14/negative-controls/report.md: `npm run uat:nc` — NC-1 (AC-FRM-14) → FAIL (R1), NC-2 (AC-FRM-09) → NEEDS-HUMAN (R3), NC-3 (AC-DEC-06, зріз 3) → FAIL (R1); PASS не отримав жоден; `negativeControls` заповнено в https://github.com/YarynaPankivv/school-purchasing/blob/4b7f65312705d4e87b890443fd1ef4148136bc9c/docs/qa/uat/2026-11-14/manifest.json
- QA proof pack (C): https://github.com/YarynaPankivv/school-purchasing/blob/4b7f65312705d4e87b890443fd1ef4148136bc9c/docs/qa/proof-pack.md
- Не перевірено (C): AC-HIST-01 на проді (точні PUR-1 і PUR-2: нумерація на проді спільна, доведено в тесті бази на порожній базі); повний Stryker не гнали; сторінкування й суми повністю в SQL не робили (обмежено індекс пошуку й список схвалювачів), сліди UAT на проді (номери PUR, тимчасові схвалювачі) описано в proof pack; приймання PM ще немає
- Відхилення від PM (C): не надходило
- Рядки `docs/conformance.md` (D): https://github.com/YarynaPankivv/school-purchasing/blob/4b7f65312705d4e87b890443fd1ef4148136bc9c/docs/conformance.md
- Акаунти для нових ролей зрізу 3 (D): нових ролей немає
- Ретро «що взяти з фабрики» (D): https://github.com/YarynaPankivv/school-purchasing/blob/4b7f65312705d4e87b890443fd1ef4148136bc9c/docs/qa/retro-ws9.md

## Бонус

—
