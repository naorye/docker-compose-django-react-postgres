FROM python:3.7.4-alpine3.10

LABEL maintainer="naorye"

ENV PYTHONUNBUFFERED 1
ENV PYTHONDONTWRITEBYTECODE 1

WORKDIR /app/backend

COPY requirements requirements

RUN apk add --no-cache \
    ca-certificates gcc postgresql-dev linux-headers musl-dev \
    libffi-dev jpeg-dev zlib-dev git

RUN pip install -U pip

RUN pip install -r requirements/dev.txt

COPY src src

COPY .env .env

EXPOSE 8000

CMD cd src && python3 manage.py runserver 0.0.0.0:8000