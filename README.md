# Standart: Vibe-ready и архитектурные стандарты

Дата обновления: 2026-11-03

## Состав release-пакета

### Основные документы

1. **Vibe-ready DoD (master)**  
   Файл: `VIBE_READY_DOD_MASTER.md`  
   Назначение: единый стандарт Definition of Done для AI-assisted/vibe-разработки, включая режимы LITE и STRICT.

2. **Аннотированные источники по Vibe-ready DoD**  
   Файл: `SOURCES_ANNOTATED.md`  
   Назначение: список первоисточников с краткими аннотациями (100–300 слов) для обоснования стандарта.

3. **Архитектурные стандарты, паттерны и антипаттерны**  
   Файл: `ARCHITECTURE_STANDARDS_PATTERNS.md`  
   Назначение: обзор канонических архитектурных стандартов и каталогов паттернов/антипаттернов.

## Быстрая навигация

- [VIBE_READY_DOD_MASTER.md](./VIBE_READY_DOD_MASTER.md)
- [SOURCES_ANNOTATED.md](./SOURCES_ANNOTATED.md)
- [ARCHITECTURE_STANDARDS_PATTERNS.md](./ARCHITECTURE_STANDARDS_PATTERNS.md)

## Что внутри (кратко)

### VIBE_READY_DOD_MASTER.md
- Базовые принципы AI-assisted разработки.
- Обязательный DoD-чеклист.
- Stage gates: до генерации, после генерации, перед merge, перед продом.
- Роли и ответственность.
- Сравнение LITE (прототип) vs STRICT (production).

### SOURCES_ANNOTATED.md
- Ссылки на практики OpenAI/Anthropic/OWASP/Microsoft/GitHub/исследования.
- Краткие пояснения, как каждый источник применим в стандарте.

### ARCHITECTURE_STANDARDS_PATTERNS.md
- Архитектурные стандарты: ISO/IEC/IEEE 42010, ISO/IEC 25010, Well-Architected подходы.
- Документирование и ревью архитектуры: C4, arc42, ADR, ATAM.
- Каталоги паттернов: GoF, EAA, EIP, microservices pattern language.
- Антипаттерны: AntiPatterns, Big Ball of Mud, microservices/cloud anti-pattern каталоги.

## Архив

Рабочие промежуточные версии вынесены в `archive/`:

- `archive/VIBE_READY_DOD_STANDARD.md`
- `archive/VIBE_READY_DOD_LITE_VS_STRICT.md`
- `archive/VIBE_READY_PACKAGE_README.md`
- `archive/PUBLISH_TO_STANDART.md`

## Рекомендованный порядок чтения

1. `VIBE_READY_DOD_MASTER.md`  
2. `SOURCES_ANNOTATED.md`  
3. `ARCHITECTURE_STANDARDS_PATTERNS.md`

---

Если не указано иное, новые стандарты и регламенты в этом репозитории оформляются как Markdown-файлы (`.md`).
