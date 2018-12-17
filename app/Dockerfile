FROM python:alpine
WORKDIR /usr/src/app
COPY requirements.txt ./
RUN apk update && apk upgrade
RUN apk add --no-cache mariadb-connector-c-dev
RUN apk add --no-cache --virtual .build-deps build-base linux-headers mysql-client
RUN python -m venv .env
RUN .env/bin/pip install --no-cache-dir -r requirements.txt
RUN apk del .build-deps
