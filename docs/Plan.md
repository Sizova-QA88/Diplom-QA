## Планирование автоматизации тестирования _"Путешествие дня - Марракэш"_

1. [Перечень автоматизируемых сценариев](#Перечень_автоматизируемых_сценариев)
2. [Перечень используемых инструментов с обоснованием выбора](#Перечень_используемых_инструментов_с_обоснованием_выбора)
3. [Перечень и описание возможных рисков при автоматизации](#Перечень_и_описание_возможных_рисков_приавтоматизации)
4. [Интервальная оценка с учётом рисков в часах](#Интервальная_оценка_с_учётом_рисков_в_часах)
5. [План сдачи работ: когда будут проведены автотесты, результаты их проведения и отчёт по автоматизации](#План_сдачи_работ_когда_будут_проведены_автотесты_результаты_их_проведения_и_отчёт_по_автоматизации)

________________

## 1. Перечень автоматизируемых сценариев <a name="перечень_автоматизируемых_сценариев"></a>

1. [Покупка с данными карты со статусом APPROVED](#покупка_с_данными_карты_со_статусом_APPROVED)
2. [Покупка с данными карты со статусом DECLINED](#покупка_с_данными_карты_со_статусом_DECLINED)
3. [Негативные сценарии](#негативные_сценарии)

#### <span style="color:blue">1. Покупка с данными карты со статусом APPROVED <a name="покупка_с_данными_карты_со_статусом_APPROVED"></a> </span>


#### I. *Оплата по карте.*

**Шаги**

1. Открыть [ссылку](http://localhost:8080/) на веб-сервис в браузере
2. Выбрать вкладку **купить** и заполнить данными:

- Поле "номер карты" заполнить данными карты со статусом APPROVED (4444 4444 4444 4441)
- Поле "месяц" заполнить данными от 1 до 12
- Поле "год" заполнить минимум на 1 год вперед от текущего года
- Поле "владелец" заполнить на латинице, например: Natalya Sizova
- Поле "CVV" заполнить тремя цифрами (например, 888)

**Ожидаемый результат:** Появляется всплывающее сообщение с текстом: "Успешно! Операция одобрена банком."


#### II. *Кредит по карте.*

**Шаги**

1. Открыть [ссылку](http://localhost:8080/) на веб-сервис в браузере
2. Выбрать вкладку **купить в кредит** и заполнить данными:

- Поле "номер карты" заполнить данными карты со статусом APPROVED (4444 4444 4444 4441)
- Поле "месяц" заполнить данными от 1 до 12
- Поле "год" заполнить минимум на 1 год вперед от текущего года
- Поле "владелец" заполнить на латинице, например: Natalya Sizova
- Поле "CVV" заполнить тремя цифрами (например, 888)

**Ожидаемый результат:** Появляется всплывающее сообщение с текстом: "Успешно! Операция одобрена банком."


_____________________

#### <span style="color:blue">2. Покупка с данными карты со статусом DECLINED <a name="покупка_с_данными_карты_со_статусом_DECLINED"></a></span>

#### I. *Оплата по карте.*

**Шаги**

1. Открыть [ссылку](http://localhost:8080/) на веб-сервис в браузере
2. Выбрать вкладку **купить** и заполнить данными:

- Поле "номер карты" заполнить данными карты со статусом DECLINED (4444 4444 4444 4442)
- Поле "месяц" заполнить данными от 1 до 12
- Поле "год" заполнить минимум на 1 год вперед от текущего года
- Поле "владелец" заполнить на латинице, например: Natalya Sizova
- Поле "CVV" заполнить тремя цифрами (например, 888)

**Ожидаемый результат:** Появляется всплывающее сообщение с текстом: "Ошибка! Банк отказал в проведении операции."


#### II. *Кредит по карте.*

1. Открыть [ссылку](http://localhost:8080/) на веб-сервис в браузере
2. Выбрать вкладку **купить в кредит** и заполнить данными:

- Поле "номер карты" заполнить данными карты со статусом DECLINED(4444 4444 4444 4442)
- Поле "месяц" заполнить данными от 1 до 12
- Поле "год" заполнить минимум на 1 год вперед от текущего года
- Поле "владелец" заполнить на латинице, например: Natalya Sizova
- Поле "CVV" заполнить тремя цифрами (например, 888)

**Ожидаемый результат:** Появляется всплывающее сообщение с текстом: "Ошибка! Банк отказал в проведении операции."

__________________________

#### <span style="color:blue">3. Негативные сценарии <a name="негативные_сценарии"></a></span>
###### ***Заполнение отдельных полей формы банковской карты невалидными данными, при этом все остальные поля заполняются валидными данными

### <span style="color:RosyBrown">_**<u>1. Поле "номер карты"</u>**_</span>

a. Оставить поле пустым

**ожидаемый результат:** форма не отправлена, поле *Номер карты* подсвечивается красным,
сообщение внизу <span style="color:red">**Неверный формат**</span>

---

b. Ввести в поле буквы

**ожидаемый результат:** поле не допускает ввода букв.

---

c. Ввести в поле спец.символы

**ожидаемый результат:** поле не допускает ввода спец.символов.

---
d. Ввести в поле более 16 цифр

**ожидаемый результат:** поле не допускает ввода цифр в количестве свыше 16.

---

e. Ввести в поле менее 16 цифр

**ожидаемый результат:** форма не отправлена, поле *Номер карты* подсвечивается красным,
сообщение внизу <span style="color:red">**Неверный формат**</span>

---

f. Ввести в поле номер карты, несуществующей в одобренном наборе.

**ожидаемый результат:** Появляется всплывающее сообщение с текстом: "Ошибка! Банк отказал в проведении операции."

---

### <span style="color:RosyBrown">_**<u>2. Поле "месяц"</u>**_</span>
a. Ввести в поле буквы

**ожидаемый результат:** поле не допускает ввода букв.

---

b. Ввести в поле число >12

**ожидаемый результат:** форма не отправлена, поле *Месяц* подсвечивается красным,
сообщение внизу <span style="color:red">**Неверно указан срок действия карты**</span>

---

c. Ввести в поле число 0

**ожидаемый результат:** форма не отправлена, поле *Месяц* подсвечивается красным,
сообщение внизу <span style="color:red">**Неверный формат**</span>

----

d. Ввести в поле число 00

**ожидаемый результат:** форма не отправлена, поле *Месяц* подсвечивается красным,
сообщение внизу <span style="color:red">**Неверный формат**</span>

---

e. Ввести в поле одну цифру (от 1 до 9)

**ожидаемый результат:** форма не отправлена, поле *Месяц* подсвечивается красным,
сообщение внизу <span style="color:red">**Неверный формат**</span>

---

f. Ввести в поле спец.символы

**ожидаемый результат:** поле не допускает ввода спец.символов.

---

g. Оставить поле пустым

**ожидаемый результат:** форма не отправлена, поле *Месяц* подсвечивается красным,
сообщение внизу <span style="color:red">**Неверный формат**</span>

---

### <span style="color:RosyBrown">_**<u>3. Поле "год"</u>**_</span>

a. Оставить поле пустым

**ожидаемый результат:** форма не отправлена, поле *Год* подсвечивается красным,
сообщение внизу <span style="color:red">**Неверный формат**</span>

---

b. Ввести в поле буквы

**ожидаемый результат:** поле не допускает ввода букв.

---

c. Ввести в поле спец.символы

**ожидаемый результат:** поле не допускает ввода спец.символов.

---

d. Ввести предыдущий год

**ожидаемый результат:** форма не отправлена, поле *Год* подсвечивается красным,
сообщение внизу <span style="color:red">**Истёк срок действия карты**</span>

---

e. Ввести в поле будущий год, более 5 лет

**ожидаемый результат:** форма не отправлена, поле *Месяц* подсвечивается красным,
сообщение внизу <span style="color:red">**Неверно указан срок действия карты**</span>

---

f. Ввести в поле 1 цифру

**ожидаемый результат:** форма не отправлена, поле *Год* подсвечивается красным,
сообщение внизу <span style="color:red">**Неверный формат**</span>

---

### <span style="color:RosyBrown">_**<u>4. Поле "владелец"</u>**_</span>

a. Оставить пустым

**ожидаемый результат:** форма не отправлена, поле *Владелец* подсвечивается красным,
сообщение внизу <span style="color:red">**Поле обязательно для заполнения**</span>

---


b. Ввести в поле имя на кириллице

**ожидаемый результат:** форма не отправлена, поле *Владелец* подсвечивается красным,
сообщение внизу <span style="color:red">**Неверный формат**</span>

---

c. Ввести в поле цифры

**ожидаемый результат:** поле не допускает ввода цифр. сообщение внизу <span style="color:red">**Неверный формат**</span>

---

d. Ввести в поле двойную фамилию через дефис

**ожидаемый результат:** форма отправлена, появляется всплывающее сообщение с текстом: "Успешно! Операция одобрена банком.".

---

e. Ввести в поле только спец.символы

**ожидаемый результат:** поле не допускает ввода спец.символов. сообщение внизу <span style="color:red">**Неверный формат**</span>


---

### <span style="color:RosyBrown">_**<u>5. Поле "CVV"</u>**_</span>

a. Оставить поле пустым

**ожидаемый результат:** форма не отправлена, поле *CVV* подсвечивается красным,
сообщение внизу <span style="color:red">**Неверный формат**</span>

---

b. Ввести в поле буквы

**ожидаемый результат:** поле не допускает ввода букв.

---

c. Ввести в поле более 3 цифр

**ожидаемый результат:** поле не допускает ввода цифр в количестве свыше 3-х .

---

d. Ввести в поле менее 3 цифр

**ожидаемый результат:** форма не отправлена, поле *CVV* подсвечивается красным,
сообщение внизу <span style="color:red">**Неверный формат**</span>

---

e. Ввести в поле спец.символы

**ожидаемый результат:** поле не допускает ввода спец.символов.
___________________

## 2. Перечень используемых инструментов с обоснованием выбора <a name="Перечень-используемых-инструментов-с-обоснованием-выбора"></a>

- **JUnit 5** - фреймворк для написания и запуска тестов.
- **Selenide** - фреймворк для автоматизированного тестирования веб-приложений.
- **Lombok** - библиотека для сокращения кода в классах и расширения функциональности языка Java.
- **Allure** - инструмент для создания отчетов о тестировании, который помогает визуализировать результаты тестов в удобном и наглядном формате.
- **Docker** - платформа для создания контейнеров с целью тестирования работы БД MySQL/Postgres.
- **dbutils** - утилита для работы с базой данных.
__________________


## 3. Перечень и описание возможных рисков при автоматизации <a name="перечень-и-описание-возможных-рисков-при-автоматизации"></a>

- Изменения в интерфейсе пользователя, влекущие за собой поломку существующих тестов.
- Сложность с производительностью при обработке больших объемов данных.
- Ошибки при взаимодействии с внешними системами.
- Ошибки сервера.
__________________
## 4. Интервальная оценка с учётом рисков в часах <a name="интервальная-оценка-с-учётом-рисков-в-часах"></a>

- Подготовка проекта, изучение тех.задания, установка программного обеспечения, запуск SUT - 5ч.
- Написание плана тестирования - 8ч.
- Написание тестов - от 24ч до 72ч.
- Написание отчетов о тестировании - 3ч.
- Написание отчетов об автоматизации - 2ч.
- Время на исключение форс-мажоров, исправление ошибок - 3ч.


**Общее время: от 45ч. до 93ч.**
_____________________

## 5. План сдачи работ: когда будут проведены автотесты, результаты их проведения и отчёт по автоматизации <a name="план-сдачи-работ-когда-будут-проведены-автотесты-результаты-их-проведения-и-отчёт-по-автоматизации"></a>

- Написание плана тестирования - 1 день после запуска SUT - 15.11.2024.
- Написание автотестов - от 3 до 7 дней после согласования плана тестирования - 15.11.2024 - 15.11.2024.
- Написание отчетов о тестировании и автоматизации - 1 день после написания автотестов - 15.11.2024 - 15.11.2024.

