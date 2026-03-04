FROM python:3.14-slim

WORKDIR /app

ENV POETRY_NO_INTERECTION=1

RUN apt-get update \
    && apt-get install -y --no-install-recommends make \
    && rm -rf /var/lib/apt/lists/*

RUN pip install --upgrade pip \
    && pip install --no-cache-dir poetry uvicorn fastapi 'pydantic[email]' \
    && poetry config virtualenvs.create false

COPY pyproject.toml poetry.lock /app/
RUN poetry install --no-ansi --no-root --no-interaction

COPY /app /app

EXPOSE 12321
