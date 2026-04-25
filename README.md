# Чат-бот для изучения программирования — Этап 2

## Структура проекта

```
bot_project/
├── bot/
│   └── bot.py              # Telegram-бот (pyTelegramBotAPI)
├── admin_panel/            # Django-проект
│   ├── manage.py
│   ├── admin_panel/
│   │   ├── settings.py
│   │   ├── urls.py
│   │   └── wsgi.py
│   └── queries/            # Django-приложение
│       ├── models.py       # Модель UserQuery
│       ├── admin.py        # Регистрация в админке
│       └── migrations/
├── shared/
│   └── db_writer.py        # Запись запросов в БД из бота
├── quotes.txt
└── requirements.txt
```

## Установка и запуск

### 1. Установить зависимости
```bash
pip install -r requirements.txt
```

### 2. Настроить бота
В файле `bot/bot.py` замени `YOUR_BOT_TOKEN` на токен от @BotFather.

### 3. Настроить Django
```bash
cd admin_panel
python manage.py migrate
python manage.py createsuperuser
```

### 4. Запустить Django-сервер
```bash
cd admin_panel
python manage.py runserver
```
Откройте http://127.0.0.1:8000/admin/

### 5. Запустить бота (в отдельном терминале)
```bash
python bot/bot.py
```

## Команды бота
- `/start` — приветствие
- `/help` — список команд
- `/topics` — список тем
- `/topic [тема]` — объяснение темы
- `/example [тема]` — пример кода
- `/task [тема]` — задание по теме
- `/quiz` — случайный вопрос викторины
- `/quote` — случайная цитата
- `/weather [город]` — заглушка погоды
- `/progress` — статистика
