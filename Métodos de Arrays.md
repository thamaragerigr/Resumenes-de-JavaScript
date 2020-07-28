# Métodos de Arrays (explicados con ✨emojis✨ 🤫)

Aquí traigo un resumen de los métodos para Arrays más usados en js y explicados con emojis (porque con ellos ¡la vida es mejor!).

## forEach(🍑) _its peach_

Acepta una **callback** y lo ejecuta en **cada elemento** del array

    const cosasPeligrosas = ['🔪','💣','🗡','🔫','🕷'];

    cosasPeligrosas.forEach(function (cosaPeligrosa){
        console.log(cosaPeligrosa);
    })

    //🔪
    //💣
    //🗡
    //🔫
    //🕷

Utilizar **‘for of’** daría el mismo resultado:

    for (let cosaPeligrosa of cosasPeligrosas){
        console.log(cosaPeligrosa);
    }

    //🔪
    //💣
    //🗡
    //🔫
    //🕷

## map(🗺️)

Crea un **nuevo array** con el resultado de haber llamado una **callback** en cada elemento del array.

    const slangMillennial = ['btw','lol','omg','ttyl'];

    const slangMillennialEnMayuscula = slangMillennial.map(function (slang){
        return slang.toUpperCase();
    })

    slangMillennialEnMayuscula;//['BTW','LOL','OMG','TTYL']

## find(📍)

Devuelve el valor del **primer elemento** del array que cumpla con los parámetros de la función.

    const pelis = [
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

    const cosasPerdidas = ['🔑',8,'🦄',6,'💄',4,'🧩',2,1]

    const números = cosasPerdidas.filter(cosa => {
        return typeof cosa === 'number'
        //la callback devuelve true o false
        //si devuelve true, n se incluye en el array filtrado
    })

    números // [8, 6, 4, 2, 1]

## some(🧑‍🤝‍🧑) & every(🤼)

Ambos son métodos **booleanos** (devuelven true o false).

**Every** acepta una callback que en sí es boleano, prueba si todos los elementos de un array pasan los parámetros de la funcción.

    const palabras = ['sal','mar','dar','sol','dos']

    const palabrasDeTresLetras = palabras.every( palabra => palabra.length === 3 )

    //true 👏👏

**Some** es igual a Every pero devuelde true si alguno de los elementos del array cumple con los parámetros de la función.

    const palabras = ['sal','mar','dar','sol','dos']

    const algunasComienzanPorS = palabras.some( palabra => palabra[0] ==='s' )

    //true 👏👏

## sort(🗂️)

    const precios = [400, 30,99,35,12]

    precios.sort()

    //[12,30,35,400,99] no aparecen en el orden correcto

Para personalizar el método .sort() se tiene que agregar una función comparadora (‘compareFunc(a,b)’):

- Si ‘compareFunc(a,b)’ devuelve menos de 0 (número negativo) → ordenar a antes que b.
- Si ‘compareFunc(a,b)’ devuelve 0 → deja a y b sin cambiar.
- Si ‘compareFunc(a,b)’ devuelve más de 0 (número positivo)→ ordenar b antes que a.

---

    const precios = [400, 3000,99,35,12];
    precios.sort();
    //orden ascendiente
    const ascsort1 = precios.sort((a,b) => a - b);
    a     b
    400   3000 - //se quedan iguales porque 400(a) se ordena antes que 3000(b)
    35     12  + //coloca a 12(b) antes que 35(a) porque el número es positivo
    //orden descendiente
    const descsort1 = precios.sort((a,b) => b - a);
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

    const maxGrade = grades.reduce((max,currVal) => {
        return Math.max(max,currVal):
    })

    //99

    const minGrade = grades.reduce((min,currVal) => {
      return Math.min(min,currVal):
    })

    //64

También se puede especificar el valor con el que comienza el reduce

    const sum = [10,20,30,40,50].reduce((sum,currVal) => {
      return sum + currVal;
    },1000)

## pop(🍿)

Remueve el último elemento de un array y devuelve ese elemento. Cambia la longitud del array.

    const cinema = ['🎥', '🎬', '🎞️']

    console.log(cinema.pop()); // '🎞️'

    console.log(cinema); // ['🎥', '🎬']

## push(🚲)

Añade uno o más elementos al final de un array y a diferencia de pop(), devuelve la nueva longitud del array

    const animales = ['🐷', '🐮', '🐔']

    const granja = animales.push('🚜')

    console.log(granja); // 4

    console.log(animales); // ['🐷', '🐮', '🐔','🚜']

## shift(➖)

Remueve el primer elemento de un array y devuelve ese elemento. Cambia la longitud del array.

    const pescados = ['🦑','🐟', '🐠', '🐡']

    const eliminado = pescados.shift()

    console.log('Elemento eliminado: ' + eliminado); // "Elemento eliminado: '🦑'

## unshift(➕)

Añade uno o más elementos al inicio de un array y a diferencia de pop(), devuelve la nueva longitud del array

    const miMaleta = ['👔','👙', '🧦','👢','🧣']

    console.log(miMaleta.unshift('🩲'))

    // 6

    console.log(miMaleta)

    // Array ['🩲','👔','👙', '🧦','👢','🧣]

## splice(💅)

Cambia el contenido de un array eliminando elementos existentes y/o agregando nuevos elementos.

    const menuDelDía = ['🥗', '🥩', '🍜', '🌮']

    menuDelDía.splice(1, 1, '🥪')

    // (4) ["🥗", "🥪", "🍜", "🌮"]

Acepta tres parámetro:

    array.splice(index, howmany, item1, ….., itemX)

- index: Indica el índice de donde se empezarán a remover los ítems (puedes usar números negativos para indicar que comience por el final del array).
- howmany (opcional): Indica el número de ítems que serán removidos.
- item1, …, itemX (opcional): Son los elementos que serán añadidos al array.

## slice(🍰)

Devuelve una copia de una parte del array dentro de un nuevo array empezando por inicio hasta fin (**fin no incluido**). El array original no se modificará.

    const miOrden = ['🥧', '🎂', '🍩', '🧁', '🍮']

    const laOrdenDeMiHermana = miOrden.slice(1, 3)

    // ['🎂','🍩']
    
## toString(⛓️)

Devuelve una cadena que representa al objeto.

    function Comida( entrante, platoPrincipal, postre ) {
       this.entrante = entrante
       this.platoPrincipal = platoPrincipal
       this.postre = postre
    }

    comidaDelLunes = new Comida("🥗","🍝","🍧")

    comidaDelLunes.toString() //devuelve [object Object]

¡Y todavía faltan más!

✨¡Espero que te haya ayudado!✨

[< Volver al índice](https://github.com/thamaragerigr/Resumenes-de-JavaScript)

<!-- - toString()
- join()
- concat()
- includes()
- join()
- findIndex( )
- indexOf( )
- fill( )
- reverse() -->
