# 💡Funciones

## Tipos de funciones

#### Function Statements

Son aquellas a las que se les asigna un nombre.

        function add() {
            return
        }

#### Function Expression

Aquí la función puede no tener nombre, sino que esta **guardada en una variable**. Esto es posible ya que las funciones **son objetos**, por lo que además de ser guardadas en una variable, también pueden serlo en un array o ser pasadas como argumento.

    const square = function(num) {
        retunr num * num;
    }
    square(7); // 49

#### Anónimas

Son funciones que no son guardadas en una variable ni tienen un nombre declarado.

Estas no se deben usar cuando: 

- Necesitas un nombre descriptivo para volver a usarla.

- Cuando las funciones son anónimas, estas son declaradas y salvadas en la memoria. Esto significa que cada vez que esta sea ejecutada, tomará un poco de espacia en la memoria, aumentando el 'computational power' necesitado para esa parte del código.

#### Flecha

Son una nueva manera de expresar las function expressions, de un modo resumido

        let mifuncion = () => {
        //código de la función
        }
 > ⚠️ Las funciones flecha NO tienen binding de la keyword this, por lo que esta no funcionará dentro de la misma, a menos que se haga explícitamente.

#### Higher Order Functions

Son funciones que operan con otras. Estas pueden:

- Aceptar otras funciones como argumento (Parameter functions)

        function callTwice(func) {
            func();
            func();
        }

        function laugh() {
            console.log('hahaha');
        }

        callTwice(laugh)
        //hahaha
        //hahaha

- Devolver funciones (Returning functions)

        function multiplyBy(x) {
            return function (x) {
            return x * num;
            }
        }

        multiplyBy(5);

        const triple = multiplyBy(3);


#### Callbacks
 
 Son funciones que son pasadas como argumento para ser invocadas dentro de la función externa.

        callTwice(laugh)//utilizada anteriormente

 > ⚠️ También se pueden utilizar funciones anónimas

        setTimeOut(function(){
            alert('welcome');
        }, 5000)

---

### Recap

- Una función es un subprograma diseñado para ejecutar una tarea en particular.
- Las declaraciones de las funciones son 'hoisted' - las inizializaciones no.
- Las funciones son ejecutadas cuando son llamadas - invocadas.
- Las funciones siempre devuelven un valor. Si no se especifica, esta devolverá undefined.
- Las funciones son objetos.

✨¡Espero que te haya ayudado!✨

[< Volver al índice](https://github.com/thamaragerigr/Resumenes-de-JavaScript)