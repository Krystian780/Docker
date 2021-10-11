# syntax=docker/dockerfile:1
FROM python:3.7-alpine

WORKDIR /code

ENV REDIS_HOST="172.19.0.3"
ENV REDIS_PORT="6379"

COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

EXPOSE 8000

COPY . .

CMD ["gunicorn", "-w 4", "-b", "0.0.0.0:8000", "main:app"]
