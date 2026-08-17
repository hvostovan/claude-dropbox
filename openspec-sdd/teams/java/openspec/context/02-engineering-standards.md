---
owner: Тимлид
updated: [ГГГГ-ММ-ДД]
---
# Engineering Standards
Стек: Java 21, Spring Boot (Spring Web + Thymeleaf), Maven.
Стайл-гайд: Google Java Style.

Запуск проверок:
- Тесты: mvn test
- Сборка/запуск: mvn spring-boot:run

Код готов, когда: mvn test зелёный, приложение поднимается через spring-boot:run, формы
отправляются без JS.
