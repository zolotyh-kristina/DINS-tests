# DINS-tests

## Задание 1
[Ссылка на тесты](https://github.com/zolotyh-kristina/DINS-tests/blob/master/tests.js)

## Задание 2

### Тест-кейсы

Тестирование выполнять на всех требуемых окружениях и устройствах;

Для тестирования можно применять техники тест-дизайна: КЭ, ГЗ;

#### GET /posts
##### Позитивные проверки

Тест-кейс 1

Окружение: 
base URL: https://jsonplaceholder.typicode.com

Запрос GET /posts?userId=10

1. Отправить запрос методом GET по пути /posts?userId=10 

ОР: 200 ОК

{
    "userId": "number",
    "id": "number",
    "title": "string",
    "body": "string"
  }

Тест-кейс 2

Окружение: 
base URL: https://jsonplaceholder.typicode.com

Запрос GET /posts?title=qui%20est%20esse

1. Отправить запрос методом GET по пути /posts?title=qui%20est%20esse

ОР: 200 ОК

[
  {
    "userId": 1,
    "id": 2,
    "title": "qui est esse",
    "body": "est rerum tempore vitae\nsequi sint nihil reprehenderit dolor beatae ea dolores neque\nfugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis\nqui aperiam non debitis possimus qui neque nisi nulla"
  }
]

Тест-кейс 3

Окружение: 
base URL: https://jsonplaceholder.typicode.com

GET /posts?title=qui%20est%20esse&userId=1

1. Отправить запрос методом GET по пути /posts?title=qui%20est%20esse&userId=1

ОР: 200 ОК

[
  {
    "userId": 1,
    "id": 2,
    "title": "qui est esse",
    "body": "est rerum tempore vitae\nsequi sint nihil reprehenderit dolor beatae ea dolores neque\nfugiat blanditiis voluptate porro vel nihil molestiae ut reiciendis\nqui aperiam non debitis possimus qui neque nisi nulla"
  }
]



##### Негативные проверки

GET /posts?userId=null
GET /posts?userId=undefined
GET /posts?userId='''''
GET /posts?userId=hello
GET /posts?userId=-1
PUT /posts?userId=1

## Задание 3

В данной задаче написанно, что GET posts/101 вернул код 404, а должен был вернуть пустой список в теле ответа. 
Эти требования не взаимоисключающие, так как можно вернуть код 404 и тело запроса.
Предполагаю, что API должно вернуть код 200 и пустой объект.

*GET /posts/101 wrong respouns*

Окружение: 
base URL: https://jsonplaceholder.typicode.com

Шаги:
1. Отправить запрос по пути /posts/101 методом GET (`curl request GET https://jsonplaceholder.typicode.com/posts/101`)

### Ожидаемый результат

Статус код: 200 

Тело ответа: `{}`

### Фактический результат

Стаутс код :404 

Тело ответа: без тела



