# Здача WS9

## Дані

- Роль: dev
- Команда: property-workflows
- GitHub-логін: yuriivynar
- Ваше репо: https://github.com/yuriivynar/property-workflows
- SHA: 74eb4a80a9c11b5503da6cd3ea618fa2a7c62cb2
- Репо вимог PM: https://github.com/solomchaak/property-workflows-spec
- Прод-URL: https://property-workflows-eta.vercel.app

## PM

—

## Розробник

### D0 — умова прийняття

- `/api/health`: https://property-workflows-eta.vercel.app/api/health — `"db":"ok"`, SHA = `main` (`74eb4a80a9c11b5503da6cd3ea618fa2a7c62cb2`)
- Зелений прогін `smoke` на `main`: https://github.com/yuriivynar/property-workflows/actions/runs/43721703887
- `accounts.zip` на SHA: https://github.com/yuriivynar/property-workflows/blob/74eb4a80a9c11b5503da6cd3ea618fa2a7c62cb2/accounts.zip
- Ролі тестових акаунтів: адміністратор — pm-admin@example.test; менеджер — pm-manager@example.test; вендор — pm-vendor@example.test. Паролі — лише в accounts.zip
- Версія `next`: next@16.4.3

### Зріз 3 звичайним способом

- AC зрізу 3: AC-VENDOR-01, AC-VENDOR-02, AC-VENDOR-03, AC-VENDOR-04, AC-VENDOR-05, AC-VENDOR-06, AC-VENDOR-07, AC-VENDOR-08, AC-VENDOR-09, AC-VENDOR-10, AC-VENDOR-11, AC-VENDOR-12, AC-VENDOR-13, AC-VENDOR-14, AC-VENDOR-15, AC-VENDOR-16, AC-VENDOR-17, AC-VENDOR-18, AC-TASK-19 (AC-VENDOR-07 і 08 — у редакції PM 10.11; AC-VENDOR-11…18 і AC-TASK-19 додано 10.11)
- `/requirements-sync` — PR «Оновлення вимог» (A): https://github.com/yuriivynar/property-workflows/pull/35
- Спека `add-vendor-assignees` і план — PR «Специфікація» (A): https://github.com/yuriivynar/property-workflows/pull/47, https://github.com/yuriivynar/property-workflows/pull/49, https://github.com/yuriivynar/property-workflows/pull/62
- Після уточнень PM (A): `/requirements-sync` 2026-11-10 — https://github.com/yuriivynar/property-workflows/pull/63; зміна специфікації `clarify-vendor-work` (MODIFIED AC-VENDOR-07/08, ADDED AC-VENDOR-11…18, AC-TASK-19) — https://github.com/yuriivynar/property-workflows/pull/64; план `impl-clarify-vendor-work` — https://github.com/yuriivynar/property-workflows/pull/65
- Питання PM (A): https://github.com/solomchaak/property-workflows-spec/issues/41, https://github.com/solomchaak/property-workflows-spec/issues/42, https://github.com/solomchaak/property-workflows-spec/issues/43, https://github.com/solomchaak/property-workflows-spec/issues/44
- PR задач «Реалізація» (B): https://github.com/yuriivynar/property-workflows/pull/50, https://github.com/yuriivynar/property-workflows/pull/54, https://github.com/yuriivynar/property-workflows/pull/55, https://github.com/yuriivynar/property-workflows/pull/56, https://github.com/yuriivynar/property-workflows/pull/66, https://github.com/yuriivynar/property-workflows/pull/67, https://github.com/yuriivynar/property-workflows/pull/68, https://github.com/yuriivynar/property-workflows/pull/70, https://github.com/yuriivynar/property-workflows/pull/74, https://github.com/yuriivynar/property-workflows/pull/76; за рев'ю здачі WS9 — https://github.com/yuriivynar/property-workflows/pull/77 (мутант E07, mutation:sql у CI, повтор Chromium), https://github.com/yuriivynar/property-workflows/pull/78 (UAT-докази) (відповіді на кожну знахідку CodeRabbit — у самому PR); оновлення вигляду (поведінка й тексти AC без змін): https://github.com/yuriivynar/property-workflows/pull/53, https://github.com/yuriivynar/property-workflows/pull/69, https://github.com/yuriivynar/property-workflows/pull/71, https://github.com/yuriivynar/property-workflows/pull/72, https://github.com/yuriivynar/property-workflows/pull/73
- Тести відмов здатні впасти (B): AC-VENDOR-02 → V02; AC-VENDOR-03 → V03; AC-VENDOR-04 → V04; AC-VENDOR-06 → V06; AC-VENDOR-07 → V07; AC-VENDOR-08 → V08 і TS-V14; AC-VENDOR-09 → V09 (SQL-мутанти, вивід — https://github.com/yuriivynar/property-workflows/pull/54); AC-VENDOR-14 → TS-V14, AC-VENDOR-15 → TS-V15 (https://github.com/yuriivynar/property-workflows/pull/66); AC-VENDOR-12 → V12, AC-VENDOR-13 → TS-V13 (https://github.com/yuriivynar/property-workflows/pull/67); AC-VENDOR-17 → V04 і V06, AC-VENDOR-18 → V18 і V18P (https://github.com/yuriivynar/property-workflows/pull/68); AC-TASK-19 і AC-VENDOR-16 → T19 (https://github.com/yuriivynar/property-workflows/pull/70). Усі KILLED; список — https://github.com/yuriivynar/property-workflows/blob/74eb4a80a9c11b5503da6cd3ea618fa2a7c62cb2/scripts/mutants.mjs
- Ворота й `db-deploy` на `main` (B): CI (зокрема fallow audit і доменна підлога покриття) https://github.com/yuriivynar/property-workflows/actions/runs/43721662300; quality (зокрема «Мутанти: SQL-правила» — повний `npm run mutation:sql`, після рев'ю WS9) https://github.com/yuriivynar/property-workflows/actions/runs/43721662253; e2e (обов'язкова перевірка `main` з 15.11) https://github.com/yuriivynar/property-workflows/actions/runs/43721662307; db-deploy (злиття міграції зрізу 3) https://github.com/yuriivynar/property-workflows/actions/runs/41470765337
- UAT — специфікації (C): https://github.com/yuriivynar/property-workflows/blob/74eb4a80a9c11b5503da6cd3ea618fa2a7c62cb2/tests/e2e/vendor-assign.spec.ts, https://github.com/yuriivynar/property-workflows/blob/74eb4a80a9c11b5503da6cd3ea618fa2a7c62cb2/tests/e2e/vendor-runs.spec.ts, https://github.com/yuriivynar/property-workflows/blob/74eb4a80a9c11b5503da6cd3ea618fa2a7c62cb2/tests/e2e/vendor-forbidden.spec.ts, https://github.com/yuriivynar/property-workflows/blob/74eb4a80a9c11b5503da6cd3ea618fa2a7c62cb2/tests/e2e/vendor-direct-reads.spec.ts, https://github.com/yuriivynar/property-workflows/blob/74eb4a80a9c11b5503da6cd3ea618fa2a7c62cb2/tests/e2e/optional-after-completed.spec.ts
- UAT — звіт на проді (C): https://github.com/yuriivynar/property-workflows/blob/74eb4a80a9c11b5503da6cd3ea618fa2a7c62cb2/docs/qa/uat/2026-11-15/report.md (22 з 22 PASS, 15.11 після рев'ю WS9: «Дано» AC-TASK-19 і AC-VENDOR-09 — фікстурою; код тестів `8e01350`, застосунок `main @ 2a2e6c8` — #77 і #78 застосунку не змінювали); попередній прогін 11.11 — https://github.com/yuriivynar/property-workflows/blob/74eb4a80a9c11b5503da6cd3ea618fa2a7c62cb2/docs/qa/uat/2026-11-11/report.md
- UAT — PR зі звітом і відео (C): https://github.com/yuriivynar/property-workflows/pull/78 (прогін 15.11), https://github.com/yuriivynar/property-workflows/pull/75 (відео AC-VENDOR-07, 08, 11…18, AC-TASK-19 — вкладенням в описі), https://github.com/yuriivynar/property-workflows/pull/60 (відео AC-VENDOR-01…10, прогін 09.11)
- UAT — негативний контроль (C): https://github.com/yuriivynar/property-workflows/blob/74eb4a80a9c11b5503da6cd3ea618fa2a7c62cb2/docs/qa/uat/2026-11-15-nc/report.md — NC-1 → FAIL (R1), NC-2 → NEEDS-HUMAN (R3), з чистого коміту `a513a1c`, кадри в git; PR https://github.com/yuriivynar/property-workflows/pull/78
- QA proof pack (C): https://github.com/yuriivynar/property-workflows/blob/74eb4a80a9c11b5503da6cd3ea618fa2a7c62cb2/docs/qa/proof-pack.md (попередній, до уточнень PM, — https://github.com/yuriivynar/property-workflows/blob/74eb4a80a9c11b5503da6cd3ea618fa2a7c62cb2/docs/qa/proof-pack-ws9-slice3.md)
- Не перевірено (C): AC-VENDOR-09 — лише назва шаблону в «Дано» (синтетична копія задач «Tenant move-in» з поточною версією 1, бо назва унікальна — AC-EDITOR-24); SQL-мутанти для не-відмов AC-VENDOR-01, 05, 10, 11, 16; таблиця запусків на телефоні для читачів екрана (VoiceOver/NVDA не перевірено); CI `e2e` для PR #73 і #74 не стартував через збій раннерів GitHub (заміна — прогін на preview і на проді; тепер `e2e` — обов'язкова перевірка, а встановлення Chromium має три спроби)
- Відхилення від PM (C): не надходило
- Рядки `docs/conformance.md` (D): https://github.com/yuriivynar/property-workflows/blob/74eb4a80a9c11b5503da6cd3ea618fa2a7c62cb2/docs/conformance.md (86 з 86 AC «реалізовано»)
- Акаунти для нових ролей зрізу 3 (D): вендор — pm-vendor@example.test, https://github.com/yuriivynar/property-workflows/pull/51
- Ретро «що взяти з фабрики» (D): https://github.com/yuriivynar/property-workflows/blob/74eb4a80a9c11b5503da6cd3ea618fa2a7c62cb2/docs/qa/retro-ws9.md

## Бонус

Частковий прогін: фабрика реалізувала **3 AC зрізу 3 з 10** — AC-VENDOR-01, AC-VENDOR-02, AC-VENDOR-09 (задача `vendor-core`). AC-VENDOR-03…08 і 10 фабриці не давали — бракувало часу на задачі, червоні тести й приховані сценарії до них.

- Двійник: https://github.com/yuriivynar/property-workflows-factory (з тегу `ws9-base`, свої Supabase і Vercel), прод — https://property-workflows-factory-eight.vercel.app, `/api/health` — SHA `main`, `"db":"ok"`
- Червоні тести, адаптер і специфікація до прогону: коміти `9bae7d3`, `f901f23`, `628afc8` (специфікацію #47 перенесено людиною: `openspec/**` для будівельника захищене)
- Прогони фабрики (Sonnet, будівельник і рецензент): `run-20261115114018-e115fd` — `needs-human`, $0,62 (ORPHAN у `ac-coverage`: двійник створено до специфікації — вада підготовки); `run-20261115115900-80778e` — `needs-human`, $0,44 (приховані сценарії 0/7 через нестачу пам'яті оцінювача на Windows; відтворено вручну — 7/7 з `--maxWorkers=2`, оцінювач виправлено); `run-20261115123312-830d76` — **released** з 2-ї спроби, $0,39: видимі тести 122, повтор, приховані сценарії 7/7, рев'ю без зауважень, мутації n/a. Разом $1,44
- Автозлиття з міграцією: https://github.com/yuriivynar/property-workflows-factory/pull/2 (proof pack фабрики — в описі; `deliver` → злиття за 2 хв після обов'язкових `spec`, `app`, `conformance`, `db-check`; `db-deploy` — success)
- UAT на проді двійника: AC-VENDOR-01 — PASS, AC-VENDOR-02 — PASS, AC-VENDOR-09 — FAIL за специфікацією UAT (рядок перевіряє «Your tasks: 0 of 2 done» — видимий результат AC-VENDOR-03, поза задачею фабрики); «Тоді» AC-VENDOR-09 перевірено напряму на базі двійника — PASS (`LAUNCH_NOT_ALLOWED`, INSERT → 42501, запусків не додалось). Звіт — https://github.com/yuriivynar/property-workflows-factory/blob/main/docs/qa/uat/2026-11-15-factory/report.md
- Звіт порівняння «звичайно проти фабрики»: https://github.com/yuriivynar/property-workflows-factory/blob/main/docs/qa/factory-comparison.md — обсяг (#50: 25 файлів, міграція 358 рядків для 10 AC; фабрика: 3 файли, міграція 68 рядків для 3 AC), час і вартість, що ворота не спіймали (матрицю не оновлено, крихка заміна тексту `launch_run` у міграції, SQL-правила не мутовано), висновки
- PR зі звітами: https://github.com/yuriivynar/property-workflows-factory/pull/3
