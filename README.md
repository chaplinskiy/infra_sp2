# chaplinskiy/infra_sp2
Учебный проект 15 спринта факультета бэкенд-разработки [Яндекс.Практикума](https://practicum.yandex.ru/backend-developer)

## стек:
- Python
- Django
- Docker
- Nginx
- Много чего еще (см. файл `api_yamdb/requirements.txt`)

## руководство по установке Docker
можно найти [здесь](https://docs.docker.com/engine/install/)


---

## Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```bash
git clone https://github.com/chaplinskiy/infra_sp2.git
```

```bash
cd api_yamdb/
```

Cоздать и активировать виртуальное окружение:

```bash
python3 -m venv env
```

```bash
source env/bin/activate
```

```bash
python3 -m pip install --upgrade pip
```

Установить зависимости из файла requirements.txt:

```bash
pip install -r requirements.txt
```

Запустить приложение в контейнерах:

*из директории `infra/`*
```bash
docker-compose up -d --build
```

Выполнить миграции:

*из директории `infra/`*
```bash
docker-compose exec web python manage.py migrate
```

Создать суперпользователя:

*из директории `infra/`*
```bash
docker-compose exec web python manage.py createsuperuser
```

Собрать статику:

*из директории `infra/`*
```bash
docker-compose exec web python manage.py collectstatic --no-input
```

Остановить приложение в контейнерах:

*из директории `infra/`*
```bash
docker-compose down -v
```
Запуск `pytest`:

*при запущенном виртуальном окружении*
```bash
cd infra_sp2 && pytest
```

### Документация API с примерами:

```json
/redoc/
```

### шаблон наполнения env-файла
см.
```bash
infra/.env.template
```

### описание команды для заполнения базы данными
```bash
cd api_yamdb && python manage.py loaddata ../infra/fixtures.json
```

## Другие проекты автора:
https://github.com/chaplinskiy/