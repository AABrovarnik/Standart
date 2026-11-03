# Vibe-ready Definition of Done (DoD)

Версия: 1.0  
Дата: 2026-11-03  
Язык стандарта: RU

## 1. Назначение

Этот документ задаёт минимальный стандарт качества для задач, выполненных с AI-ассистентами (vibe-разработка, agentic coding, AI-assisted development).

Цель стандарта: ускорять разработку без потери управляемости, безопасности и ответственности.

## 2. Область применения

Стандарт применяется ко всем задачам, где код/тесты/конфигурация/документация полностью или частично сгенерированы AI.

Если для конкретного проекта есть более строгие правила, приоритет у более строгих правил.

## 3. Обязательные принципы

1. **Человек несёт ответственность.**
   - У каждого AI-изменения есть назначенный владелец (owner).
   - AI не может быть финальным утверждающим лицом.

2. **Итеративная разработка вместо one-shot.**
   - Цикл обязателен: `сгенерировать -> проверить -> исправить -> перепроверить`.

3. **Явные границы задачи.**
   - Перед началом должны быть зафиксированы: scope, non-goals, acceptance criteria.

4. **Детерминированные гейты обязательны.**
   - Критичные требования должны быть в автоматических проверках (CI/hooks/policy), а не только в текстовых инструкциях.

5. **Минимально необходимые права.**
   - Агентам, ключам, токенам, сервисам и пайплайнам выдаются только нужные доступы.

## 4. Definition of Done (минимальный чеклист)

Задача считается **Done** только если выполнены все пункты:

- [ ] **Scope зафиксирован:** цель, границы, non-goals, критерии приёмки.
- [ ] **Контекст задан:** есть проектные инструкции для агента (как запускать/тестировать/что нельзя трогать).
- [ ] **Изменения трассируемы:** понятен список изменённых файлов и их назначение.
- [ ] **Код-ревью человеком проведено:** reviewer подтверждает корректность и поддерживаемость.
- [ ] **Технические проверки зелёные:** релевантные тесты + линт/типизация (если применимо).
- [ ] **Security-проверки зелёные:** secret scan + dependency scan + базовые secure coding проверки.
- [ ] **Риски зафиксированы:** известные ограничения, что не проверено, план дальнейшей валидации.
- [ ] **Документация обновлена:** инструкции по запуску/валидации/ограничениям актуальны.
- [ ] **Решение о релизе явно принято:** merge/release или осознанный перенос.

Если хотя бы один пункт не выполнен — статус **не Done** (`Blocked` или `Follow-up required`).

## 5. Гейты по стадиям

### 5.1 До генерации

- [ ] Задача достаточно узкая и проверяемая.
- [ ] Определены acceptance criteria и список «что не менять».
- [ ] Проверено, что в промпт не попадают секреты/PII без разрешённой политики.

### 5.2 После генерации

- [ ] Человек прочитал diff и понял логику изменений.
- [ ] Проверены edge-cases, ошибки, негативные сценарии.
- [ ] Нет небезопасных shortcuts (отключённая валидация, чрезмерные роли, hardcoded secrets).

### 5.3 Перед merge

- [ ] CI прошёл.
- [ ] Security-gates прошли.
- [ ] Есть явное одобрение назначенного reviewer.

### 5.4 Перед прод-выкаткой

- [ ] Есть rollback/feature flag план.
- [ ] Настроены наблюдаемость и алерты по изменённому участку.
- [ ] Назначен ответственный за post-release мониторинг.

## 6. Ролевые ожидания

### 6.1 Junior

- Даёт агенту узкие задачи по тикету.
- Не мержит AI-код без ревью старшего.
- Приложение доказательств проверки обязательно (логи тестов, скриншоты/выводы).

### 6.2 Middle

- Делит задачу на итерации.
- Проверяет архитектурные инварианты и обратную совместимость.
- Отвечает за полноту тестов и корректность миграций.

### 6.3 Senior/Lead

- Определяет guardrails (hooks, deny rules, policy checks).
- Утверждает высокорисковые изменения (auth, payments, secrets, infra).
- Контролирует метрики качества AI-изменений.

### 6.4 Security Champion / AppSec

- Поддерживает SAST/DAST/secret scanning/dependency scanning гейты.
- Проводит выборочный security review AI-изменений.
- Ведёт каталог повторяющихся уязвимостей и контрмер.

## 7. Красные флаги (запрещённые практики)

- Деплой AI-кода без human review.
- Широкие/админские доступы «чтобы быстрее работало».
- Отключение проверок в CI ради дедлайна.
- Отсутствие владельца изменения.
- Смешивание статуса «кажется работает» со статусом «проверено и безопасно».
- Авто-одобрение AI собственного результата без независимого reviewer.

## 8. Шаблон отчёта по задаче

Использовать в PR/чате/задаче:

```md
## Scope
- Что делаем:
- Что не делаем:
- Acceptance criteria:

## Changes
- Ключевые изменения:
- Затронутые модули:

## Validation
- Авто-проверки:
- Ручные проверки:
- NOT RUN:

## Security
- Secret scan:
- Dependency scan:
- Доп. проверки:

## Risks
- Остаточные риски:
- План снижения:

## Decision
- Статус: Done / Blocked / Follow-up
- Owner:
- Reviewer:
```

## 9. Минимальные метрики для команды

Рекомендуется отслеживать минимум:

- Доля AI-assisted задач от общего объёма изменений.
- Дефектность после merge (bug rate) для AI-assisted изменений.
- Доля security-замечаний в AI-assisted PR.
- Mean Time To Detect (MTTD) дефектов в AI-assisted изменениях.
- % задач, где все обязательные DoD-гейты пройдены с первого раза.

## 10. Источники (основа стандарта)

1. Martin Fowler — Vibe Coding: <https://martinfowler.com/bliki/VibeCoding.html>
2. Martin Fowler — The VibeSec Reckoning: <https://martinfowler.com/articles/vibesec-reckoning.html>
3. OpenAI Learn — Codex Best Practices: <https://learn.chatgpt.com/docs/learn/best-practices>
4. OpenAI Cookbook — Iterating Development Workflows with Codex: <https://developers.openai.com/cookbook/examples/codex/iterating-development-workflows-with-codex>
5. OpenAI PDF — How OpenAI uses Codex: <https://cdn.openai.com/pdf/6a2631dc-783e-479b-b1a4-af0cfbd38630/how-openai-uses-codex.pdf>
6. Anthropic — Claude Code Best Practices: <https://code.claude.com/docs/en/best-practices>
7. OWASP SAMM — Guidance for AI-Assisted Development: <https://owaspsamm.org/docs/guides/ai-assisted-development/>
8. OWASP Cheat Sheet — Secure Coding with AI: <https://cheatsheetseries.owasp.org/cheatsheets/Secure_Coding_with_AI_Cheat_Sheet.html>
9. OWASP AISVS Appendix C — AI for Code Generation: <https://github.com/OWASP/AISVS/blob/main/1.01/en/0x92-Appendix-C_AI_for_Code_Generation.md>
10. Microsoft VS Code — Best practices for using AI agents: <https://code.visualstudio.com/docs/agents/best-practices>
11. GitHub Docs — Responsible use of Copilot Agents: <https://docs.github.com/en/copilot/responsible-use/agents>
12. arXiv (2026) — Vibe Coding in Software Development: A Multivocal Literature Review: <https://arxiv.org/abs/2607.21652>

---

## 11. Правило по умолчанию для формата

Если явно не указано иное, результатные регламенты/чеклисты/стандарты в этой рабочей области оформляются как Markdown-файлы (`.md`).
