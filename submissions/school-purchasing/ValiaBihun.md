# Здача WS9

## Дані

- Роль: pm
- Команда: school-purchasing
- GitHub-логін: ValiaBihun
- Ваше репо: https://github.com/ValiaBihun/2026-quitcode-dream-team
- SHA: 8f0fee554e7d6c50ba62e995aefda3eab7156eaa
- Репо вимог PM: https://github.com/ValiaBihun/2026-quitcode-dream-team
- Прод-URL: —

## PM

- Сховище вимог: issues
- Зріз 3: схвалювач частково схвалює чи повертає заявку, автор виправляє й подає знову; кожна заявка має номер, суми й історію рішень
- Вимоги зрізу 3: https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/63, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/64
- Питання, на які ви відповіли (A): https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/73, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/74, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/75, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/76
- Зміни вимог із журналом змін (A): https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/63#issuecomment-6661656033 (зріз скорочено до 4 AC), https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/64#issuecomment-6661644251 (зріз скорочено до 4 AC), https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/64#issuecomment-6682823017, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/64#issuecomment-6741155417, https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/49#issuecomment-6682859430

### Приймання зрізу 3 (трек B)

- Таблиця приймання PM (B): заповнено: вкладка school-purchasing, розробники @YarynaPankivv, @mvorobets-blip, @kdeineko-tech; AC зрізу 3: AC-DEC-01, AC-DEC-04, AC-DEC-06, AC-DEC-07, AC-HIST-01, AC-HIST-02, AC-HIST-06, AC-HIST-10, AC-LANG-09
- Відхилення від вимог (B): відхилень немає
- Звірка «вердикт агента ↔ запис» і «AC ↔ специфікація» (B): вердикт агента збігається із записом для всіх прийнятих AC. У браузері на проді перевірено всі 9 AC у @mvorobets-blip і по 3 AC (AC-DEC-06, AC-HIST-06, AC-HIST-10) у @YarynaPankivv і @kdeineko-tech; решту — за кадрами звіту UAT, кодом і тестами на базі. Розбіжності «AC ↔ специфікація»: у @kdeineko-tech «Тоді» в кроках UAT для AC-DEC-01 і AC-HIST-10 процитовано не повністю, а AC-HIST-10 перевірено дзеркально (схвалювач «Початкової школи» відкриває заявку «Офісу» замість навпаки); у @YarynaPankivv AC-HIST-01 у звіті процитовано дослівно з «PUR-1» і «PUR-2», а на проді перевірено пару PUR-n і PUR-(n+1), що відповідає моїй відповіді на питання https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/73; у @mvorobets-blip «Дано» AC-HIST-10 у тесті не містить історії рішень. Також помічено різні формати дати на сторінці заявки (запис історії й поле Created); на оцінку не вплинуло.
- Підпис у репо розробників (B): https://github.com/YarynaPankivv/school-purchasing/pull/75#issuecomment-6825883992, https://github.com/mvorobets-blip/school-purchasing/pull/62#issuecomment-6825557810, https://github.com/kdeineko-tech/school-purchasing/pull/70#issuecomment-6827375459
- Повторні перевірки (B): «Виправлено» в issues не надходило (оцінки 2–3, відхилень не було); зауваження до тестів і документів розробники виправляють у своїх PR, наприклад https://github.com/mvorobets-blip/school-purchasing/pull/67

### Зріз 4 для WS10 (трек C)

- Зріз 4: працівник вставляє вільний опис покупки, а AI пропонує заповнений рядок закупівлі, який він перевіряє перед поданням
- Вимога зрізу 4 (C): https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/71
- AC відмови й стану (C): AC-AI-02 (відмова: запит поза закупівлями), AC-AI-03 (стан: обробка), AC-AI-04 (стан: відповіді AI немає протягом 15 секунд)
- Golden cases (C): https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/70 — 10 кейсів; у WS10 діють кейси 1, 5, 6, 7, 8 і 9, кейси 2, 3, 4 і 10 позначено як наступна версію; складні — 5, 6 і 7 (межі правил), відмови — 8 і 9
- Roadmap (C): https://github.com/ValiaBihun/2026-quitcode-dream-team/issues/1#issuecomment-6849015310

## Розробник

—

## Бонус

—
