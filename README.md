# DINS-tests

## Задание 1
[Ссылка на тесты](https://github.com/zolotyh-kristina/DINS-tests/blob/master/tests.js)

## Задание 2

### Тест-кейсы

Тестирование выполнять на всех требуемых окружениях и устройствах;

Для тестирования можно применять техники тест-дизайна: КЭ, ГЗ;

#### GET /posts
##### Позитивные проверки

*Тест-кейс 1*

Окружение: 
base URL: https://jsonplaceholder.typicode.com

Запрос GET /posts?userId=10

1. Отправить запрос методом GET по пути /posts?userId=10 

ОР: 200 ОК

[
  {
    "userId": 1,
    "id": "number",
    "title": "string",
    "body": "string"
  }
]

*Тест-кейс 2*

Окружение: 
base URL: https://jsonplaceholder.typicode.com

Запрос GET /posts?title=qui%20est%20esse

1. Отправить запрос методом GET по пути /posts?title=qui%20est%20esse

ОР: 200 ОК

[
  {
    "userId": "number",
    "id": "number",
    "title": "qui est esse",
    "body": "string"
  }
]

*Тест-кейс 3*

Окружение: 
base URL: https://jsonplaceholder.typicode.com

GET /posts?title=qui%20est%20esse&userId=1

1. Отправить запрос методом GET по пути /posts?title=qui%20est%20esse&userId=1

ОР: 200 ОК

[
  {
    "userId": 1,
    "id": "number",
    "title": "qui est esse",
    "body": "string"
  }
]



##### Негативные проверки

*Тест-кейс 4*

Окружение: 
base URL: https://jsonplaceholder.typicode.com

GET /posts?userId=null

1. Отправить запрос методом GET по пути /posts?userId=null

ОР: статус код 404, 
Тело ответа: `{}`

*Тест-кейс 5*

Окружение: 
base URL: https://jsonplaceholder.typicode.com

GET /posts?userId=undefined

1. Отправить запрос методом GET по пути /posts?userId=undefined

ОР: статус код 404,
Тело ответа: `{}`

*Тест-кейс 6*

Окружение: 
base URL: https://jsonplaceholder.typicode.com

GET GET /posts?userId='''''

1. Отправить запрос методом GET по пути /posts?userId='''''

ОР: статус код 404,
Тело ответа: `{}`

*Тест-кейс 7*

Окружение: 
base URL: https://jsonplaceholder.typicode.com

GET /posts?userId=hello

1. Отправить запрос методом GET по пути /posts?userId=hello

ОР: статус код 404,
Тело ответа: `{}`

*Тест-кейс 8*

Окружение: 
base URL: https://jsonplaceholder.typicode.com

GET /posts?userId=-1

1. Отправить запрос методом GET по пути /posts?userId=-1

ОР: статус код 404,
Тело ответа: `{}`

*Тест-кейс 9*

Окружение: 
base URL: https://jsonplaceholder.typicode.com

PUT /posts?userId=1

1. Отправить запрос методом PUT по пути /posts?userId=1

ОР: статус код 404



## Задание 3

В данной задаче написанно, что GET posts/101 вернул код 404, а должен был вернуть пустой список в теле ответа. 
Эти требования не взаимоисключающие, так как можно вернуть код 404 и тело запроса.
Предполагаю, что API должно вернуть код 200 и пустой объект.

ID BUG-1
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



