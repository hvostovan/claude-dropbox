---
owner: Тимлид
updated: [ГГГГ-ММ-ДД]
---
# Engineering Standards
Стек: Node.js 20+, Express + EJS (server-side шаблоны).
Стайл-гайд: eslint + prettier.

Запуск проверок:
- Тесты: npm test
- Линт: npx eslint .
- Сборка: не требуется, запуск напрямую через node server.js

Код готов, когда: npm test зелёный, eslint без ошибок, страницы рендерятся и формы
отправляются без клиентского JS.
