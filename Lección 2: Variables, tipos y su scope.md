# 💡 Lección 2: Variables, tipos y su scope

1. [Variables](#Variables)
2. [¿Qué es y cómo se come?](#El-scope:¿Qué-es-y-cómo-se-come?)
3. [Tipos de Variable](#Tipos-de-variable)
   1. [var](#var)
   2. [¿Por qué no deberíamos usar var?](#¿Por-qué-no-deberíamos-usar-var?)
   3. [let](#let)
   4. [const](#const)
   5. [Decidiendo entre let y const](#Decidiendo-entre-let-y-const)

## Variables

Una **variable** es un elemento que se emplea para almacenar y hacer referencia a otro valor. Visto desde otro modo, son como **jarrones que puedes etiquetar 🏷️** y **guardar lo que necesites**. Gracias a ellas, se pueden codificar "programas genéricos", es decir, programas que funcionan siempre igual sin importar que los valores cambien.

A la hora de programar, `var`, `let` y `const` tienen ciertas diferencias que debemos conocer. Para ello es necesario tener claro el espacio en el que se encuentran y su entorno, es decir, el **'scope'**.

## El scope : ¿Qué es y cómo se come?

El **‘scope’** se define como el espacio de visibilidad de una variable, es decir, que no es posible verla y acceder a su valor fuera del scope en el que fue declarada.

De este modo, la locación en donde una variable es definida dictará donde tenemos acceso a ella. JavaScript tiene:

- **global scope :** Variables definidas fuera de cualquier función, bloque (block) o module scope.

        const cancion = "Roxanne";
        // Aquí se puede acceder a la variable 'cancion'🕺🏽

        function myFunction() {
        // ¡Y aquí también!💃
        }

- **module scope :** Antes que los modulos, una variable declarada fuera de cualquier función es una variable global. En módulos, la variable esta oculta y no esta disponible para otros módulos a menos de que sea exportada explícitamente.

          // en ejemplo.js
          export { ejemplo, toList, take };

          // en app.js
         import { ejemplo, toList, toList } from "./ejemplo";

- **function scope :** Significa que los parametros y variables definidas en una funcion son visibles solo dentro de la misma, fuera de ella no se puede acceder a ellos.

        function hazAlgo(){
          let algo = 1;
          console.log(algo);
        }
        hazAlgo(); //undefined

- **block scope :** O también **scope de bloque**, se define por los **{ }**. Pero, ¿qué es un bloque? básicamente una estructura de código creada por llaves.

        let a = 'global scope';
        {
          let a = 'block scope';
        }
        console.log(a);
        //'global scope'

> Aquí el valor de a cuando es igual a 'block scope' se encuentra aislado en el block scope, mientras que cuando es igual a 'global scope', su scope es global!

- **lexical scope :** Es el acceso que tienen funciones internas a variables de la funcion que la contiene.

       function externa(){
          let serie = 'Paquita Salas';
          function interna(){
             console.log(serie.toUpperCase())//Esta funcion es capaz de acceder a los valores de la funcion que la contiene.
           }
          interna();
          //PAQUITA SALAS
        }

Ahora que hemos definido los diferentes tipos de scope podemos comenzar a hablar de `var`, `let`y `const`! 🥳🥳

## Tipos de variable

### var

En **ES6** ya tenemos varias formas de declarar nuestras variables. En **ES5** lo hacíamos con la palabra `var` como en el siguiente ejemplo:

      var = 'loquequieras'

Las variables con `var` son sometidas a **hoisting**, es decir, la declaración de la variable es 'levantada' hasta el inicio del código pero la asignación al valor permanece en el sitio donde se realice.

Si intentamos acceder a su valor antes de que se asigne, obtendremos **undefined**:

     console.log(v); // undefined
     var v = 0;

>Si el hoisting no sucediera, la consola devolvería un 'ReferenceError: v is not defined'.

Todo esto muy bien pero el problema de `var` es el scope que genera, es decir el ámbito que crea para la variable en cuestión ya que **su scope esta definido por la función (function scope).**

      function imprime(matriz) {
        for (var i = 0; i < matriz.length; i++) {
           var line = matriz[i];

           for (var i = 0; i < line.length; i++) {
               var element = line[i];
               console.log(element);
            }
        }
    }

     var matriz = [
       [1, 2, 3],
       [4, 5, 6],
       [7, 8, 9]
     ];

     imprime(matriz);// ❌ 1 2 3

La primera impresión es que, para el segundo for loop, se esta creando una nueva variable **i**, pero en realidad lo que esta sucediendo es que se utiliza la misma variable para ambos for loops, por lo que para el segundo loop, la variable es igual a 3 (el 'length' de la primera línea de la matriz), la condición vuelve 'false', el loop para y solo se imprime 1 2 3.

### ¿Por qué no deberíamos usar var?

Porque con la introducción de `let`, `const` y el **block scope** se puede trabajar más fácilmente a la hora de declarar variables como hemos visto en el ejemplo anterior. E incluso otros lenguajes de programación si que cuentan con el **Block scope** también!

> Por lo tanto, se recomienda dejar de usar var y de esta forma, reemplazarla por let y const.

### let

`let` funciona de manera similar a `var`, lo único que como variable de bloque **(posee un block scope)**.

Asimismo, estas son variables que **pueden mutar el 'binding' con su valor** y ser reasignadas:

       let animal;
       animal = 'PavoReal';  🦚
       animal = 'Loro'; 🦜
       console.log(animal); // ✅ 'Loro' 🦜

El hoisting que habiamos comentado antes  no sucede con las variables let y const, con ellas siempre se obtendrá un 'ReferenceError' si se intenta acceder a su valor antes de ser declaradas:

     console.log(animal); // ReferenceError: animal is not defined
     let animal = 'Loro'; 🦜

### const

`const` tiene un funcionamiento parecido a let, con la diferencia de que el valor de una variable `const` no puede cambiarse a través de la reasignación, y no se puede redeclarar. Fue pensado para asignar valores que no queremos muta y que sabemos que son constantes.

En otras palabras, `const` significa que el 'binding' (la asociación entre el nombre de la variable y su valor) es inmutable. **El valor en si puede mutar.**

//ejemplo 1

       const animal;
       animal = 'PavoReal';  🦚
       animal = 'Loro'; 🦜
       console.log(animal); // ❌ VM418:1 Uncaught SyntaxError: Identifier 'animal' has already been declared...

//ejemplo 2

      const influencer = {
          name: 'Belén'
       }

       person.name = 'Belén Esteban' // ✅

Aquí se puede observar cómo valores declarados con `const` si pueden ser mutados.

### Decidiendo entre let y const

Para decidir es recomendado seguir las siguientes dos reglas:

- Prefiere usar `const` ya que indica un binding inmutable y que el valor de la variable no cambiará. 

- Usa `let`cuando no puedas usar const`.


Y para resumir:

| Tipo de variable | Características | Scope |
| ---------------- | -------------------------------------------------------------------- | ----- | 
| Var              | Nos permite mutar el valor de una variable en cualquier punto. También son 'hoisted'                                                        |    Function Scope   |
| Let              | Crea un scope y evita que podamos sobre escribir valores fuera de su scope. También se puede cambiar su valor.       No son 'hoisted'                                                                                |    Block Scope   |
| Const            | Fue pensado para asignar valores que no queremos muta y que sabemos que son constantes. No son 'hoisted'          |    Block Scope     |
