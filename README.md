# Дипломный проект профессии «Тестировщик ПО»

Дипломный проект представляет собой автоматизацию тестирования сервиса, взаимодействующего с СУБД и API Банка.

---

> ### Описание приложения

Приложение представляет из себя веб-сервис "Путешествие дня".

Приложение предлагает купить тур по определённой цене двумя способами:
1. Обычная оплата по дебетовой карте
2. Уникальная технология: выдача кредита по данным банковской карты

Само приложение не обрабатывает данные по картам, а пересылает их банковским сервисам:
* сервису платежей (далее - Payment Gate)
* кредитному сервису (далее - Credit Gate)

Приложение должно в собственной СУБД сохранять информацию о том, каким способом был совершён платёж и успешно ли он был совершён (при этом данные карт сохранять не допускается).

> ### Prerequisites

Перед началом работы с проектом убедитесь, что у вас установлены следующие инструменты:
* IntelliJ IDEA
* JDK11
* GIT
* Docker & Docker Desktop
* Allure Report


> ### Инструкция по запуску

1. Склонируйте репозиторий `git clone`
2. Запустите Docker Desktop
3. Запустите контейнеры в терминале IntelliJ Idea, в котором разворачиваются базы данных  `docker-compose up -d --force-recreate`
4. Запустите SUT командой :
    * для использования Postgres: `java "-Dspring.datasource.url=jdbc:postgresql://localhost:5432/TBank" -jar aqa-shop.jar`
    * для использования MySQL: `java "-Dspring.datasource.url=jdbc:mysql://localhost:3306/TBank" -jar aqa-shop.jar`

      (Приложение запускается на порту 8080 URL : http://localhost:8080/)

5. Запустите тесты командой:
    * при работе с postgres: `./gradlew clean test -Ddb.url=jdbc:postgresql://localhost:5432/TBank`
    * при работе с mySql: `./gradlew clean test -Ddb.url=jdbc:mysql://localhost:3306/TBank`

6. Запустите репортинг Allure командой `./gradlew allureServe` для открытия отчёта в браузере
7. Завершите работу приложения, выполнив команду в терминале IDEA:
    * **Ctrl+C**
8. Остановите контейнеры, выполнив команду в терминале IDEA:
    * **docker-compose down**
>### Документация проекта

<details>
<summary>Ссылки на документацию</summary>

* [Планирование автоматизации](https://github.com/Sizova-QA88/Diplom-QA/blob/main/docs/Plan.md)
* [Отчёт по итогам тестирования](https://github.com/Sizova-QA88/Diplom-QA/blob/main/docs/Report.md)
* [Отчёт по итогам автоматизации](https://github.com/Sizova-QA88/Diplom-QA/blob/main/docs/Summary.md)
</details>