# tg-бот для заказов (хардкод)
Данный бот разработан за 2 дня для хакатона.
Основная задача - помогать отслеживать статус заказа по его номеру с помощью тг бота на питоне, путем отправки запроса на api сбп райфайзенбанка
Код написан на питоне и использует библиотеки
1) pandas - для ускорения работы с файлами
2) requests - для отправки запросов
3) telebot - для работы самого бота
Несмотря на подключение данных библиотек, основной задачей было упрощение внедрения бота в систему. Поэтому бд в проекте не используется и основная информация хранится в формате json и csv


## Конфигурация

### Для работы проекта необходимо установить следующие параметры конфигурации:

- base_url = 'https://pay-test.raif.ru/api/sbp/v2/qrs/'
- secret_key = 'ВАШ_СЕКРЕТНЫЙ_КЛЮЧ'
- headers = {'Authorization': f'Bearer {secret_key}'}
- sbpMerchantId = 'ВАШ_MERCHANT_ID'
- user_file_path = 'users.csv'
- admin_file_path = 'admins.csv'
- bot_key = 'ВАШ_BOT_KEY'

## requests_funcs.py

Модуль requests_funcs.py содержит функции для взаимодействия с API Сбербанка:
- response_code_handler(code): Обработчик кодов ответа.
- create_qr_request(url, body, headers): Создание QR-кода.
- get_qr_request(url, body, headers): Получение информации о QR-коде.
- delete_qr_request(url, body, headers): Удаление QR-кода.

## Файл main.py содержит основную логику Telegram бота, включая:

- Авторизацию администраторов и пользователей.
- Функции для добавления и удаления администраторов и пользователей.
- Обработку команд для создания, поиска и удаления QR-кодов.
- Файлы данных
- admins.csv: Файл содержит данные администраторов (tg-id и пароль).
- users.csv: Файл содержит данные пользователей (tg-id).

### Запуск
Для запуска бота используйте команду: python bot_logic.pyэ

### Пример работы бота доступен по ссылке
https://youtu.be/j_S9NiEzHm4
