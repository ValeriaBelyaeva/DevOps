# ПЛОХОЙ Dockerfile

# 1) Тяжёлый базовый образ + latest
FROM ubuntu:latest

# 2) Устанавливаем много лишнего, без очистки кэша
RUN apt-get update && \
    apt-get install -y python3 python3-pip git curl vim && \
    echo "Bad Dockerfile example"

# Рабочая директория (это вообще из хорошего, но я не знаю как сделать тоже, но плохо)
WORKDIR /app

# 3) ADD и копирование всего контекста (включая мусор)
ADD . /app

# 4) Установка зависимостей в том же слое — без оптимизации кэша
RUN pip3 install -r requirements.txt

# 5) Запуск под root (пользователь по умолчанию не меняется)
CMD ["python3", "app.py"]
