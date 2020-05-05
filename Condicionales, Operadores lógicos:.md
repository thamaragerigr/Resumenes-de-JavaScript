# 💡 Lección 3: Condicionales y operadores lógicos

- [Condicionales](#💡Lección-3-:-Condicionales)
  1.  [if](#if)
  2.  [else](#else)
  3.  [switch](#switch)
  4.  [ternary operator](#ternary-operator)
- [Operadores Lógicos](#Operadores-Lógicos-y-de-comparación)

Los condicionales son partes de código que determinan si algo se ejecutará o no.

Por regla general, las declaraciones en JavaScript son ejecutadas en secuencia desde arriba para abajo. El flujo de ejecución puede ser alterado de dos maneras:

- Condicionales
- Ejecución repetitiva (loops)

Existen diferentes tipos de condicionales en JS:

### if

Dicta que si la condición es verdadera, el bloque de código que le sigue será ejecutado. Para crear un _if statement_, utilizamos la palabra 'if' seguida de la condición entre paréntesis y el bloque de código a ejecutar entre llaves ({}).

        if (condition) {
            //  block of code to be executed if the condition is true
        }
        -------------------------------------------------------------
        if ( número == 1 ) {
          saludo = "Buenos días";
          console.log(saludo);
        }

        //"Buenos días"

### else

Como habiamos comentado anteriormente, si la condición se cumple el promer bloque de código será el que se ejecutará. De no ser así, es aconsejable escribir una alternativa para siempre evitar errores en el código. Esto puede ser logrado con _else_

        if (condition) {
            //  block of code to be executed if the condition is true
        } else {
           //  block of code to be executed if the condition is NOT true
        }
        -------------------------------------------------------------
        if ( número == 1 ) {
          saludo = "Buenos días";
          console.log(saludo);
        } else {
            saludo = "Buenas tardes";
            console.log(saludo);
        }

> También es posible añadir otro condicional _if_ luego del _else_.

### Switch

Este condicional nos permite Realizar varias elecciones dentro de un mismo _statement_ de manera más eficiente. En este caso se toma una sola expresión y luego se verifica a través de una serie de opciones hasta que encuentran una que coincida con ese valor, ejecutando el código correspondiente.

      switch (expresión) {
        case opción1:
          ejecuta este código
          break;

        case opción2:
          ejecuta este código
          break;

        // Se pueden incluir todos los casos que quieras

        default:
          código predeterminado a ejecutarse
      }


       Ejemplo:

        const estación = mes => {
        switch (mes) {
            case 'septiembre' :
            case  'octubre' :
            case  'noviembre':
                console.log('Otoño');
                break;
            case 'diciembre':
            case 'enero':
            case 'febrero':
                console.log('Invierno');
                break;
            case 'marzo':
            case 'abril':
            case 'mayo':
                console.log('Primavera');
                break;
            case 'junio':
            case 'julio':
            case 'agosto':
                console.log('Verano');
                break;
            default:
                console.log("No has introducido el mes!");
                break;
        };
        };

        checkSeason('abril');
        //Primavera


## Operadores Lógicos y de Comparación

### De comparación

Estos son utilizados para determinar la igualdad o diferencia entre valores. 

    ==   equal to
    ===  equal value and equal type
    !=   not equal
    !==  not equal value or not equal type
    >    greater than
    <    less than
    >=   greater than or equal to
    <=   less than or equal to

### Lógicos

Son útiles para realizar múltiples comprobaciones y reducir las líneas de código. En JavaScript existen tres tipos de estos, ! (NOT), && (AND), ||(OR).

**! - NOT:** Indica que solo se ejecutará el código si el *statement* es falso.

    !(x == y) is true

**&& — AND:** Ambas expresiones tienen que ser verdaderas para que se pueda ejecutar el código.

    (x < 10 && y > 1) is true

**|| — OR:** Solo una de ellas tiene que ser verdadera para que se ejecute el código.

	(x == 5 || y == 5) is false