# Обновление актуальности

## PUT /pricelist/{id}/renew

Обновляет актуальность указанной или всех позиций магазина

- Ресурс **/pricelist/{id}/renew**
- HTTP-метод **PUT**
- Формат ответа **JSON**

### Параметры

*нет параметров*

### Пример 1. Обновить актуальность позиции с ID = 1

```
PUT /pricelist/1/renew
```

```
HTTP/1.1 200 OK

[{"id":1, "dateUpdate":"2013-01-01 12:00:00"}]
```

### Пример 2. Обновить актуальность несуществующей позиции

```
PUT /pricelist/99/renew
```

```
HTTP/1.1 400 Bad Request

{
    "errors": {99: "Not found"}
}
```

### Пример 3. Обновить актуальность всех позиций магазина

```
PUT /pricelist/all/renew
```

```
HTTP/1.1 200 OK

[
    {"id":1, "dateUpdate":"2013-01-01 12:00:00"},
    {"id":2, "dateUpdate":"2013-01-01 12:00:00"},
    {"id":3, "dateUpdate":"2013-01-01 12:00:00"}
]
```