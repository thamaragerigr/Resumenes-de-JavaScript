# 💡 Lección 3: Condicionales y operadores lógicos

* [Condicionales](#💡Lección-3-:-Condicionales) 
   1. [if](#if)
   2. [else](#else) 
   3. [if else if else](#if-else-if-else)
   4. [switch](#switch)
   5. [ternary operator](#ternary-operator)
    
Los condicionales son partes de código que determinan si algo se ejecutará o no. 

Por regla general, las declaraciones en JavaScript son ejecutadas en secuencia desde arriba para abajo. El flujo de ejecución puede ser alterado de dos maneras:

* Condicionales
* Ejecución repetitiva (loops)

Existen diferentes tipos de condicionales en JS:

### if 

Dicta que si la condición es verdadera, el bloque de código que le sigue será ejecutado. Para crear un *if statement*, utilizamos la palabra 'if' seguida de la condición entre paréntesis y el bloque de código a ejecutar entre llaves ({}).

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
Como habiamos comentado anteriormente, si la condición se cumple el promer bloque de código será el que se ejecutará. De no ser así, es aconsejable escribir una alternativa para siempre evitar errores en el código. Esto puede ser logrado con *else*

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

### if else if else

T
- if else if else this specifies a new test if the first condition is false.On our daily life, we make decision on daily basis. We make decision not by checking one or two conditions instead we make decisions based on multiple conditions. As similar to our daily life, programming is also full conditions. We use else if when we have multiple conditions.

- switch Switch is an alternative for if else if else else. The switch statement starts with a switch keyword followed by a parenthesis and code block. Inside the code block we will have different cases. Case block run if the value in the switch statement parenthesis match with the case vale. The break is to terminate and it does not go down after the condition is satisfied. The default block run if all the cases don't satisfy the condition.

- operadores ternarios (ternary operators)Another way to write conditionals is using ternary operators. We have covered this in other sections but we should also mention it here.




switch
ternary operator
