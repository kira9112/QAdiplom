### Запуск тестов.

1.Cклонировать репозиторий git clone по ссылке https://github.com/kira9112/QAdiplom

2.Открыть проект в IntelliJ IDEA.

3.Для подключения к базе данных MySQL использовать :

Database-New-Data Sourse-MySQL

Для подключения к базе данных PostgreSQL использовать:

Database-New-Data Sourse-PostgreSQL

Параметры для подключения хранятся в файле docker-compose.yml.

3.В терминале введите команду docker-compose up -d.

4.В терминале введите команду java -jar artifacts/aqa-shop.jar .
Приложение запускается на порту 8080, по умолчанию используется БД MySQL. Убедитесь в готовности приложения по адресу : http://localhost:8080.

5. В терминале введите команду для запуска тестов: ./gradlew clean test.