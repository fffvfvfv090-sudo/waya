# Telegram bot (пример)

Короткая инструкция, чтобы запустить локально (Windows PowerShell).

1) Перейдите в папку `c:\Users\rober\OneDrive\Документы\waya` и создайте виртуальное окружение (опционально):

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
pip install --upgrade pip
pip install -r requirements.txt
```

2) Скопируйте `.env.sample` в `.env` и заполните `BOT_TOKEN` и при необходимости ссылки:

```text
BOT_TOKEN=ваш_токен
SUBMIT_LINK=https://clubgg.app.link/...
MENU_IMAGE=меню.png  # уже присутствует в папке
```

3) Файлы, включённые в папку:
- `bot.py` — пример Telegram-бота на aiogram с меню, акциями и FSM для приёма заявок; сохраняет заявки в `submissions.json`.
- `flow.json` — кодовое представление всех блоков/настроек со скриншотов.
- `flow_repr.py` — утилита для подстановки `{{SUBMIT_LINK}}` и создания `flow_resolved.json`.
- `меню.png` — изображение меню (уже в папке).

4) Запуск бота:

```powershell
# активируйте виртуальное окружение
python bot.py
```

5) Команды и сценарии:
- Откройте чат с ботом и отправьте `/start` или `/menu`.
- Чтобы подать заявку через бота (форма ожидания), используйте команду `/submit` — бот попросит ввести текст заявки и сохранит её в `submissions.json`.

Если хотите, я могу:
- добавить экспорт `flow.json` в формат SmartBot,\
- расширить `bot.py` (отправлять PDF/вложения, логировать, уведомлять менеджера через Telegram и т.д.).
