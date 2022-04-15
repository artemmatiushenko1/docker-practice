FROM python:3.10-buster

WORKDIR /app

COPY . .

RUN pip install --no-cache-dir -r ./requirements/backend.in

EXPOSE 80

CMD ["uvicorn", "spaceship.main:app", "--proxy-headers", "--host", "0.0.0.0", "--port", "80"]