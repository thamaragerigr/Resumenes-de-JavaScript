# Métodos de Arrays

## forEach(🍑) *its peach*

Acepta una **callback** y lo ejecuta en **cada elemento** del array

        const cosasPeligrosas = [🔪,💣,🗡,🔫,🕷];
        cosasPeligrosas.forEach(function (cosaPeligrosa){
            console.log(cosaPeligrosa);
        })
        //🔪
        //💣
        //🗡
        //🔫 ...

Utilizar ‘for of’ daría el mismo resultado:

    for (let cosaPeligrosa of cosasPeligrosas){
       console.log(cosaPeligrosa);
    }
    //🔪
    //💣
    //🗡
    //🔫
    …

## map(🗺️)

Crea un **nuevo array** con el resultado de haber llamado una **callback** en cada elemento del array.

    const slangMillennial = ['btw','lol','omg','ttyl'];
    const slangMillennialEnMayuscula = slangMillennial.map(function (slang){
        return slang.toUpperCase();
    })
    slangMillennialEnMayuscula;//['BTW','LOL','OMG','TTYL']

## find(📍)

Devuelve el valor del **primer elemento** del array que cumpla con los parámetros de la función.

    lconst pelis = [
        "👸🐸",
        "🔪🚿👩",
        "👑🎙️🎶",
        "🌎🐒🐒🐒"
    ]
    const musical = pelis.find(peli => {
        return peli.includes('🎶');
    })

## filter(👓)

Crea un **nuevo array** con todos los elementos que cumpla con los parámetros de la función.

    const num = [9,8,7,6,5,4,3,2,1];
    const oods = nums.filter(n => {
    return n % 2 ===2;//la callback devuelve true o false
    //si devuelve true, n se incluye en el array filtrado
    })
    //9,7,5,3,1
    const smallNums = nums.filter(n => n < 5);
    //4,3,2,1

## some(🧑‍🤝‍🧑) & every(🤼)

Ambos son métodos **booleanos** (devuelven true o false).

**Every** acepta una callback que en sí es boleano, prueba si todos los elementos de un array pasan los parámetros de la funcción.

    const words = ['dog','dig','log','bag','wag'];
    const all3Lets = words.every(word => word.length === 3);
    const allEndInG = words.every(word =>{
    const last = word.length -1;
    return word[last] === 'g'
    })
    //true

**Some** es igual a Every pero devuelde true si alguno de los elementos del array cumple con los parámetros de la función.

    const words = ['dog','dig','log','bag','wag'];
    const all3Lets = words.every(word => word.length === 3);
    const someStartWithD = words.some(word => word[0] ==='d');
    //true

## sort(🗂️)

    const prices = [400, 30,99,35,12];
    prices.sort();
    //[12,30,35,400,99] no aparecen en el orden correcto

Para personalizar el método .sort() se tiene que agregar una función comparadora (‘compareFunc(a,b)’):

- Si ‘compareFunc(a,b)’ devuelve menos de 0 (número negativo) → ordenar a antes que b.
- Si ‘compareFunc(a,b)’ devuelve 0 → deja a y b sin cambiar.
- Si ‘compareFunc(a,b)’ devuelve más de 0 (número positivo)→ ordenar b antes que a.

---

    const prices = [400, 3000,99,35,12];
    prices.sort();
    //orden ascendiente
    const ascsort1 = prices.sort((a,b) => a - b);
    a     b
    400   3000 - //se quedan iguales porque 400(a) se ordena antes que 3000(b)
    35     12  + //coloca a 12(b) antes que 35(a) porque el número es positivo
    //orden descendiente
    const descsort1 = prices.sort((a,b) => b - a);
    b      a
    3000   400 + //coloca a 3000(b) antes que 400(a) porque el número es positivo
    12     35  - //coloca a 12(b) después que 35(a) porque el número es negativo

> IMPORTANTE: sort hace un update del array, NO crea uno diferente con el nuevo orden

## reduce(♻️)

Ejecuta una función reductiora en cada elemento del array, resultando en un solo valor.

    [3,5,7,9,11].reduce((accumulator, currentValue)=>{
    return accumulator + currentValue;
    })

| Callback    | accumulator | currentValue | return value |
| ----------- | ----------- | ------------ | ------------ |
| first call  | 3           | 5            | 8            |
| second call | 8           | 7            | 15           |
| third call  | 15          | 9            | 24           |
| fourth call | 24          | 11           | 35           |

También se puede utilizar para encontrar el máximo valor en un array.

    const grades = [87,64,96,92,88,99,73,70,64];

    const maxGrade = grades.reduce((max,currVal)=>{
    if(currVal > max) return currVal;
    return max:
    })

    //max  currVal return
    //87    64      87
    //87    96      96
    //96    92      96...

    //maxGrade
    //99

El mismo resultado se puede obtener utilizando Math.min/max

    const grades = [87,64,96,92,88,99,73,70,64];

    const maxGrade = grades.reduce((max,currVal)=>{
    return Math.max(max,currVal):
    })
    //99
    const minGrade = grades.reduce((min,currVal)=>{
    return Math.min(min,currVal):
    })
    //64

También se puede especificar el valor con el que comienza el reduce

    const sum = [10,20,30,40,50].reduce((sum,currVal)=>{
    return sum + currVal;
    },1000)

## pop(🍿)

Remueve el último elemento de un array y devuelve ese elemento. Cambia la longitud del array.

    let gatos = ['Bob', 'Willy', 'Mini'];
    console.log(gatos.pop()); // 'Mini'
    console.log(gatos); // ['Bob', 'Willy']

## push(🚲)

Añade uno o más elementos al final de un array y a diferencia de pop(), devuelve la nueva longitud del array

    const animales = ['cerdo', 'cabra', 'oveja'];
    const cuenta = animals.push('vaca');
    console.log(cuenta); // 4
    console.log(animales); // ['cerdo', 'cabra', 'oveja', 'vaca]

## shift(➖)

Remueve el primer elemento de un array y devuelve ese elemento. Cambia la longitud del array.

    const miPescado = ['ángel', 'payaso', 'mandarín', 'cirujano'];
    const eliminado = miPescado.shift(); 
    console.log('Elemento eliminado: ' + eliminado);  // "Elemento eliminado: ángel"

## unshift(➕)

Añade uno o más elementos al inicio  de un array y a diferencia de pop(), devuelve la nueva longitud del array

    const array1 = [1, 2, 3];

    console.log(array1.unshift(4, 5));
    // expected output: 5

    console.log(array1);
    // expected output: Array [4, 5, 1, 2, 3]

## splice(💅)

Cambia el contenido de un array eliminando elementos existentes y/o agregando nuevos elementos.

    const months = ['Jan', 'March', 'April', 'June'];
    months.splice(1, 0, 'Feb');
    // inserts at index 1
    console.log(months);
    // expected output: Array ["Jan", "Feb", "March", "April", "June"]

## slice(🍰)

 Devuelve una copia de una parte del array dentro de un nuevo array empezando por inicio hasta fin (fin no incluido). El array original no se modificará.

    const nombres = ['Rita', 'Pedro', 'Miguel', 'Ana', 'Vanesa'];
    const masculinos = nombres.slice(1, 3);

    // masculinos contiene ['Pedro','Miguel']

- toString()
- join()
- concat()
- includes()
- join()
- findIndex( )
- indexOf( )
- fill( )
- reverse()