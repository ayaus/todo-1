# API Документация

## Эндпоинты пользователей

### Получить список пользователей
**GET /api/users**  
Ответ:
```json
[
  {
    "id": 1,
    "fullName": "Иван Иванов",
    "job": "Developer",
    "age": 30,
    "city": "Москва"
  }
]
```

### Получить пользователя по ID
**GET /api/users/:id**  
Ответ:
```json
{
  "id": 1,
  "fullName": "Иван Иванов",
  "job": "Developer",
  "age": 30,
  "city": "Москва"
}
```

### Создать пользователя
**POST /api/users**  
Тело запроса:
```json
{
  "fullName": "Иван Иванов",
  "job": "Developer",
  "age": 30,
  "city": "Москва"
}
```

### Обновить пользователя
**PUT /api/users/:id**  
Тело запроса:
```json
{
  "city": "Санкт-Петербург"
}
```

### Удалить пользователя
**DELETE /api/users/:id**  
Ответ: `204 No Content`

## Эндпоинты задач

### Получить все задачи
**GET /api/tasks**  
Ответ:
```json
[
  {
    "id": 1,
    "userId": 1,
    "title": "Купить молоко",
    "completed": false
  }
]
```

### Получить задачи конкретного пользователя
**GET /api/users/:id/tasks**  
Ответ:
```json
[
  {
    "id": 1,
    "userId": 1,
    "title": "Купить молоко",
    "completed": false
  }
]
```

### Создать задачу для пользователя
**POST /api/users/:id/tasks**  
Тело запроса:
```json
{
  "title": "Сделать домашку",
  "completed": false
}
```
Ответ:
```json
{
  "id": 3,
  "userId": 1,
  "title": "Сделать домашку",
  "completed": false
}
```

### Обновить задачу
**PUT /api/tasks/:id**  
Тело запроса:
```json
{
  "completed": true
}
```

### Удалить задачу
**DELETE /api/tasks/:id**  
Ответ: `204 No Content`

### Каскадное удаление задач при удалении пользователя
**DELETE /api/users/:id**  
После удаления пользователя все его задачи также удаляются.
