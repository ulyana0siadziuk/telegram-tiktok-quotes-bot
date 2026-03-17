# Telegram TikTok quotes bot

Telegram‑бот, который отправляет случайную мотивирующую цитату и даёт ссылку на поиск видео в TikTok по этой цитате (в веб‑версии TikTok).

## Как это выглядит

Скриншот работы бота в Telegram:

![Telegram TikTok quotes bot](./screenshot.png)

## Функциональность

- Получение случайной цитаты через API [ZenQuotes](https://zenquotes.io/).
- Перевод цитаты на русский язык с помощью `deep_translator` (`GoogleTranslator`).
- Генерация ссылки на поиск этой цитаты в TikTok (web):
  - формируется URL вида `https://www.tiktok.com/search?q=<текст_цитаты>`.
- Отдельная команда для скачивания TikTok‑видео по ссылке с помощью `yt-dlp`.
- Логирование ошибок в консоль.

Основные команды бота:

- `/start` — приветствие и краткая инструкция.
- `/help` — помощь по командам.
- `/quote` — получить случайную цитату и ссылку на поиск в TikTok.
- `/tiktok <ссылка>` — скачать видео из TikTok по ссылке и отправить в чат.

## Стек

- **Язык**: Python  
- **Библиотеки**:
  - `python-telegram-bot` — работа с Telegram Bot API
  - `requests` — HTTP‑запросы к API цитат
  - `deep-translator` — перевод текста
  - `yt-dlp` — скачивание видео из TikTok
- **Внешние сервисы**:
  - ZenQuotes API
  - Web‑версия TikTok для поиска по сгенерированной ссылке

## Запуск проекта

1. Клонировать репозиторий:

   ```bash
   git clone https://github.com/ulyana0siadziuk/telegram-tiktok-quotes-bo.git
   cd telegram-tiktok-quotes-bo
   ```

2. (Опционально) Создать и активировать виртуальное окружение:

   ```bash
   python -m venv venv
   venv\Scripts\activate
   ```

3. Установить зависимости:

   ```bash
   pip install -r requirements.txt
   ```

   > Если файла `requirements.txt` нет, можно установить напрямую:
   >
   > ```bash
   > pip install python-telegram-bot requests deep-translator yt-dlp
   > ```

4. Указать токен Telegram‑бота через переменную окружения `TELEGRAM_BOT_TOKEN`:

   ```powershell
   $env:TELEGRAM_BOT_TOKEN = "ТВОЙ_ТОКЕН_БОТА"
   ```

5. Запустить бота:

   ```bash
   python main.py
   ```

После запуска бот начнёт опрашивать Telegram и будет отвечать на команды в чате.

## Идея и цель

Проект сделан как учебный пет‑проект для практики:

- работы с Telegram Bot API,
- интеграции с внешними API (цитаты, перевод),
- генерации ссылок для сторонних сервисов (TikTok),
- работы с мультимедиа (скачивание и отправка видео).

Основная идея — быстро получить вдохновляющую цитату и по ней же посмотреть короткие видео в TikTok, соответствующие настроению цитаты.