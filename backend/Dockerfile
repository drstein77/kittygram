# Указываем базовый образ
FROM python:3.10-slim

# Устанавливаем переменные окружения
ENV PYTHONUNBUFFERED=1

# Создаем рабочую директорию
WORKDIR /app

# Обновляем pip, setuptools и wheel для корректной сборки зависимостей
RUN pip install --upgrade pip setuptools wheel

# Копируем файл с зависимостями
COPY requirements.txt .

# Устанавливаем Python-зависимости
RUN pip install --no-cache-dir -r requirements.txt

# Копируем все файлы проекта
COPY . .

# Открываем порт для приложения
EXPOSE 8000

# Команда для запуска приложения
CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]
