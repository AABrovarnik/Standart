# Архитектурные стандарты, паттерны и антипаттерны (обзор)

Дата актуализации: 2026-11-03

## Принцип ранжирования источников

- `tier`: `A` (normative/authoritative), `B` (method/canonical practice), `C` (evidence/empirical), `D` (contextual/secondary)
- `importance`: `high` / `medium` / `supporting`
- `usage`: `policy` / `architecture-review` / `delivery` / `training`
- `scope`: `org` / `system` / `team` / `code`

## Карта источников по рангам

| Блок | Источник | tier | importance | usage | scope |
|---|---|---|---|---|---|
| Архитектурные стандарты | ISO/IEC/IEEE 42010 | A | high | policy | org |
| Архитектурные стандарты | ISO/IEC 25010 | A | high | policy | org |
| Cloud framework | AWS Well-Architected | A | high | architecture-review | system |
| Cloud framework | Google Cloud Well-Architected | A | high | architecture-review | system |
| Cloud patterns | Azure Architecture Center (patterns/antipatterns) | B | high | delivery | system |
| Документирование | C4 model | B | high | architecture-review | system |
| Документирование | arc42 | B | high | delivery | team |
| Документирование | ADR templates | B | high | delivery | team |
| Оценка компромиссов | ATAM (SEI) | B | high | architecture-review | system |
| Паттерны | GoF (Design Patterns, 1994) | B | high | training | code |
| Паттерны | Fowler EAA Catalog | B | high | delivery | system |
| Паттерны | Enterprise Integration Patterns | B | high | delivery | system |
| Паттерны | Microservices.io pattern language | B | medium | delivery | system |
| Антипаттерны | AntiPatterns (Brown et al., 1998) | D | medium | training | team |
| Антипаттерны | Big Ball of Mud | D | medium | architecture-review | system |
| Антипаттерны | Microservices anti-patterns taxonomy (arXiv/EuroPLoP) | C | medium | architecture-review | system |


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

## 7) Каталог: паттерн -> когда применять -> антипаттерн -> сигнал деградации -> метрика контроля

Ниже — практический каталог для архитектурных ревью и еженедельного архитектурного контроля.

### 7.1 Каталог архитектурных и интеграционных решений

| Паттерн | Когда применять | Типичный антипаттерн | Сигнал деградации | Метрика контроля |
|---|---|---|---|---|
| Layers (слоистая архитектура) | Бизнес-приложения с чётким разделением UI/Domain/Data | Big Ball of Mud, bypass слоёв | Модули обращаются к БД в обход доменного слоя | Доля межслойных нарушений (static analysis), число bypass-импортов |
| Hexagonal / Ports & Adapters | Нужна изоляция домена от инфраструктуры и удобная тестируемость | Framework-centric core | Домен зависит от web/ORM SDK | Процент доменных модулей без внешних инфраструктурных импортов |
| API Gateway | Много клиентских входов и нужен единый edge-контур | Shared Everything Endpoint / chatty clients | Клиент ходит в десятки сервисов напрямую | Среднее число upstream-call на клиентский сценарий |
| Event-Driven + Pub/Sub | Слабосвязанные процессы, асинхронная интеграция, высокая эластичность | Temporal coupling via sync chains | Сервисы блокируются друг на друге по sync-вызовам | P95 end-to-end latency процесса, доля async-шагов |
| Saga (оркестрация/хореография) | Кросс-сервисные бизнес-транзакции без 2PC | Distributed transaction wishful thinking | Невозможность консистентно откатить шаги | Процент бизнес-операций с компенсирующими действиями |
| Circuit Breaker + Retry (bounded) | Внешние/нестабильные зависимости | Retry Storm | Лавинообразный рост повторов при деградации dependency | Retry rate, open-circuit rate, error budget burn |
| CQRS (где оправдано) | Высокая нагрузка чтения/записи и разный профиль оптимизации | Premature CQRS | Усложнение модели без выигрыша по SLA | Улучшение read/write latency vs baseline, стоимость сопровождения |
| Caching (explicit TTL/invalidation) | Горячие чтения и дорогие вычисления/запросы | Cache-as-database / stale forever | Рост инцидентов из-за устаревших данных | Hit ratio, stale-read incidents, cache churn |
| Strangler Fig (эволюционная миграция) | Переход от монолита к сервисам по частям | Big-bang rewrite | Срок миграции растёт, value не поставляется итерациями | Lead time каждого среза миграции, % трафика через новый контур |
| Modular Monolith (осознанный старт) | Ранний этап продукта, ограниченная команда, высокая связность домена | Distributed Monolith | Сервисы деплоятся только вместе, общий release train | Independent deployability rate, число cross-service lockstep релизов |

### 7.2 Каталог design-level (GoF/OO) для командной практики

