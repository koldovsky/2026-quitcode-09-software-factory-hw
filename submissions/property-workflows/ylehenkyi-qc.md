# Здача WS9

## Дані

- Роль: dev
- Команда: property-workflows
- GitHub-логін: ylehenkyi-qc
- Ваше репо: https://github.com/ylehenkyi-qc/property-workflows
- SHA: a5302fa5a2788a97381b29701e884d78d6e65aad
- Репо вимог PM: https://github.com/solomchaak/property-workflows-spec
- Прод-URL: https://pmwp-ylehenkyi.vercel.app

## PM

—

## Розробник

### D0 — умова прийняття

- `/api/health`: https://pmwp-ylehenkyi.vercel.app/api/health
- Зелений прогін `smoke` на `main`: https://github.com/ylehenkyi-qc/property-workflows/actions/runs/43710794872
- `accounts.zip` на SHA: https://github.com/ylehenkyi-qc/property-workflows/blob/a5302fa5a2788a97381b29701e884d78d6e65aad/accounts.zip
- Ролі тестових акаунтів: адміністратор — admin@example.test, pm-admin@example.test; менеджер — manager1@example.test, manager2@example.test, pm-manager@example.test; вендор — vendor1@example.test, vendor2@example.test. Паролі — лише в accounts.zip
- Версія `next`: next@16.4.3

### Зріз 3 звичайним способом

- AC зрізу 3: AC-VENDOR-01, AC-VENDOR-02, AC-VENDOR-03, AC-VENDOR-04, AC-VENDOR-05, AC-VENDOR-06, AC-VENDOR-07, AC-VENDOR-08, AC-VENDOR-09, AC-VENDOR-10
- `/requirements-sync` — PR «Оновлення вимог» (A): https://github.com/ylehenkyi-qc/property-workflows/pull/35
- Спека `add-vendor-access` і план — PR «Специфікація» (A): https://github.com/ylehenkyi-qc/property-workflows/pull/43, https://github.com/ylehenkyi-qc/property-workflows/pull/44
- Після уточнень PM (A): `/requirements-sync 2026-11-09: Вимоги актуальні` (знімок 2026-11-02). Після цього PM оновив вимоги 10.11 (AC-VENDOR-11…18, AC-TASK-19, уточнено AC-VENDOR-07 і 08) і написав у чаті команди, що приймання WS9 іде за AC-VENDOR-01…10 у попередньому тексті, а нове — «у наступному оновленні»; новий текст не підтягував (розбіжності з нашими рішеннями — #43 і #44, див. «Не перевірено»)
- Питання PM (A): https://github.com/solomchaak/property-workflows-spec/issues/48, https://github.com/solomchaak/property-workflows-spec/issues/49, https://github.com/solomchaak/property-workflows-spec/issues/50 (питання колег #41–#47 не дублював; PM відповів на всі 10.11)
- PR задач «Реалізація» (B): https://github.com/ylehenkyi-qc/property-workflows/pull/45, https://github.com/ylehenkyi-qc/property-workflows/pull/46, https://github.com/ylehenkyi-qc/property-workflows/pull/47, https://github.com/ylehenkyi-qc/property-workflows/pull/48 (ADR 0004 — https://github.com/ylehenkyi-qc/property-workflows/pull/49)
- Тести відмов здатні впасти (B): AC-VENDOR-04, 06 → V5, V6, V7, V8, V13 KILLED (https://github.com/ylehenkyi-qc/property-workflows/pull/46); AC-VENDOR-07 → V16, V17, V18, V21 KILLED (https://github.com/ylehenkyi-qc/property-workflows/pull/47); AC-VENDOR-08 → V10, V11 KILLED (https://github.com/ylehenkyi-qc/property-workflows/pull/46), V22, V23, V24 KILLED (https://github.com/ylehenkyi-qc/property-workflows/pull/48); AC-VENDOR-09 → V1 KILLED (https://github.com/ylehenkyi-qc/property-workflows/pull/45). Мутації локальні (`scripts/mutation-check.mjs`), червоних прогонів CI для них немає (див. «Не перевірено»)
- Ворота й `db-deploy` на `main` (B): зелений quality https://github.com/ylehenkyi-qc/property-workflows/actions/runs/43710759477; зелений db-deploy (у прогонах `CI` із міграціями зрізу 3): https://github.com/ylehenkyi-qc/property-workflows/actions/runs/41852743332, https://github.com/ylehenkyi-qc/property-workflows/actions/runs/41854979649, https://github.com/ylehenkyi-qc/property-workflows/actions/runs/41857075638
- UAT — специфікації (C): https://github.com/ylehenkyi-qc/property-workflows/blob/a5302fa5a2788a97381b29701e884d78d6e65aad/tests/e2e/vendor-access.spec.ts (10 тестів, по одному на кожен AC зрізу 3)
- UAT — звіт на проді (C): https://github.com/ylehenkyi-qc/property-workflows/blob/a5302fa5a2788a97381b29701e884d78d6e65aad/docs/qa/uat/2026-11-06/report.md
- UAT — PR зі звітом і відео (C): https://github.com/ylehenkyi-qc/property-workflows/pull/51 (відео — вкладенням в описі)
- UAT — негативний контроль (C): https://github.com/ylehenkyi-qc/property-workflows/pull/51: `npm run uat:nc` — NC-1 і NC-3 → FAIL (R1), NC-2 → NEEDS-HUMAN (R3)
- QA proof pack (C): https://github.com/ylehenkyi-qc/property-workflows/blob/a5302fa5a2788a97381b29701e884d78d6e65aad/docs/qa/proof-pack.md
- Не перевірено (C): немає червоних прогонів CI для мутантів зрізу 3 (мутації проганялися локально); AC-DSYS-02 (зріз 2) не покриває частину «той самий макет»; розбіжності з відповідями PM від 10.11: #43 (діалог лише для останньої обов'язкової задачі, у нас на кожній) і #44/AC-VENDOR-13 (навігація «Runs» і «Profile», у нас лише «Runs») — це нові AC, поза приймання WS9
- Відхилення від PM (C): не надходило (станом на 15.11.2026 у репо немає issues «Відхилення від вимог», PM після 10.11 не залишав коментарів до PR)
- Рядки `docs/conformance.md` (D): https://github.com/ylehenkyi-qc/property-workflows/blob/a5302fa5a2788a97381b29701e884d78d6e65aad/docs/conformance.md
- Акаунти для нових ролей зрізу 3 (D): вендор — vendor1@example.test, vendor2@example.test, PR https://github.com/ylehenkyi-qc/property-workflows/pull/53
- Ретро «що взяти з фабрики» (D): https://github.com/ylehenkyi-qc/property-workflows/blob/a5302fa5a2788a97381b29701e884d78d6e65aad/docs/qa/retro-ws9.md

## Бонус

—
