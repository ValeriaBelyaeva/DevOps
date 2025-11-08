# ХОРОШИЙ Dockerfile

# 1) Лёгкий специализированный образ с фиксированной версией
FROM python:3.12-slim

# 2) Явная рабочая директория
WORKDIR /app

# 3) Отдельный слой для зависимостей -> хороший кэш
COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

# 4) Копируем только нужный код
COPY app.py .

# 5) Создаём нерутового пользователя
RUN useradd -m appuser && chown -R appuser:appuser /app
USER appuser

# 6) Экспонируем порт приложения
EXPOSE 8000

CMD ["python", "app.py"]
