FROM python:3.9-slim

WORKDIR /app

RUN pip install gunicorn==20.1.0

COPY requirements.txt .

RUN pip install -r requirements.txt --no-cache-dir

# Копируем все, что в директории backend в директорию /app контейнера.
COPY . .

# Запускаем gunicorn на 8000 порту.
CMD ["gunicorn", "--bind", "0:9000", "kittygram_backend.wsgi"]
