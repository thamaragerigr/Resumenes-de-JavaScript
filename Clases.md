# 💡 Clases

## ¿Qué es una clase en JavaScript?

- Es una sintáxsis añadida a ES6 que nos permite utilizar la herencia de prototipo, similar a otros lenguajes orientados a objetos (OOP).

> Recordemos que ES6 se refiere a la versión 6 de ECMA Script (el nombre estandarizado para JavaScript) sacado en el 2015.

- Para declarar una nueva clase utilizamos la palabra clave `class`.

- Son funciones normales de Javascript pero que permiten que sea más sencillo declarar objetos y heredar complejos.

- Ya que son funciones, como cualquier otra, pueden ser **'class expressions'** o **'class declarations'**. Las **'class declaration'** no pueden ser _'hoisted'_, lo que significa que no pueden ser usadas antes de ser definidas en el código.

> Recordemos que _'hoisting'_ es un término que se refiere a cuando se colocan automáticamente las variables arriba del código antes de ser ejecutado.

- A las **'class expressions'** se les puede asignar nombre como a las **'function expression'**:

        let Persona = class {
            constructor(nombre, apellido) {
                this.nombre = firstName;
                this.apellido = lastName;
            }
        }

## ¿Para qué usar clases?

- Sirven como principio de **OOP**.

> OOP significa Objecto Oriented Programming y es un paradigma en la programación tomando en cuenta el enfoque que se le da al código. [Ver más al respecto](https://github.com/thamaragerigr/Resumenes-de-JavaScript/blob/master/OOPvsFP.md).

- Las clases sirven de 'plantillas' para crear nuevos objetos.

- Se utilizan para crear herencias entre objetos, es decir, que puedes crear clases donde las propiedades sean heredadas por las clases *'hijas'*. Lo que permite que podamos crear clases de alto nivel que contengan propiedades comunes entre las hijas, y estas puedan tener otras exclusivas de ellas.

## ¿Qué es un constructor?

- Las clases en JavaScript tienen un 'constructor', el cual es un método especial para crear e inicializar un objeto creado a partir de una clase.

- Un constructor puede utilizar la palabra clave **super** para llamar al constructor de una clase padre.

        class Square extends Polygon {
        constructor(length) {
            // Aquí, llama al constructor de la clase padre con sus longitudes
            // contemplando la anchura y la altura del Polígono
            super(length, length);
            // Nota: En las clases derivadas, super() se debe llamar primero
            // Se puede utilizar "this". Dejando esto causará un error de
            //referencia.
            this.name = 'Square';
        }

            get area() {
                return this.height * this.width;
            }

            set area(value) {
                this.area = value;
            }
        }

## ¿Para qué sirve super()?

- Un constructor también puede llamar al método 'super' para llamar al constructor de la 'super class', si esta clase se extiende de una madre.

## ¿Qué son getters y setters? ¿Cuándo usar cada uno?

- Getters son métodos que te permiten coger informacion de una clase. Se denotan con la palabra `get`

- Setters te permiten cambiar propiedades dentro de una clase. Se denotan con la palabra 'set'

<!-- with the èxtends`keyword https://levelup.gitconnected.com/using-classes-in-javascript-e677d248bb6e--> 


✨¡Espero que te haya ayudado!✨

[< Volver al índice](https://github.com/thamaragerigr/Resumenes-de-JavaScript)