FROM python:3.9

# Делаем рабочей директорией, то же самое, что команда CD, условно.
WORKDIR /app

# Устанавливаем gunicorn
RUN pip install gunicorn==20.1.0

# Копируем файлик с зависимостями.
COPY requirements.txt .

# Устанавливаем биб-ки в окружение.
RUN pip install -r requirements.txt --no-cache-dir

# Копируем все, что в директории backend в директорию /app контейнера.
COPY . .


CMD ["gunicorn", "--bind", "0:9000", "kittygram_backend.wsgi"]
