# chaplinskiy/infra_sp2
Учебный проект 15 спринта факультета бэкенд-разработки [Яндекс.Практикума](https://practicum.yandex.ru/backend-developer)

## шаблон наполнения env-файла
см. ```infra/.env.template```

## описание команд для запуска приложения в контейнерах
```cd infra && docker-compose up -d --build```

## описание команды для заполнения базы данными
```cd api_yamdb && python manage.py loaddata ../infra/dump.json```