| Паттерн | Когда применять | Типичный антипаттерн | Сигнал деградации | Метрика контроля |
|---|---|---|---|---|
| Strategy | Много вариантов алгоритма с выбором во время выполнения | Switch explosion | Огромные `if/switch` по типам поведения | Cyclomatic complexity по модулю, число условных веток |
| Factory Method / Abstract Factory | Вариативное создание семейств объектов | `new` scattered everywhere | Конструирование размазано по бизнес-коду | Количество точек создания объектов вне фабрик |
| Adapter | Интеграция с внешним API/SDK без протечки в домен | Leaky abstraction | Доменные сервисы знают детали внешнего контракта | Число мест с прямым использованием внешних DTO |
| Facade | Упрощение сложной подсистемы | God Facade | Фасад разрастается в бизнес-оркестратор всего | Размер фасада (LOC/public methods), fan-in/fan-out |
| Observer / Pub-Sub | Реактивные расширения без жёсткой связанности | Hidden side-effects | Непредсказуемые цепочки обработчиков | Длина цепочки уведомлений, процент неявных сайд-эффектов |
| Decorator | Комбинируемое расширение поведения | Inheritance explosion | Глубокие иерархии ради мелких вариаций | Средняя глубина наследования, число декораторов на цепь |

### 7.3 Каталог антипаттернов для обязательного мониторинга

| Антипаттерн | Где чаще возникает | Ранний сигнал | Последствия | Контрмера / целевая метрика |
|---|---|---|---|---|
| Big Ball of Mud | Legacy/быстрый рост без архитектурных границ | Любой модуль меняется при любой задаче | Высокая стоимость изменений, ошибки при релизах | Архитектурные границы + ADR; снижение change-failure-rate |
| Distributed Monolith | Псевдо-микросервисы с жёсткой сцепкой | Совместные релизы “всех сервисов сразу” | Потеря автономности команд, инциденты интеграции | Ограничение sync-зависимостей; рост independent deployability |
| Golden Hammer | Одна технология “на всё” | Насильное применение выбранного стека к любому кейсу | Техдолг и неоптимальные решения | ADR с альтернативами; доля решений с сравнением вариантов |
| Shared Database (без границ владения) | Микросервисы и интеграции данных | Множественные сервисы пишут в одни таблицы | Ломкие релизы и скрытые контракты | Ownership per schema/table; число cross-service write конфликтов |
| Chatty Interface | Сервисные API без coarse-grained контрактов | Сценарий требует много сетевых hops | Латентность и нестабильность | Снижение hop count и P95 latency бизнес-сценария |
| Retry Storm | Неправильные ретраи при деградации зависимости | Пики повторов в аварии | Эскалация инцидента и перегрузка | Bounded retry + jitter + circuit breaker; retry/open-circuit rate |
| Hardcoded Secrets | Быстрые прототипы без секрет-менеджмента | Ключи в коде/конфигах/логах | Компрометация доступа | Secret scanning + vault; MTTR по secret-утечкам |

## 8) Как использовать каталог в регулярной работе

1. На дизайн-ревью выбирать **1-2 целевых паттерна** и **2-3 риск-метрики** из таблиц выше.  
2. На каждое значимое решение создавать **ADR** с альтернативами и последствиями.  
3. На еженедельном архитектурном синке отслеживать тренд метрик деградации.  
4. При ухудшении метрик запускать корректирующий план: refactoring backlog + owner + дедлайн.

## 9) Ролевой мониторинг: пороги Green/Yellow/Red

Пороговые значения ниже — стартовые ориентиры. Для зрелых команд их стоит калибровать по историческим данным.

### 9.1 CTO / Head of Engineering (портфельный уровень)

| Метрика | Green | Yellow | Red |
|---|---:|---:|---:|
| Change Failure Rate (доля релизов с инцидентом) | <= 10% | > 10% и <= 20% | > 20% |
| MTTR инцидентов (продукт/платформа) | <= 4 ч | > 4 ч и <= 24 ч | > 24 ч |
| Доля сервисов с актуальными ADR за 90 дней | >= 85% | >= 60% и < 85% | < 60% |
| Доля систем с owner + backup owner | >= 95% | >= 80% и < 95% | < 80% |
| Доля критичных систем с наблюдаемостью (SLI/SLO+алерты+runbook) | >= 90% | >= 70% и < 90% | < 70% |

### 9.2 Chief/Lead Architect (архитектурный уровень)

| Метрика | Green | Yellow | Red |
|---|---:|---:|---:|
| Доля решений, зафиксированных ADR до реализации | >= 80% | >= 50% и < 80% | < 50% |
| Open architecture risks старше 30 дней | <= 3 | 4-8 | > 8 |
| Нарушения архитектурных границ на релиз | <= 2 | 3-7 | > 7 |
| Independent deployability (сервисы, деплоимые независимо) | >= 80% | >= 60% и < 80% | < 60% |
| Доля доменов с явными контрактами API/Events (versioned) | >= 85% | >= 65% и < 85% | < 65% |

