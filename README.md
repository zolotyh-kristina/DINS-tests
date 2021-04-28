# DINS-tests

## Задание 1
[Ссылка на тесты](https://github.com/zolotyh-kristina/DINS-tests/blob/master/tests.js)

## Задание 2


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



