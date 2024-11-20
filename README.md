1. telegram_bot/
│
├── bot/
│   ├── __init__.py
│   ├── main.py
│   ├── handlers.py
│   ├── database.py
│   ├── payment.py
│   ├── referral.py
│   ├── admin.py
│   └── utils.py
│
├── config.py
│
├── requirements.txt
│
└── README.md
Описание файлов

    config.py: Конфигурационный файл с настройками бота.
    requirements.txt: Файл с зависимостями проекта.
    bot/: Папка с основным кодом бота.
        main.py: Точка входа для запуска бота.
        handlers.py: Обработчики команд и сообщений.
        database.py: Взаимодействие с базой данных.
        payment.py: Логика платежной системы.
        referral.py: Логика реферальной системы.
        admin.py: Административные команды и функции.
        utils.py: Вспомогательные функции.

4. Создание и Активация Виртуального Окружения
 sudo  apt install python3.12-venv

    Создание виртуального окружения:

    sh

python3 -m venv myenv

Активация виртуального окружения:

    На Linux/MacOS:

    sh

source myenv/bin/activate

На Windows:

sh

        myenv\Scripts\activate

Установите зависимости:

pip install -r requirements.txt

Запустите бота:

    python bot/main.py
python -m bot.main

@Mysr_test_bot


Конечные функции бота

    Основное меню с кнопками:
        Пользователь может навигаровать по функциям бота с помощью кнопок.

    Регистрация пользователя:
        При регистрации пользователя, бот генерирует уникальный кошелек TON и сохраняет его в базе данных.

    Платежная система:
        Генерация уникального кошелька TON.
        Интеграция с обменником для конвертации рублевых платежей в TON.
        Логика распределения платежей: 20% на индивидуальный баланс пользователя, пригласившего нового подписчика, и 80% на основной счёт проекта.
        Кнопка "Донат" для перевода средств на благотворительный счёт.

    Реферальная система:
        Генерация уникальной реферальной ссылки.
        Отслеживание количества привлечённых пользователей.
        Автоматическое присвоение статуса "привилегированный" после 5 успешно приглашённых пользователей.
        Реализация выплат: 20% от подписки автоматически зачисляются на баланс пригласившего пользователя.

    "Приватная комната":
        Организация "приватной комнаты" для пользователей со статусом "привилегированный".

    Единоразовая подписка:
        Подписка оформляется один раз и действует бессрочно.
        Доступ к основному каналу с анонсами и новостями, а также к "приватной комнате" при выполнении условия реферальной системы.

    Административные команды:
        Просмотр статистики: общее количество подписчиков, количество пользователей с "привилегированным статусом", динамика привлечения подписчиков, статистика по выплатам и доходам.
        Управление доступами: возможность вручную добавлять или удалять пользователя из "приватной комнаты", ручное обновление статуса.

    Уведомления и отчёты:
        Уведомление пользователя о достижении 5 приглашённых.
        Еженедельные отчёты для администратора: общее количество подписчиков, суммы на счетах, список активных "привилегированных" пользователей.

    Автоматизация контента:
        Возможность запланировать посты (обычные и для "приватной комнаты").

    Просмотр истории транзакций:
        Пользователь может просматривать историю своих транзакций.

    Настройки:
        Пользователь может изменять некоторые настройки, такие как язык интерфейса.

    Обратная связь:
        Пользователь может отправлять сообщения администратору.


Функции админ-панели

    Просмотр статистики:
        Общее количество подписчиков.
        Количество пользователей с "привилегированным статусом".
        Динамика привлечения подписчиков.
        Статистика по выплатам и доходам (раздельно для основного счёта и донатного счёта).

    Управление доступами:
        Возможность вручную добавлять или удалять пользователя из "приватной комнаты".
        Ручное обновление статуса в случае технических сбоев.

    Просмотр истории транзакций:
        Просмотр всех транзакций, совершённых пользователями.

    Управление контентом:
        Возможность запланировать посты (обычные и для "приватной комнаты").

    Уведомления и отчёты:
        Еженедельные отчёты для администратора: общее количество подписчиков, суммы на счетах, список активных "привилегированных" пользователей.
Как пользоваться админ-панелью

    Просмотр статистики:
        Используйте команду /admin_stats, чтобы получить общую статистику по количеству пользователей, привилегированных пользователей и транзакций.

    Управление доступами:
        Используйте команду /admin_manage_access, чтобы вручную добавить или удалить пользователя из "приватной комнаты". Введите Telegram ID пользователя для изменения его статуса.

    Просмотр истории транзакций:
        Используйте команду /admin_view_transactions, чтобы просмотреть все транзакции, совершённые пользователями.

    Управление контентом:
        Используйте команду /admin_schedule_post, чтобы запланировать пост. Введите текст поста.

    Уведомления и отчёты:
        Используйте команду /admin_weekly_report, чтобы получить еженедельный отчёт по количеству пользователей, привилегированных пользователей и транзакций.