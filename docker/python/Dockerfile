FROM python:3.10-alpine

WORKDIR /code

RUN apk update && apk add \
    gcc \
    libc-dev \
    make \
    mariadb-connector-c-dev

COPY requirements.txt requirements.txt
RUN pip install -r requirements.txt

EXPOSE 8000
COPY . .
CMD ["daphne", "mydjango.asgi:application", "-b", "python"]