# План Team Leader

> Схема репозитория: **master** — каркас (скилы, шаблоны контекста, `config.yaml`), общий для
> всех. Отдельные **ветки по стеку** (`python` / `javascript` / `java`) — уже с заполненным
> `02-engineering-standards.md` и стеком в реализации. Всё это готовится один раз заранее (см.
> "Подготовка репозитория" ниже) — тебе как лиду команды в день обучения нужно только выбрать
> стек и переключиться.

## День обучения — что делаешь

1. Выбираешь стек команды: `python` / `javascript` / `java`.
2. Клонируешь репозиторий:
```
git clone <url>
```
3. Переключаешься на ветку своего стека:
```
git checkout python   # или javascript / java
```
4. Ставишь зависимости под стек (`npm install` / `pip install -r requirements.txt` / `mvn
   install` — что актуально, это не коммитится в git, отдельный шаг).
5. Дальше — по `role-playbooks.md`, начиная с Этапа 1.

## Подготовка репозитория (один раз, до обучения)

- [ ] `master` — каркас: skills (`openspec-intent` и что ещё нужно), `openspec/context/`
      (`00-start-here.md`, `01-architecture.md` — общие, без стека), `openspec/config.yaml`
      (с плейсхолдером `Продукт:`).
- [ ] Ветка `python` от master + `02-engineering-standards.md` под Python/FastAPI/Jinja2.
- [ ] Ветка `javascript` от master + `02-engineering-standards.md` под Node/Express/EJS.
- [ ] Ветка `java` от master + `02-engineering-standards.md` под Java/Spring Boot/Thymeleaf.

Готовое содержимое под каждую ветку уже есть в `claude-dropbox/openspec-sdd/teams/<стек>/` —
переносишь оттуда.
