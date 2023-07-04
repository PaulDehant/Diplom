# Дипломный проект

## Дипломная работа по модулю «Автоматизация тестирования»

Дипломная работа представляет собой автоматизацию тестирования веб-сервиса по покупке тура. После заполнения определенной формы сервис заносит информацию о покупке тура (одним из двух способов) в собственную БД.

### Начало работы

На компьютере, где запускается проект, должно быть установлено ПО: Git, IntelliJ IDEA 2022 1.3, Docker Desktop.

1. Запустить настроенный Docker Desktop
2. Запустить IntelliJ IDEA 2022 1.3
3. Открыть новый проект. Склонировать диплом (https://github.com/PaulDehant/Diplom) с GitHub
4. Запустить БД (MySQL, PostgreSQL) и симулятор банковских сервисов, выполнив в терминале из корня проекта команду: docker-compose up. Дождаться пока поднимутся БД (вывод логов запуска прекратится).

### Запуск SUT, авто-тестов и генерация отчетов

5. В новой вкладке терминала из корня проекта выполнить одну из команд:

*С подключением к MySQL:*

java "-Dspring.datasource.url=jdbc:mysql://localhost:3306/db_mysql" -jar artifacts/aqa-shop.jar

*С подключением к PostgreSQL:*

java "-Dspring.datasource.url=jdbc:postgresql://localhost:5432/db_postgresql" -jar artifacts/aqa-shop.jar

6. В консоли (двойное нажатие Ctrl) выполнить одну из команд в зависимости от выбранной БД

*С подключением к MySQL:*

./gradlew clean test "-Ddb.url=jdbc:mysql://localhost:3306/db_mysql"

*С подключением к PostgreSQL:*

./gradlew clean test "-Ddb.url=jdbc:postgresql://localhost:5432/db_postgresql"

7. Создаем отчёт Allure:

.\gradlew allureServe

8. Остановить приложение - Ctrl+C


9. Для остановки работы выполнить команду:
   docker-compose down

### Документация проекта:
[1.Задание к диплому](https://github.com/PaulDehant/Diplom/blob/main/docs/Plan.md)  
[2.План автоматизации](https://github.com/Pauldehant/Diplom/docs/Plan.md)  
[3.Отчет по итогам тестирования](https://github.com/PaulDehant/Diplom/blob/main/docs/Report.md)
[4.Отчет по итогам автоматизации](https://github.com/PaulDehant/Diplom/blob/main/docs/Summary.md)