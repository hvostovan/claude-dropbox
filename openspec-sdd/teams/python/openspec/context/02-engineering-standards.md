---
owner: Тимлид
updated: [ГГГГ-ММ-ДД]
---
# Engineering Standards
Стек: Python 3.12, FastAPI + Jinja2Templates, Uvicorn.
Стайл-гайд: PEP8 + ruff.

Запуск проверок:
- Тесты: pytest
- Линт: ruff check .
- Сборка: не требуется, запуск напрямую через uvicorn main:app

Код готов, когда: pytest зелёный, ruff check без ошибок, страницы рендерятся и формы
отправляются без JS.
