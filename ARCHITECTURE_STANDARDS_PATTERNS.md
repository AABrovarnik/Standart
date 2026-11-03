# Архитектурные стандарты, паттерны и антипаттерны (обзор)

Дата актуализации: 2026-11-03

## 1) Базовые архитектурные стандарты и фреймворки

### 1.1 ISO/IEC/IEEE 42010 (Architecture Description)
- Источник: <https://www.iso.org/standard/74393.html>
- Что это: международный стандарт описания архитектуры (Architecture Description).
- Практическая ценность: задаёт **как** документировать архитектуру, роли стейкхолдеров, представления (view/viewpoint), соответствия между решениями и требованиями.
- Когда применять: для системного архитектурного документа, архитектурного ревью, трассировки решений.

### 1.2 ISO/IEC 25010 (SQuaRE Product Quality Model)
- Источник: <https://www.iso.org/standard/78176.html>
- Что это: модель качества ПО/систем (характеристики качества продукта).
- Практическая ценность: помогает формулировать quality attributes (например, надежность, безопасность, сопровождаемость) как проверяемые требования.
- Когда применять: при постановке NFR и валидации архитектурных trade-off.

### 1.3 AWS Well-Architected Framework
- Источники:
  - <https://docs.aws.amazon.com/wellarchitected/latest/framework/definitions.html>
  - <https://wa.aws.amazon.com/index.en.html>
- Что это: набор best practices и вопросов самооценки архитектуры.
- Основа: 6 pillars (operational excellence, security, reliability, performance efficiency, cost optimization, sustainability).
- Когда применять: проектирование/аудит cloud-архитектур на AWS.

### 1.4 Google Cloud Well-Architected Framework
- Источник: <https://docs.cloud.google.com/architecture/framework>
- Что это: рекомендации для безопасной, эффективной, устойчивой, производительной и экономичной архитектуры в Google Cloud.
- Отметка актуальности страницы: last reviewed 2026-10-13 (на момент проверки).
- Когда применять: cloud-архитектуры и архитектурные ревью в GCP.

### 1.5 Azure Architecture Center (паттерны и антипаттерны)
- Источники:
  - Паттерны: <https://learn.microsoft.com/en-us/azure/architecture/patterns/>
  - Антипаттерны: <https://learn.microsoft.com/azure/architecture/antipatterns/>
- Что это: инженерный каталог проблем/решений + отдельный каталог типовых архитектурных ошибок.
- Когда применять: как практическую библиотеку шаблонов и чеклистов для design review.

## 2) Стандарты/подходы к документированию архитектуры

### 2.1 C4 Model
- Источник: <https://c4model.com/>
- Что это: модель визуализации архитектуры на 4 уровнях (Context, Container, Component, Code).
- Практическая ценность: резко улучшает читаемость архитектуры для разных аудиторий.

### 2.2 arc42
- Источники:
  - <https://arc42.org/>
  - <https://arc42.org/overview/>
  - <https://github.com/arc42/arc42-template>
- Что это: шаблон и метод структурирования архитектурной документации.
- Практическая ценность: снижает риск «архитектуры в голове одного человека».

### 2.3 ATAM (Architecture Tradeoff Analysis Method)
- Источник: <https://www.sei.cmu.edu/library/the-architecture-tradeoff-analysis-method/>
- Что это: метод анализа архитектурных компромиссов по quality attributes.
- Практическая ценность: формализует оценку рисков и конфликтов (например, security vs performance).

### 2.4 ADR (Architecture Decision Records)
- Источники:
  - <https://adr.github.io/adr-templates/>
  - <https://docs.aws.amazon.com/prescriptive-guidance/latest/architectural-decision-records/architectural-decision-records.html>
- Что это: легковесный формат фиксации архитектурных решений.
- Практическая ценность: сохраняет контекст, альтернативы и последствия решений.

## 3) Каталоги паттернов (по уровням)

### 3.1 Уровень design patterns (GoF)
- Источник (издатель): <https://www.pearson.com/en-us/subject-catalog/p/design-patterns-elements-of-reusable-object-oriented-software/P200000009480/9780201633610>
- Классика: 23 GoF-паттерна (creational, structural, behavioral).
- Смысл: переиспользуемые решения на уровне проектирования классов/объектов.

### 3.2 Уровень enterprise application patterns (Fowler)
- Источник: <https://www.martinfowler.com/eaaCatalog/>
- Примеры тем: layering, business logic, ORM/data mapping, session state.
- Смысл: шаблоны для бизнес-приложений и транзакционных систем.

### 3.3 Уровень integration patterns (EIP)
- Источник: <https://www.enterpriseintegrationpatterns.com/>
- Классика: паттерны маршрутизации, трансформации, обмена сообщениями.
- Смысл: проектирование интеграций и message-driven архитектур.

### 3.4 Уровень microservices patterns
- Источник: <https://microservices.io/patterns/>
- Смысл: pattern language для декомпозиции, данных, коммуникаций и операций в микросервисах.

## 4) Антипаттерны: канонические и практические источники

### 4.1 AntiPatterns (Brown et al.)
- Источник: <https://www.wiley.com/en-ca/antipatterns-refactoring-software-architectures-and-projects-in-crisis-p-9780471197133>
- Смысл: систематизация повторяющихся «ложно хороших» решений в архитектуре/разработке/управлении.

### 4.2 Big Ball of Mud
- Источники:
  - <https://www.laputan.org/mud/mud.html>
  - <https://www.informit.com/store/pattern-languages-of-program-design-4-9780201433043>
- Смысл: архитектурная деградация в систему без явной структуры.
- Практическое применение: ранняя диагностика эрозии архитектуры.

### 4.3 Microservices anti-patterns
- Источники:
  - <https://arxiv.org/abs/1908.04101>
  - <https://doi.org/10.1145/3424771.3424812>
- Смысл: каталог типовых ошибок внедрения микросервисов (в т.ч. distributed-monolith-подобные проблемы).

### 4.4 Cloud antipatterns (практика)
- Источник: <https://learn.microsoft.com/azure/architecture/antipatterns/>
- Смысл: набор распространённых ошибок масштабирования/производительности и способы исправления.

## 5) Рекомендуемый минимум для команды (быстрый старт)

1. Для описания архитектуры: **ISO 42010 + C4 + arc42**.  
2. Для фиксации решений: **ADR**.  
3. Для оценки компромиссов: **ATAM**.  
4. Для облака: **Well-Architected (AWS/GCP/Azure)**.  
5. Для решений на уровне кода/сервисов: **GoF + EAA + EIP + microservices pattern language**.  
6. Для профилактики деградации: **AntiPatterns + Big Ball of Mud + cloud/microservices anti-pattern каталоги**.

## 6) Замечание по TOGAF/ArchiMate

TOGAF и ArchiMate также являются широко используемыми enterprise-стандартами The Open Group, однако часть официальной библиотеки The Open Group требует SSO-доступа. При формальной стандартизации в компании рекомендуется фиксировать конкретную редакцию стандарта и дату проверки по официальному порталу The Open Group.
