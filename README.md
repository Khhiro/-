# Лекция: Синхронные и асинхронные функции в JavaScript

![](https://www.freecodecamp.org/news/content/images/2023/12/PROMISE---ASYNC.png)

## Введение

В JavaScript функции могут быть синхронными и асинхронными. Понимание этих концепций важно для эффективного написания кода, особенно при работе с сетевыми запросами и другими длительными операциями.

## Синхронные функции

Синхронные функции выполняются последовательно, одна за другой. Если функция выполняет длительную задачу, это может заблокировать выполнение остального кода.

### Пример

```javascript
function syncFunction() {
    console.log("Начало");
    for (let i = 0; i < 1000000000; i++) {} // Длительная операция
    console.log("Конец");
}

syncFunction();
console.log("Эта строка выполнится после завершения syncFunction");
```

# Асинхронные функции

### Асинхронные функции позволяют выполнять задачи, не блокируя основной поток выполнения. Это особенно полезно для операций, требующих времени, таких как сетевые запросы.


## Пример с использованием Promise

```js
function asyncFunction() {
    return new Promise((resolve) => {
        console.log("Начало асинхронной функции");
        setTimeout(() => {
            resolve("Асинхронная операция завершена");
        }, 2000);
    });
}

asyncFunction().then(result => {
    console.log(result);
});
console.log("Эта строка выполнится сразу после вызова asyncFunction");

```

## Асинхронные функции с async/await

![](https://miro.medium.com/v2/resize:fit:1198/1*jcywAqHuABrR1wt0oB1WCQ.png)

### Синтаксис async/await упрощает работу с промисами и делает код более читаемым.

```js
async function main() {
    console.log("Начало");
    const result = await asyncFunction();
    console.log(result);
    console.log("Конец");
}

main();

```
