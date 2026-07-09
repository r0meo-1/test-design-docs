# test-design-docs — Manual QA Artifacts

[![Docs Check](https://github.com/r0meo-1/test-design-docs/actions/workflows/docs-check.yml/badge.svg)](https://github.com/r0meo-1/test-design-docs/actions/workflows/docs-check.yml)
![Manual QA](https://img.shields.io/badge/Manual%20QA-Test%20Design-0a7)
![Jira](https://img.shields.io/badge/Jira-YouTrack-0052CC)
![License](https://img.shields.io/badge/license-MIT-blue)

> Артефакты ручного тестирования для системы онлайн-бронирования туров:
> **тест-план, тест-стратегия, тест-кейсы, чек-листы, баг-репорты и матрица прослеживаемости**.
> Показывают подход к тест-дизайну, приоритизации и работе с дефектами.
>
> Часть QA-портфолио: **[r0meo1.ru](https://r0meo1.ru)** · автор — Роман Неклюдов (Middle QA Engineer).

## Содержание

| Раздел | Файлы |
|--------|-------|
| Планирование | [`test-plan.md`](test-plan.md), [`test-strategy.md`](test-strategy.md) |
| Тест-кейсы | [`test-cases/booking-flow.md`](test-cases/booking-flow.md), [`test-cases/payment-flow.md`](test-cases/payment-flow.md), [`test-cases/auth-and-access.md`](test-cases/auth-and-access.md) |
| Чек-листы | [`checklists/smoke.md`](checklists/smoke.md), [`checklists/regression.md`](checklists/regression.md), [`checklists/cross-browser.md`](checklists/cross-browser.md), [`checklists/release.md`](checklists/release.md) |
| Баг-репорты | [`bug-reports/`](bug-reports/) — примеры с severity/priority, шагами и SQL/логами |
| Прослеживаемость | [`traceability-matrix.md`](traceability-matrix.md) |

## Чем это полезно для оценки кандидата

- Видно владение **тест-дизайном** (классы эквивалентности, границы, таблицы решений, попарное).
- Понятна **приоритизация** (P1–P3, severity) и фокус на бизнес-рисках (деньги, данные, доступ).
- Баг-репорты — **воспроизводимые**, с фактическим/ожидаемым результатом и доказательствами.
- Связь требований, кейсов и автотестов через **матрицу прослеживаемости**.

## Связанные репозитории

- [`api-automation-tests`](https://github.com/r0meo-1/api-automation-tests) — авто-API-тесты (Postman + Newman + CI).
- [`data-quality-checks`](https://github.com/r0meo-1/data-quality-checks) — SQL-проверки целостности данных.

## Стек и навыки

`Manual QA` · `Test Design` · `Test Plan` · `Checklists` · `Bug Reports` · `Jira` · `YouTrack` · `Confluence` · `Agile` · `Scrum`

## Контакты

- Сайт / портфолио: **[r0meo1.ru](https://r0meo1.ru)**
- Telegram: [@r0meo1](https://t.me/r0meo1) · Email: r0meo1@ya.ru · GitHub: [r0meo-1](https://github.com/r0meo-1)

## Лицензия

[MIT](LICENSE)
