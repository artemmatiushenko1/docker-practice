FROM python:3.10-buster

WORKDIR /app

COPY ./requirements/backend.txt .

RUN pip install --no-cache-dir -r backend.txt

COPY . .

EXPOSE 80

CMD ["uvicorn", "spaceship.main:app", "--proxy-headers", "--host", "0.0.0.0", "--port", "80"]