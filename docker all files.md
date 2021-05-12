# Step 1

### Dockerfile

```
FROM python:3.6-slim

ENV PYTHONUNBUFFERED 1
ENV PORT 8000

ENV TZ=Asia/Dhaka
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

WORKDIR /app
RUN mkdir src

RUN apt-get update && apt-get install build-essential curl -y && \
    pip3 install -U pip

ADD requirements.txt /app

RUN pip3 install -r requirements.txt && \
    apt-get --purge autoremove build-essential -y


COPY src/ /app/src/

EXPOSE 8000
```




### docker-compose.ymal

```
version: "3"

services:
  db:
    image: postgres:11.4-alpine
    environment:
      - POSTGRES_USER=django_food
      - POSTGRES_PASSWORD=12345
      - POSTGRES_DB=django_food
    ports:
      - 54323:5432

  redis:
    image: redis:5-alpine
    ports:
      - 6378:6379

  app:
    build:
      context: .
      dockerfile: Dockerfile
    links:
      - db:db
      - redis:redis
    depends_on:
      - db
      - redis
    volumes:
      - ./src:/app/src
    command: bash -c "python src/manage.py runserver 0.0.0.0:8000"
    ports:
      - 8099:8000
    env_file:
      - .env
```





### .env

```
DB_HOST=db
DB_USER=django_food
DB_PASS=12345
DB_PORT=5432
DB_NAME=django_food
DEBUG=True
SECRET_KEY=8dd3w6-_!&1s@6*pr0zbgi19v)$9g7v89x@_p9g@827&+9fv21
REDIS_HOST=redis
```




### .gitignore
#### https://www.gitignore.io/api/django
#### https://www.gitignore.io/?templates=django






### .editorconfig

#### http://editorconfig.org


