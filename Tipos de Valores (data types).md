# 💡Lección 1: Tipos de Valores (data types)

## 

Los tipos de data o valores pueden dividirse en dos grupos:

* [Primitivos](#Primitivos) *(Primitive data types)*
   1. [Números](#Números)
   2. [Cadenas de texto](#Cadenas-de-texto) *(Strings)*
   3. [Booleans](#Booleans)
   4. [Undefined](#Undefined)
   5. [Null](#Null)
   6. [Symbol](#Symbol)

* [No Primitivos](#No-Primitivos) *(Non-primitive data types)*
   1. [Arrays](#Arrays)
   2. [Funciones](#Funciones)
   3. [Objetos](#Objetos)
    
---
## Primitivos

  Los tipos de datos **Primitivos son inmutables**, es decir, que no pueden ser modificados una vez que son creados. 

### Números: 
  JavaScript tiene solo un tipo de **valor numérico**. Pueden ser positivos o negativos, enteros o decimales. 


Existen tres valores numéricos especiales:

  * infinity
  * -infinity
  * NaN (Not a Number)


**NaN**:  valor numérico para representar algo que no es un número


    0/0 //NaN
    1 + NaN//NaN

> 🤓 Nota: NaN es el único valor que no es igual a si mismo. Esto se debe a que NaN representa el resultado de una ‘nonsensical computation’, por lo tanto no es igual a cualquier otra de su tipo.

    console.log( NaN == NaN)//false

**Infinity/-Infinity** : valor infinito (también pude ser negativo igual que el -0)


    1/0//Infinity
    -0//-0

### Cadenas de texto
Los valores textuales en JavaScript representan una **serie de carácteres** dentro de una **cadena** *('string')*. Se escriben con comillas alrededor:

     'Loquesea'
     "Me gustan las mandarinas"
     `¡¡A tope con el JavaScript!!`

> ⚠️ Se pueden utilizar comillas simple, dobles o 'backticks'( `` ), siempre y cuando se use el mismo tipo al abrir y cerrar.



Las cadenas de texto pueden ser **concatenadas**, es decir juntarlas entre si usando el símbolo de +:

     'con'+'cat'+'e'+'nar'

También existen los **template literals**, los cuales permiten introducir otros valores dentro de la misma cadena de texto: 
     
     
       `half of 100 is ${100/2}`

### Booleans

Son valores que distinguen entre dos posibilidades únicamente, `true` y `false`

     console.log(3 > 2)
     //true
     console.log('itchy' = 'scratchy')
     //false

 Los valores tienen por defecto un valor booleano y se clasifican en *Truthy *  y *Falsy*

 **Valores Truthy**: Todos los valores son truthy (números positivos y negativos, todas las cadenas de texto y el `true` booleano) a menos de que sean definidos como falsy o en el caso de algunas excepciones.


>⚠️ Algunos valores truthy interesantes son : el cero y la palabra false como cadenas de texto ('0', 'false'). También lo son un array vacio ([]), un objeto vacio ({}) y una función vacía ( function(){} ).

**Valores Falsy**: El único valor numérico *falsy* es el 0 (sin comillas!). Tambien 0n, null, undefined, NaN, el `false` booleano y las comillas vacías ( ' ', " " ).


### Undefined
 Se refiere a las variables a las que todavía no se les ha asignado un valor. 

    let firstName
    console.log(firstName)
    //undefined 

### Null
 Son variables o valores vacios. 

     let empty = null
     console.log(empty) 
     //null 


### Symbol
Representa un identificador único. Son constantes que tienen algunas propiedades extras, que nos permiten trabajar mejor en debug y guardar valores.

    var dos = Symbol("foo");
    var tres = Symbol("foo");

[Leer más del tema](https://javascript.info/symbol)


---
## No Primitivos
Este tipo de valores pueden ser modificados y tienen la capacidad de mutar.

Las variables a las que se les asignan estos valores obtienen una referencia que se guarda en la memoria (esta referencia apunta a la ubicación del objeto). Es decir, que las variables en realidad no contienen estos valores.


### Arrays
Son colecciones ordendas de valores, cada valor dentro de ellos posee una posición númerica (** index **).Son utitlizados para almacenar listas de elementos y acceder a ellos en una misma variable 

    let frutasGuays = ["Manzana", "Fresa", "Mandarina"];

Tambíen se pueden reemplazar objetos, o agregar o quitar elementos.
    
     let frutasGuays[2] = 'Mora'; // ["Manzana", "Fresa", "Mora"];

     let frutasGuays[3] = 'Banana'; // ["Manzana", "Fresa", "Mora", "Banana"];

Dentro de estos se pueden almacenar cualquier tipo de valor, ya sean strings, booleans o números, incluso objetos u otros arrays

    let cosas = [ 82, true, 'Domingo'];

### Funciones
Una función es conjunto de ** declaraciones que realiza una tarea o calcula un valor. **

Son objetos de primera clase, es decir, son objetos y se pueden manipular y transmitir al igual que cualquier otro objeto. Concretamente son objetos `Function`.

    function nombre([param[,param[, ...param]]]) {
        instrucciones
     }


### Objetos
Es una colección de datos relacionados y / o funcionalidad (que generalmente consta de varias variables y funciones, que se denominan propiedades y métodos cuando están dentro de objetos).

     const persona = {
      nombre: ['Pepito', 'Pérez'],
      edad: 12,
      genero: 'masculino',
      intereses: ['patinar', 'dormir'],
      saludo: function() {
      alert('Hola, Soy '+ this.nombre[0] + '. ');
      }
    };

