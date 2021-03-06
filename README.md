## Дипломная работа профессии «Тестировщик ПО».

### Документы:
* [План автоматизации тестирования веб-cервиса покупки тура, взаимодействующего с СУБД и API Банка](https://github.com/kira9112/QAdiplom/blob/master/docs/Plan.md)
* [Отчет по итогам тестирования](https://github.com/kira9112/QAdiplom/blob/master/docs/Report.md)
* [Отчет по итогам автоматизации](https://github.com/kira9112/QAdiplom/blob/master/docs/Summary.md)
### Краткое описание приложения
Приложение представляет из себя веб-сервис "Путешествие дня".

Приложение предлагает купить тур по определённой цене с помощью двух способов:

* Обычная оплата по дебетовой карте
* Уникальная технология: выдача кредита по данным банковской карты

Само приложение не обрабатывает данные по картам, а пересылает их банковским сервисам:

* сервису платежей (далее - Payment Gate)
* кредитному сервису (далее - Credit Gate)

Приложение должно в собственной СУБД сохранять информацию о том, каким способом был совершён платёж и успешно ли он был совершён (при этом данные карт сохранять не допускается).
### Запуск тестов.

1.Cклонировать репозиторий git clone [по ссылке](https://github.com/kira9112/QAdiplom).

2.Открыть проект в IntelliJ IDEA.

3.В терминале введите команду docker-compose up -d.

4. Запуск БД.

Заявлена поддержка двух СУБД :

1. MySQL 
2. PostgreSQL

Для подключения к базе данных MySQL использовать :

На боковой вкладе IDEA Ultimate нажать вкладку Database->New->Data Sourse->MySQL. В открывшемся окне указать следующие данные:
* user - app
* password - pass
* database - app

После ввода данных нажать кнопку ОК.

Для подключения к базе данных PostgreSQL использовать:

На боковой вкладе IDEA Ultimate нажать вкладку Database->New->Data Sourse->PostgreSQL. В открывшемся окне указать следующие данные:
* user - app
* password - pass
* database - app

Параметры для подключения хранятся в файле docker-compose.yml.

5.В терминале введите команду java -jar artifacts/aqa-shop.jar .
Приложение запускается на порту 8080, по умолчанию используется БД MySQL. Убедитесь в готовности приложения по адресу : http://localhost:8080.

6.В терминале введите команду для запуска тестов: ./gradlew clean test.

7.При необходимости создания отчета тестирования в терминале введите команду:

   ./gradlew allureReport -генерация отчета после прохождения тестов или

   ./gradlew allureServe -генерация отчета и автоматическоеоткрытие в браузере по умолчанию