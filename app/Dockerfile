FROM python:alpine
WORKDIR /usr/src/app
COPY requirements.txt ./
RUN apk update && apk upgrade; \
    apk add --no-cache mariadb-connector-c-dev uwsgi-python3; \
    apk add --no-cache --virtual .build-deps build-base mysql-client; \
    pip install --no-cache-dir -r requirements.txt; \
    apk del .build-deps
