# Promesas 🤝

- "Una **Promise** (promesa) es un **objeto** que representa la terminación o el fracaso de una **operación asíncrona**." - [MDN](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Usar_promesas)

- Una manera más limpia de hacer callbacks.
- Evitan el **Callback Hell**.

> 🔥 **Callback Hell**: "Consiste en múltiples Callbacks anidados que provocan que el código se vuelva difícil de leer y ‘debuggear’; ésta es la principal razón por la cual se debe evitar..." - [El Callback Hell](https://blog.nearsoftjobs.com/the-callback-hell-6cc184ce8704)

**Ejemplo de una promesa:**

```
    let miPromesa = new Promise((resolve, reject) => {
        let tePrometoQue = 1 + 1
        if (tePrometoQue == 2) {
            resolve('Eres de fiar 🌹')
        } else {
            reject('No eres de fiar 🥀')
        }
    })

    miPromesa.then((mensaje) => {
        console.log(mensaje) //Eres de fiar 🌹
    }).catch((message) => {
        console.log(mensaje) // No eres de fiar 🥀
    })

```

### Diseccionando una Promesa 💉

Una promesa tiene diferentes **estados**:

* ❔**pending**: estado inicial, no cumplida o rechazada.

* ✔**fulfilled**: operación completada satisfactoriamente.

* ❌**rejected**: operación fallida.

[![promise](assets/promises.png)](https://developer.mozilla.org/es/docs/Web/JavaScript/Guide/Usar_promesas)

- 👍**resolve**: Es la función que llamamos cuando la promesa finaliza con éxito.

- 👎**reject**: Es la función que llamamos cuando la promesa falla.

### Convirtiendo una callback a promesa

    const personaDeGatos = false
    const personaDePerros = false

    //Usando CALLBACKS//

    function queTipoDePersonaEres(callback, errorCallback) {
        if (personaDeGatos) {
            errorCallback('Los 🐱 molan')
        }
        else if (personaDePerros) {
            errorCallback('Los 🐶 molan')
        } else {
            callback('No me gustan pelos en el sofá 🛋️')
        }
    }

    queTipoDePersonaEres((mensaje) => {
        console.log(mensaje) // No me gustan pelos en el sofá 🛋️
    }, (error) => {
        console.log(error) // Los 🐱 molan // o // Los 🐶 molan
    })


    /// PROMISE

    function queTipoDePersonaEres() {
        return new Promise ((resolve, reject) => {
            if (personaDeGatos) {
            reject('Los 🐱 molan')
             }
            else if (personaDePerros) {
                reject('Los 🐶 molan')
            } else {
                resolve('No me gustan pelos en el sofá 🛋️')
            }
        })
    }

    queTipoDePersonaEres().then((mensaje) => {
        console.log(mensaje) // No me gustan pelos en el sofá 🛋️
    }).catch((error) => {
        console.log(error) // Los 🐱 molan // o // Los 🐶 molan
    })

✨¡Espero que te haya ayudado!✨

[< Volver al índice](https://github.com/thamaragerigr/Resumenes-de-JavaScript)