### 9.3 Engineering Manager / Team Lead (командный уровень)

| Метрика | Green | Yellow | Red |
|---|---:|---:|---:|
| PR cycle time (медиана, до merge) | <= 24 ч | > 24 ч и <= 72 ч | > 72 ч |
| Доля PR с покрытием тестами изменённого критичного пути | >= 90% | >= 70% и < 90% | < 70% |
| Reopen rate дефектов (повторное открытие) | <= 5% | > 5% и <= 12% | > 12% |
| Доля задач, закрытых без `NOT RUN` в валидации | >= 85% | >= 60% и < 85% | < 60% |
| Доля задач с соблюдённым DoD (без waiver) | >= 90% | >= 75% и < 90% | < 75% |

### 9.4 Platform / SRE Lead (эксплуатационный уровень)

| Метрика | Green | Yellow | Red |
|---|---:|---:|---:|
| Error budget burn (месячный, по критичным сервисам) | <= 80% | > 80% и <= 100% | > 100% |
| P1/P2 incidents на сервис в месяц | <= 1 | 2-3 | >= 4 |
| Доля сервисов с автоматическим rollback/feature flag | >= 85% | >= 60% и < 85% | < 60% |
| Change-induced latency regression (P95) | <= 5% | > 5% и <= 15% | > 15% |
| Доля алертов без runbook | <= 10% | > 10% и <= 25% | > 25% |

### 9.5 Security Lead / AppSec (безопасность)

| Метрика | Green | Yellow | Red |
|---|---:|---:|---:|
| Критические уязвимости, открытые > 7 дней | 0 | 1-2 | >= 3 |
| High уязвимости, открытые > 30 дней | <= 5 | 6-15 | > 15 |
| Доля репозиториев с secret scanning + dependency scanning в CI | >= 95% | >= 80% и < 95% | < 80% |
| Доля релизов с security sign-off (для критичных систем) | >= 95% | >= 80% и < 95% | < 80% |
| Доля инцидентов из-за misconfiguration/overprivilege | <= 5% | > 5% и <= 12% | > 12% |

### 9.6 Продуктовый владелец / Delivery Manager (продукт + delivery)

| Метрика | Green | Yellow | Red |
|---|---:|---:|---:|
| Predictability (выполнение квартального плана) | >= 85% | >= 65% и < 85% | < 65% |
| Доля фич с documented trade-offs (качество/скорость/стоимость) | >= 80% | >= 55% и < 80% | < 55% |
| Доля инцидентов, влияющих на клиентский путь после релиза | <= 8% | > 8% и <= 18% | > 18% |
| Время от фидбека до решения (triage lead time) | <= 3 дня | 4-10 дней | > 10 дней |

### 9.7 Как применять пороги

- Если метрика 2 периода подряд в **Yellow**, формировать корректирующий план с owner и сроком.
- Если метрика попала в **Red**, запускать обязательный architecture/security review и ограничение на дальнейшее масштабирование изменений до стабилизации.
- Все waiver по DoD/quality gates фиксировать отдельным ADR с датой истечения waiver.

## 10) Исторические нотации: где уместны сегодня (пример: цветовая нотация Питера Коуда)

### 10.1 Краткий вывод

Цветовая нотация Питера Коуда (Object Modeling in Color) **не исчезла**, но на 2026 год используется в основном **нишево**: как обучающая и эвристическая техника анализа домена, а не как массовый корпоративный стандарт архитектурной документации.

### 10.2 Когда уместно применять

- На старте доменного моделирования, когда нужно быстро классифицировать сущности и роли.
- В воркшопах discovery (особенно с бизнес-стейкхолдерами), где цвет помогает визуально выделить типы сущностей.
- Как вспомогательный слой к основным артефактам (C4/arc42/ADR), а не как их замена.

### 10.3 Когда лучше не делать основным стандартом

- Когда нужна строгая корпоративная трассируемость архитектуры (аудит, compliance, формальные ревью).
- Когда команда распределённая и требуется единый канонический формат документации между проектами.
- Когда необходимо прямое соответствие современным практикам cloud/platform governance.

### 10.4 Практическая рекомендация

Использовать нотацию Коуда как **дополнительную технику анализа**, а в качестве основных стандартов архитектурного контура фиксировать:

- C4 для визуализации структуры,
- arc42 для структуры документа,
- ADR для фиксации решений,
- Well-Architected/quality-frameworks для операционных и quality-гейтов.

### 10.5 Опорные источники

- Object Modeling in Color (обзор и архетипы): <https://en.wikipedia.org/wiki/Object_Modeling_in_Color>
- C4 (официальный сайт): <https://c4model.com/>
- arc42 reference: <https://docs.arc42.org/>
- ADR templates: <https://adr.github.io/adr-templates/>
