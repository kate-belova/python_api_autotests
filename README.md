# Python API Autotests

![Python](https://img.shields.io/badge/Python-3.12-blue)
![Pytest](https://img.shields.io/badge/Pytest-tested-green)
![HTTPX](https://img.shields.io/badge/HTTPX-API%20Testing-brightgreen)
![GitHub Actions](https://img.shields.io/badge/CI-GitHub%20Actions-success)

Учебный проект по автоматизации тестирования REST API с использованием **Python**, **HTTPX** и **Pytest**.
Проект демонстрирует построение сервисного слоя, валидацию данных и организацию API-тестов.

## Стек

- Python
- HTTPX
- Pytest
- Pydantic
- Allure Report
- GitHub Actions

## Что реализовано

- Тестирование REST API
- Сервисный слой для работы с API
- Базовый API-класс для повторного использования логики запросов
- Модели запросов и ответов на Pydantic
- Валидация данных ответа
- Параметризация тестов
- Фикстуры Pytest
- Проверка позитивных и негативных сценариев
- Автоматический запуск тестов через GitHub Actions
- Генерация Allure-отчётов

## Структура проекта

```
schemas/        # Pydantic-модели
services/       # сервисы для работы с API
tests/          # API-тесты
conftest.py     # общие фикстуры Pytest
pytest.ini      # настройки Pytest
pyproject.toml
```

## Установка

```bash
git clone https://github.com/kate-belova/python_api_autotests.git
cd python_api_autotests

python -m venv .venv

# Windows
.venv\Scripts\activate

# Linux/macOS
source .venv/bin/activate

uv sync
```

## Запуск тестов

Все тесты:

```bash
pytest
```

По маркеру:

```bash
pytest -m smoke
pytest -m regression
pytest -m positive
pytest -m negative
```

Запуск тестов определённого сервиса:

```bash
pytest tests/users
pytest tests/characters
pytest tests/random
pytest tests/tokens
```

## Отчёт Allure

```bash
allure serve allure-results
```

## CI

При каждом push и pull request тесты автоматически запускаются в GitHub Actions.
