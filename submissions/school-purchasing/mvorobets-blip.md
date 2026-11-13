# Здача WS9

## Дані

- Роль: dev
- Команда: school-purchasing
- GitHub-логін: mvorobets-blip
- Ваше репо: https://github.com/mvorobets-blip/school-purchasing
- SHA: d2148c00ceba8e1e6eb056e078589ba89727f576
- Репо вимог PM: https://github.com/ValiaBihun/2026-quitcode-dream-team
- Прод-URL: https://therapy-scheduling-ten.vercel.app

## PM

—

## Розробник

### D0 — умова прийняття

- `/api/health`: https://therapy-scheduling-ten.vercel.app/api/health — `"db":"ok"`, sha `d2148c00ceba8e1e6eb056e078589ba89727f576` (= `main`)
- Зелений прогін `smoke` на `main`: https://github.com/mvorobets-blip/school-purchasing/actions/runs/43442534693
- `accounts.zip` на SHA: https://github.com/mvorobets-blip/school-purchasing/blob/d2148c00ceba8e1e6eb056e078589ba89727f576/accounts.zip
- Ролі тестових акаунтів: (роль approver / requester рахує база: схвалювач хоча б одного відділу — approver) адміністратор (admin) — pm-admin@example.test, admin@example.test; схвалювач (approver) — approver-primary@example.test (лише «Primary School», «Марія» в AC зрізу 3), approver-office@example.test (лише «Office», «Петро» в AC зрізу 3); працівник (requester) — pm-requester@example.test, pm-approver@example.test (назва історична: не схвалює жодного відділу, тому база рахує requester; для схвалення — approver-primary / approver-office), member1@example.test, member2@example.test
- Версія `next`: next@16.4.3

### Зріз 3 звичайним способом

