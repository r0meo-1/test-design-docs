# test-design-docs — бумага, которая спасает релизы

[![Docs Check](https://github.com/r0meo-1/test-design-docs/actions/workflows/docs-check.yml/badge.svg)](https://github.com/r0meo-1/test-design-docs/actions/workflows/docs-check.yml)
![Manual QA](https://img.shields.io/badge/Manual%20QA-Test%20Design-0a7)
![Jira](https://img.shields.io/badge/Jira-YouTrack-0052CC)
![License](https://img.shields.io/badge/license-MIT-blue)

> Автотесты крутые. Но без тест-дизайна вы просто автоматизируете хаос —  
> быстрее, дороже и с гордым бейджем «coverage 87%» над пропастью.

Артефакты **ручного тестирования** для системы онлайн-бронирования туров:  
план, стратегия, кейсы, чек-листы, баг-репорты, матрица прослеживаемости.

Часть QA-портфолио: **[r0meo1.ru](https://r0meo1.ru)** · Роман Неклюдов

---

## Содержание

| Раздел | Файлы |
|--------|-------|
| Планирование | [`test-plan.md`](test-plan.md), [`test-strategy.md`](test-strategy.md) |
| Тест-кейсы | [`test-cases/booking-flow.md`](test-cases/booking-flow.md), [`payment-flow.md`](test-cases/payment-flow.md), [`auth-and-access.md`](test-cases/auth-and-access.md) |
| Чек-листы | smoke / regression / cross-browser / release в [`checklists/`](checklists/) |
| Баг-репорты | [`bug-reports/`](bug-reports/) — severity, шаги, SQL/логи (не «ну оно сломалось») |
| Прослеживаемость | [`traceability-matrix.md`](traceability-matrix.md) — требование → кейс → автотест |

---

## Чем это полезно рекрутеру / тимлиду

- Видно **тест-дизайн**, а не «потыкал кнопки и написал LGTM»
- Есть **приоритеты** (P1–P3) и фокус на деньгах/данных/доступе
- Баги **воспроизводимы** (фактический / ожидаемый / доказательства)
- Матрица связывает требования, ручные кейсы и автоматизацию — меньше «а это кто-то тестировал?»

Техники: классы эквивалентности, границы, таблицы решений, pairwise.  
Не магия. Просто дисциплина с markdown.

---

## Связанные репозитории

- [`api-automation-tests`](https://github.com/r0meo-1/api-automation-tests) — когда кейсы решили работать без кофе
- [`data-quality-checks`](https://github.com/r0meo-1/data-quality-checks) — SQL-детектив после «успешного» API

---

## Стек и навыки

`Manual QA` · `Test Design` · `Test Plan` · `Checklists` · `Bug Reports` · `Jira` · `YouTrack` · `Agile`

## Контакты

- **[r0meo1.ru](https://r0meo1.ru)** · [@r0meo1](https://t.me/r0meo1) · r0meo1@ya.ru

## Лицензия

[MIT](LICENSE) — копируйте структуру, не копируйте баги в прод.
