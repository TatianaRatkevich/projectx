# Используем официальный Python 3.13 образ
FROM python:3.13-slim

# Устанавливаем рабочую директорию
WORKDIR /usr/src/app

# Устанавливаем зависимости для сборки (например psycopg2, Pillow)
RUN apt-get update && apt-get install -y \
    build-essential \
    libpq-dev \
    && rm -rf /var/lib/apt/lists/*

# Копируем requirements.txt и устанавливаем зависимости
COPY requirements.txt .
RUN pip install --upgrade pip && pip install -r requirements.txt

# Копируем весь проект внутрь контейнера
COPY . .

# Указываем переменные окружения
ENV PYTHONDONTWRITEBYTECODE=1
ENV PYTHONUNBUFFERED=1

# Запуск через Gunicorn
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "projectx.wsgi:application"]