- AC зрізу 3: AC-DEC-01, AC-DEC-04, AC-DEC-06, AC-DEC-07, AC-HIST-01, AC-HIST-02, AC-HIST-06, AC-HIST-10, AC-LANG-09
- `/requirements-sync` — PR «Оновлення вимог» (A): https://github.com/mvorobets-blip/school-purchasing/pull/53
- Спека `add-<зріз3>` і план — PR «Специфікація» (A): https://github.com/mvorobets-blip/school-purchasing/pull/56 (спека `add-purchase-history`), https://github.com/mvorobets-blip/school-purchasing/pull/57 (план `impl-purchase-history`)
- Після уточнень PM (A): https://github.com/mvorobets-blip/school-purchasing/pull/55 (знімок 2026-11-06, відповіді на #73–#75), https://github.com/mvorobets-blip/school-purchasing/pull/64 (знімок 2026-11-10, відповідь на #76); тексти AC не змінено — зміни `clarify-*` не потрібно
- Питання PM (A): https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/73, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/74, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/75
- PR задач «Реалізація» (B): https://github.com/mvorobets-blip/school-purchasing/pull/58, https://github.com/mvorobets-blip/school-purchasing/pull/59, https://github.com/mvorobets-blip/school-purchasing/pull/60, https://github.com/mvorobets-blip/school-purchasing/pull/61, https://github.com/mvorobets-blip/school-purchasing/pull/63, https://github.com/mvorobets-blip/school-purchasing/pull/62 (UAT), https://github.com/mvorobets-blip/school-purchasing/pull/66 (`users:demo`: роль за правилом бази), https://github.com/mvorobets-blip/school-purchasing/pull/67 (зауваження PM з приймання: мутанти, повтор UAT, швидка відмова ролі), https://github.com/mvorobets-blip/school-purchasing/pull/68 (відгук WS8: правила ролей доводить база, мутанти S35–S42), https://github.com/mvorobets-blip/school-purchasing/pull/70 (знахідки `/code-review high` усього коду WS9: тести до коду, Stryker 100 %); докази й звіти — https://github.com/mvorobets-blip/school-purchasing/pull/65 (proof pack, archive плану), https://github.com/mvorobets-blip/school-purchasing/pull/69 (фінальний прогін UAT з `main`), https://github.com/mvorobets-blip/school-purchasing/pull/71 (proof pack за фінальною перевіркою, Stryker 128/128)
- Тести відмов здатні впасти (B): AC-DEC-06 → SQL-мутант S22 KILLED, https://github.com/mvorobets-blip/school-purchasing/pull/61; AC-HIST-10 → SQL-мутанти S15, S16 KILLED, https://github.com/mvorobets-blip/school-purchasing/pull/59; правила відмови AC-DEC-07 → S23–S27, S29 KILLED, https://github.com/mvorobets-blip/school-purchasing/pull/63; AC-DEC-01 → S18, S21 KILLED, https://github.com/mvorobets-blip/school-purchasing/pull/60; AC-DEC-04 → S33, S34 KILLED, відмови `decide_purchase` (чужий відділ, `NOT_PENDING`) → S30, S32 KILLED, https://github.com/mvorobets-blip/school-purchasing/pull/67 (усього `npm run mutation:sql` — 41 з 41 разом із S35–S42 для ролей зрізу 1, PR 68; результати в репо — https://github.com/mvorobets-blip/school-purchasing/blob/d2148c00ceba8e1e6eb056e078589ba89727f576/docs/qa/mutation/sql-2026-11-13.md)
- Ворота й `db-deploy` на `main` (B): зелений quality https://github.com/mvorobets-blip/school-purchasing/actions/runs/43442471201; зелений CI з job `db-deploy` (Apply migrations — success) https://github.com/mvorobets-blip/school-purchasing/actions/runs/43442470968
- UAT — специфікації (C): https://github.com/mvorobets-blip/school-purchasing/blob/d2148c00ceba8e1e6eb056e078589ba89727f576/tests/e2e/purchase-history.spec.ts (усі 9 AC зрізу 3)
- UAT — звіт на проді (C): фінальний прогін з `main` — https://github.com/mvorobets-blip/school-purchasing/blob/d2148c00ceba8e1e6eb056e078589ba89727f576/docs/qa/uat/2026-11-13-final/report.md (застосунок і тести — `main` @ `fd48a47`, злиття PR 70; від фінального `main` код не відрізняється — лише `docs/`; PASS 12 з 12: 9 AC зрізу 3 і повтор AC-FRM-08, 14, 15 зрізу 2); попередні — https://github.com/mvorobets-blip/school-purchasing/blob/d2148c00ceba8e1e6eb056e078589ba89727f576/docs/qa/uat/2026-11-10/report.md (PASS 12 з 12) і https://github.com/mvorobets-blip/school-purchasing/blob/d2148c00ceba8e1e6eb056e078589ba89727f576/docs/qa/uat/2026-11-13/report.md (з гілки PR 67: PASS 11, AC-DEC-06 NEEDS-HUMAN лише через мову — у фінальному прогоні PASS)
- UAT — PR зі звітом і відео (C): https://github.com/mvorobets-blip/school-purchasing/pull/62 (відео — https://github.com/mvorobets-blip/school-purchasing/pull/62#issuecomment-6777577345); повтор 13.11 — https://github.com/mvorobets-blip/school-purchasing/pull/67 (відео — https://github.com/mvorobets-blip/school-purchasing/pull/67#issuecomment-6849163322); фінальний прогін — https://github.com/mvorobets-blip/school-purchasing/pull/69 (відео всіх 12 AC — https://github.com/mvorobets-blip/school-purchasing/pull/69#issuecomment-6854837935)
- UAT — негативний контроль (C): https://github.com/mvorobets-blip/school-purchasing/pull/62 · https://github.com/mvorobets-blip/school-purchasing/blob/d2148c00ceba8e1e6eb056e078589ba89727f576/docs/qa/uat/2026-11-10/negative-controls/report.md — NC-1 → FAIL (R1), NC-2 → NEEDS-HUMAN (R3), NC-3 (AC-DEC-06) → FAIL (R1)
- QA proof pack (C): https://github.com/mvorobets-blip/school-purchasing/blob/d2148c00ceba8e1e6eb056e078589ba89727f576/docs/qa/proof-pack.md
- Не перевірено (C): кожен із 9 AC доведено тестом і UAT на проді (proof pack, «Фінальний прогін UAT»); не перевірено лише частини: (1) «в історії» з AC-LANG-09 — записів рішень у WS9 немає (відповідь PM на #75; список і сторінка заявки — перевірено); (2) буквальні `PUR-1` / `PUR-2` з AC-HIST-01 на непорожньому проді — доведено тестом бази на порожній базі, на проді — `PUR-n`, `PUR-(n+1)` (відповідь PM на #73); (3) прогалина в номерах після невдалого подання — наше тлумачення відповіді PM на #76 (зауваження PM 12); (4) причина повернення після повторного подання й подія «повернено» в історії — поза «Тоді» й поза WS9 (зауваження PM 13, відповідь PM на #75)
- Відхилення від PM (C): не надходило — приймання PM 12.11.2026: усі 9 AC прийнято з оцінкою 3, відхилень від вимог немає, https://github.com/mvorobets-blip/school-purchasing/pull/62#issuecomment-6825557810; 14 зауважень, що не знижують оцінку, — виправлено або пояснено в https://github.com/mvorobets-blip/school-purchasing/pull/67, таблиця в proof pack; відгук викладача на WS8 — https://github.com/mvorobets-blip/school-purchasing/pull/68 (розділ «Відгук викладача на WS8» у proof pack)
- Рядки `docs/conformance.md` (D): https://github.com/mvorobets-blip/school-purchasing/blob/d2148c00ceba8e1e6eb056e078589ba89727f576/docs/conformance.md (рядки 92–99 і 107 — усі 9 «реалізовано», з тестом UAT на проді)
- Акаунти для нових ролей зрізу 3 (D): нових ролей у зрізі 3 немає; нові акаунти схвалювачів відділів — схвалювач (approver) лише «Primary School» — approver-primary@example.test, схвалювач (approver) лише «Office» — approver-office@example.test; https://github.com/mvorobets-blip/school-purchasing/pull/62 (`supabase/demo-users.json`), https://github.com/mvorobets-blip/school-purchasing/pull/65 (`accounts.zip`), https://github.com/mvorobets-blip/school-purchasing/pull/66 (роль у `users:demo` — за правилом бази)
- Ретро «що взяти з фабрики» (D): https://github.com/mvorobets-blip/school-purchasing/blob/d2148c00ceba8e1e6eb056e078589ba89727f576/docs/qa/proof-pack.md#ретро-що-б-ми-взяли-з-фабрики-у-свій-звичайний-процес

## Бонус

—
