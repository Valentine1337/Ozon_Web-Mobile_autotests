# Проект по автотестированию интернет-магазина [Ozon](https://www.ozon.ru/)
[<img alt="Ozon" height="100" src="https://raw.githubusercontent.com/Valentine1337/qa_guru_diplom_uiAndMobile/master/images/logo/Ozon.svg.png" width="500"/>](https://www.ozon.ru/)

## Содержание:

* [Технологии, используемые в данном проекте](#computer-технологии-используемые-в-данном-проекте)
* [Тест кейсы](#clipboard-тест-кейсы)
* [Сборка в Jenkins](#-сборка-в-jenkins)
* [Отчеты и информация о тестах в Allure report](#-отчеты-и-информация-о-тестах-в-allure-report)
* [Интеграция с AllureTestOps](#-интеграция-с-alluretestops)
* [Уведомления в Telegram](#-уведомления-в-telegram)
* [Пример аттачей](#movie_camera-пример-аттачей)

## :computer: Технологии, используемые в данном проекте

[<img alt="Java" height="50" src="https://raw.githubusercontent.com/Valentine1337/qa_guru_diplom_uiAndMobile/master/images/logo/Java.svg" width="50"/>](https://www.java.com/)
[<img alt="IDEA" height="50" src="https://raw.githubusercontent.com/Valentine1337/qa_guru_diplom_uiAndMobile/master/images/logo/Idea.svg" width="50"/>](https://www.jetbrains.com/idea/)
[<img alt="Appium" height="50" src="https://raw.githubusercontent.com/Valentine1337/qa_guru_diplom_uiAndMobile/master/images/logo/Appium.svg" width="50"/>](https://appium.io/)
[<img alt="Selenide" height="50" src="https://raw.githubusercontent.com/Valentine1337/qa_guru_diplom_uiAndMobile/master/images/logo/Selenide.svg" width="50"/>](https://ru.selenide.org/)
[<img alt="Selenoid" height="50" src="https://raw.githubusercontent.com/Valentine1337/qa_guru_diplom_uiAndMobile/master/images/logo/Selenoid.svg" width="50"/>](https://aerokube.com/selenoid/latest/)
[<img alt="Android" height="50" src="https://raw.githubusercontent.com/Valentine1337/qa_guru_diplom_uiAndMobile/master/images/logo/Android.svg" width="50"/>](https://developer.android.com/studio)
[<img alt="Browserstack" height="50" src="https://raw.githubusercontent.com/Valentine1337/qa_guru_diplom_uiAndMobile/master/images/logo/Browserstack.svg" width="50"/>](https://www.browserstack.com/)
[<img alt="Github" height="50" src="https://raw.githubusercontent.com/Valentine1337/qa_guru_diplom_uiAndMobile/master/images/logo/GitHub.svg" width="50"/>](https://github.com/)
[<img alt="JUnit 5" height="50" src="https://raw.githubusercontent.com/Valentine1337/qa_guru_diplom_uiAndMobile/master/images/logo/Junit5.svg" width="50"/>](https://junit.org/junit5/)
[<img alt="Gradle" height="50" src="https://raw.githubusercontent.com/Valentine1337/qa_guru_diplom_uiAndMobile/master/images/logo/Gradle.svg" width="50"/>](https://gradle.org/)
[<img alt="Allure" height="50" src="https://raw.githubusercontent.com/Valentine1337/qa_guru_diplom_uiAndMobile/master/images/logo/Allure.svg" width="50"/>](https://github.com/allure-framework/allure2)
[<img alt="Allure_EE" height="50" src="https://raw.githubusercontent.com/Valentine1337/qa_guru_diplom_uiAndMobile/master/images/logo/Allure_EE.svg" width="50"/>](https://qameta.io/)
[<img alt="Jenkins" height="50" src="https://raw.githubusercontent.com/Valentine1337/qa_guru_diplom_uiAndMobile/master/images/logo/Jenkins.svg" width="50"/>](https://www.jenkins.io/)

В данном проекте автотесты написаны на **Java** с использованием фреймворков для тестирования **Selenide**. Для сборки проекта в среде **IntelliJ IDEA** используется **Gradle**.
**JUnit5** задействован в качестве фреймворка модульного тестирования. Запуск тестов выполняется из **Jenkins**. **Selenoid** используется для запуска браузеров в контейнерах **Docker**.

**Browserstack** используется для запуска мобильных тестов, для запуска на эмуляторе используются **Android Studio** и **Appium**. **Allure Report**, **AllureTestOps** и **Telegram Bot** используются для визуализации результатов тестирования.

Применен архитектурный стиль **Page Object**.

## :clipboard: Тест кейсы

### Тест кейсы для UI web тестирования

✓ Добавление товара в избранное

✓ Добавление товара в корзину через поиск

✓ Добавление нескольких товаров в список сравнения

✓ Добавление подарочных сертификатов с разным номиналом

✓ Функция 'Узнать о снижении цены' в разделе подарочных сертификатов

✓ Подсказки 'Поддержка производителя' у подарочного сертификата

✓ Выпадающие меню в разделе 'Помощь'

✓ Поиск новостей в разделе 'Новости'

✓ Работоспособность всех кнопок 'Начать продавать'

### Тест кейсы для UI mobile тестирования

✓ Отображение значка 'Поделиться' в рекламном банере

✓ Напоминания в разделе с лайв видео

✓ Фильтры в разделе 'Пункты выдачи на карте' в профиле

✓ Необходимость авторизации для добавления видео в 'Моменты'

✓ Работоспособность функции 'Скан товара'

[К содержанию ⬆](#содержание)

## <img width="4%" title="Jenkins" src="https://raw.githubusercontent.com/Valentine1337/qa_guru_diplom_uiAndMobile/master/images/logo/Jenkins.svg"> [Сборка в Jenkins](https://jenkins.autotests.cloud/job/011_Diplom_UiAndMobile_valentiniam/)
    gradle clean ${TYPE_OF_UI_TESTS}
    -DstandHost=${STAND}
    -DdeviceHost=${HOST_OF_MOBILE_TESTS}
    -Dthreads=${THREADS}
![](images/screenshots/Jenkins_2.png)
В данной сборке указаны следующие параметры:

`${TYPE_OF_UI_TESTS}` - тип тестов web или mobile (возможен запуск **web тестов** - в **selenoid**,
**mobile тестов** - в **Browserstack**, на эмуляторе в **Android Studio** c
помощью сервера **Appium**)

`standHost` - стенд (опция пустая, добавлена ради эмуляции боевого проекта). Указывается в виде URL **https://www.ozon.ru**, **https://www.test-ozon.ru** как пример.

`deviceHost` - хост для мобильных тестов (**Browserstack**, **emulator**)

`threads` - количество потоков для запуска теста (от null до 4)

Остальные опции настраиваются с помощью файла .properties, пример лежит в папке **resources**.

![](images/screenshots/Jenkins_2.png)

[К содержанию ⬆](#содержание)

## <img width="4%" title="Jenkins" src="https://raw.githubusercontent.com/Valentine1337/qa_guru_diplom_uiAndMobile/master/images/logo/Allure.svg"> Отчеты и информация о тестах в [Allure report](https://jenkins.autotests.cloud/job/011_Diplom_UiAndMobile_valentiniam/)

### Дашбоард

![](images/screenshots/Allure_1.jpg)
_Мобильные тесты_

### Окно с тест-кейсами 

![](images/screenshots/Allure_2.png)
_Веб тесты_

### Окно с графиками

![](images/screenshots/Allure_3.jpg)
_Графики веб тестов_

![](images/screenshots/Allure_4.jpg)
_Мобильные тесты_

![](images/screenshots/Allure_5.jpg)
_Графики мобильных тестов_

[К содержанию ⬆](#содержание)

## <img width="4%" title="Jenkins" src="https://raw.githubusercontent.com/Valentine1337/qa_guru_diplom_uiAndMobile/master/images/logo/Allure_EE.svg"> Интеграция с [AllureTestOps](https://allure.autotests.cloud/project/1329/dashboards)

### Дашборд проекта

![](images/screenshots/Allure_TO.jpg)

### Список ручных и автотестов
![](images/screenshots/Allure_TO2.jpg)

[К содержанию ⬆](#содержание)
## <img width="4%" title="Jenkins" src="https://raw.githubusercontent.com/Valentine1337/qa_guru_diplom_uiAndMobile/master/images/logo/Telegram.svg"> Уведомления в Telegram

После завершения тестов отчет о прохождении приходит в Telegram с помощью заранее созданного бота

### Для web тестов
![](images/screenshots/telegram-bot.jpg)

[К содержанию ⬆](#содержание)

## :movie_camera: Пример аттачей
К каждому тесту в Allure прикрепляется видеопрохождение, скриншот последнего экрана и код страницы

### Видео прохождения web тестов (пример)

![](images/screenshots/web.gif)

### Видео прохождения mobile тестов (пример)

![](images/screenshots/mobile.gif)
[К содержанию ⬆](#содержание)
