# Публикация в `AABrovarnik/Standart`

## 1) Рекомендуемый состав к публикации

- `VIBE_READY_DOD_MASTER.md`
- `SOURCES_ANNOTATED.md`
- `VIBE_READY_PACKAGE_README.md`
- (опционально) `VIBE_READY_DOD_STANDARD.md`
- (опционально) `VIBE_READY_DOD_LITE_VS_STRICT.md`

## 2) Быстрый сценарий (PowerShell)

```powershell
# 1. Клонировать целевой репозиторий
cd $HOME\Documents\Codex
git clone https://github.com/AABrovarnik/Standart.git

# 2. Скопировать подготовленные файлы
$src = "C:\Users\aabro\Documents\Codex\стандарт"
$dst = "C:\Users\aabro\Documents\Codex\Standart"
Copy-Item "$src\VIBE_READY_DOD_MASTER.md" "$dst\" -Force
Copy-Item "$src\SOURCES_ANNOTATED.md" "$dst\" -Force
Copy-Item "$src\VIBE_READY_PACKAGE_README.md" "$dst\" -Force
Copy-Item "$src\VIBE_READY_DOD_STANDARD.md" "$dst\" -Force
Copy-Item "$src\VIBE_READY_DOD_LITE_VS_STRICT.md" "$dst\" -Force

# 3. Закоммитить и запушить
cd $dst
git add .
git commit -m "Add Vibe-ready DoD standards and annotated sources"
git push origin main
```

## 3) Структура (опционально)

Если хотите более аккуратный вид:

- в корне оставить `VIBE_READY_DOD_MASTER.md` и `SOURCES_ANNOTATED.md`
- `VIBE_READY_DOD_STANDARD.md` и `VIBE_READY_DOD_LITE_VS_STRICT.md` перенести в `archive/`
