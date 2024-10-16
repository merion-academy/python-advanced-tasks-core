# Задание №6

## Тестирование приложения

### Задача

Покройте тестами ваше веб-приложение с API для получения курсов валют.

### Описание

Доработайте проект из задания №2, добавьте тесты для API.

Примените в тестировании:

- `pytest`;
- `coverage`;
- фикстуры;
- параметризацию;
- мокирование - в тестах не должно быть внешних API запросов;
- проверку выброса исключений;

Также добавьте плагины для:

- проверки отчётом о покрытии тестами;
- тестирования aiohttp сервера;
- мокирования ответов aiohttp клиента;
- поддержки асинхронных тестов.

#### Настройка тестов

Для корректной работы тестов с плагином `pytest-aiohttp` вместе с `aresponses`
в файле `conftest.py` уже созданы фикстуры.
Если вы хотите самостоятельно разобраться со сложностью настройки тестов, то не копируйте себе файл `conftest.py`,
а напишите его полностью самостоятельно.

Если вы решите воспользоваться готовым файлом `conftest.py`, учтите, что его нужно редактировать:

- доработайте одну из существующих фикстур,
  иначе `pytest-aiohttp` вместе с `aresponses` работать не будет - запросы не будут проходить;
- добавляйте необходимые фикстуры ниже в этом же файле.

### Рекомендации

- Настройки `pytest`: https://docs.pytest.org/en/latest/reference/customize.html
- Плагин `pytest-asyncio` для асинхронных тестов https://github.com/pytest-dev/pytest-asyncio
- Пригодится пакет `pytest-aiohttp` https://pypi.org/project/pytest-aiohttp/
- Как тестировать aiohttp server https://docs.aiohttp.org/en/stable/testing.html
- Для замены ответов aiohttp client подойдёт пакет [`aresponses`](https://github.com/aresponses/aresponses)
- Может пригодиться фикстура `tmp_path`: https://docs.pytest.org/en/stable/how-to/tmp_path.html
- Для отчёта по покрытию воспользуйтесь плагином https://pypi.org/project/pytest-cov/
- Исключение строк из отчета покрытия https://coverage.readthedocs.io/en/latest/excluding.html

### Подсказки

Запуск тестов с покрытием и генерация отчёта:

- Запуск pytest с отчётом о покрытии: `pytest --cov`
- Создание HTML отчёта для удобного просмотра в браузере: `coverage html`

Либо всё в одной команде:

```shell
pytest --cov --cov-report=html
```