# Async / Await

Es una sintaxis especial que nos permite escribir código asíncrono de manera que parece síncrono.

## Async

La palabra clave `async`se coloca al principio de una función para indicar que esta devuelve una promesa. Por ejemplo:

    async function ejemplo() {
    return 1;
    }

    ejemplo().then(alert); // 1

Es lo mismo que:

    async function ejemplo() {
    return Promise.resolve(1);
    }

    ejemplo().then(alert); // 1

## Await

Otra palabra clave es `await`, la cual solo funciona dentro de funciones asíncronas, es decir, que lleven `async` por delante.

El poder de esta palabra esta en que le indica a JavaScript que debe esperar hasta que la promesa se cumpla. Ejemplo:

    async function f() {

    let promise = new Promise((resolve, reject) => {
        setTimeout(() => resolve("done!"), 1000)
    });

    let result = await promise;

    alert(result);
    }

    f();

## Error Handling

Para manejar los casos en los que la promesa no es resuelta podemos utilizar la sintaxis `try..catch`