# Веб сервис на Django.

***

## ЗАДАНИЕ

Необходимо реализовать веб-сервис с использованием фреймворка Django и СУБД PostgreSQL имеющее два API метода:

1. Метод для заполнения списка остановок по URL с использованием API Яндекс карт.  
Метод входным параметром должен получать ссылку на Яндекс карту, которая ведет на маршрут городского автотранспорта. Пример: [ссылка](https://yandex.ru/maps/213/moscow/routes/bus_e70/796d617073626d313a2f2f7472616e7369742f6c696e653f69643d32303336393234353737266c6c3d33372e37333038383425324335352e373236383635266e616d653d254430254235373026723d3637383026747970653d627573/?l=masstransit&ll=37.617700%2C55.755863&tab=stops&z=10).
2. Метод, возвращающий список остановок по указанному маршруту.  
Метод должен возвращать данные из таблицы `mts_routepoint` в виде json-массива, в котором должны быть поля:

- порядковый номер остановки по маршруту;
- название остановки;
- координаты.

json должен реализовывать двухсвязный некольцевой список.

> [!IMPORTANT]
>**Важно** 
>При выполнении задания не использовать библиотеки Yandex.API и Django REST. Для получения данных из Яндекс карт использовать библиотеку `requests`, метод `session`.
>Желательно, но необязательно добавить в проект Swagger.

***

## Структура таблиц
Таблица `mts_route`
```sql
CREATE TABLE public.mts_route (
	id serial NOT NULL,
	name varchar(128) NOT NULL
);
```

Таблица `mts_routepoint`  
```sql
CREATE TABLE mts_routepoint (
	id serial NOT NULL,
	name varchar(128) NOT NULL,
	route_id int4 NULL,
	next_point_id int4 NULL,
	prev_point_id int4 NULL,
	point geometry NOT NULL
	CONSTRAINT mts_routepoint_pkey PRIMARY KEY (id)
);
```

***

### ПРИМЕРЫ РЕШЕНИЙ

***

**[Назад](/developer/README.md)**