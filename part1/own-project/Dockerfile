FROM python:3.10-slim

ENV PYTHONDONTWRITEBYTECODE=1 \
    PYTHONUNBUFFERED=1 \
    FLASK_APP=app.py

WORKDIR /app

RUN pip install --no-cache-dir poetry

COPY pyproject.toml poetry.lock* /app/

RUN poetry config virtualenvs.create false \
    && poetry install --no-dev

COPY . /app

WORKDIR /app/src

EXPOSE 5000

CMD ["poetry", "run", "flask", "run", "--host=0.0.0.0"]

