# Задание на позицию стажёра-разработчка (2020)
***

## ЗАДАНИЕ

Используя один из фреймворков ([Flask](https://palletsprojects.com/p/flask/), [Django](https://www.djangoproject.com/), [FastApi](https://fastapi.tiangolo.com/)), создать микросвервис, который на запрос GET /api/meta/ будет возвращать список файлов (которые находятся в директории) с датой.

Пример ответа от сервиса:

```
{
    "data":[
        {
            "name": "name",
            "type": "file",
            "time": "time"
        },
        {
            "name": "name",
            "type": "file",
            "time": "time"
        },
    ]
}
```

Директория с файлами должна задаваться в config.py
***

###  Дополнительные требования
🔸 наличие Dockerfile;
🔸 наличие virtualenv;
🔸 использование poetry или аналогов.
***


**[Назад](/developer/README.md)**