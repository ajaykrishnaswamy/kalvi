FROM python:3.12.2

RUN pip3 install poetry

WORKDIR /usr/src/app

COPY pyproject.toml poetry.lock ./

# Install dependencies only
RUN poetry config virtualenvs.create false \
    && poetry install --no-root --no-interaction --no-ansi

# Then copy the rest of the application
COPY . .

CMD ["python", "manage.py", "runserver", "0.0.0.0:8000"]