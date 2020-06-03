# Métodos de Arrays

### forEach(🍑)

Método de arrays, acepta una callback y lo ejecuta en cada elemento del array

    const numbers = [20,21,22,23,24,25,26,27];
    numbers.forEach(function (num){
    console.log(num);
    })
    //20
    //21
    //22
    //23
    ...

También se puede utilizar una función ya pre hecha

    const numbers = [20,21,22,23,24,25,26,27];
    function printTriple(n){
    console.log(n*3);
    }
    numbers.forEach(printTriple);
    //60
    //63
    //66
    //69
    ...

Utilizar ‘for of’ daría el mismo resultado:

    for (let num of numbers){
    console.log(n*3);
    }

### map(🗺️)

Crea un nuevo array con el resultado de haber llamado una callback en cada elemento del array.

    const texts = ['rofl','lol','omg','ttyl'];
    const caps = texts.map(function (t){
    return t.toUpperCase();
    })
    texts;//['rofl','lol','omg','ttyl']
    caps;//['ROFL','LOL','OMG','TTYL'];

    ///////////////////////////////////////////

    const numbers = [20,21,22,23,24,25,26,27];

    const numDetail = numbers.map(function(n){
    return{
    value:n,
    isEven:n % 2 === 0
    }
    })
    //1: {value:21,isEven:false}
    //2: {value:22,isEven:true}
    //3: {value:23,isEven:false}
    //4: {value:24,isEven:true}
    ...

Se podría hacer lo mismo de manera manual, pero se tiene que crear el array previamente.

    const doubles2 = [];
    for (let num of numbers){
    doubles2.push(num*2);
    }

### find(📍)

Devuelve el valor del **primer elemento** del array que cumpla con los parámetros de la función.

    let movies = [
    "The Fantastic Mr. Fox",
    "Mr. and Mrs. Smith",
    "Mrs. Doubtfire",
    "Mr. Deeds"
    ]
    //Encontrar la primera película que tenga 'mrs.'
    const movie = movies.find(movie => {
    return movie.includes('Mrs');
    })
    //Encontrar la primera película que empiece por  'mrs.'
    const movie2 = movies.find(m => m.indexOf("Mrs") === 0);

    /////////////////////////////////////////

    const books = [{
        title: 'Good Omens',
        authors: ['Terry Pratchett', 'Neil Gaiman'],
        rating: 4.25
    },
    {
        title: 'Bone: The Complete Edition',
        authors: ['Jeff Smith'],
        rating: 4.42
    },
    {
        title: 'American Gods',
        authors: ['Neil Gaiman'],
        rating: 4.11
    },
    {
        title: 'A Gentleman in Moscow',
        authors: ['Amor Towles'],
        rating: 4.36
    }
    ]
    //Encuentra un libro con un raiting mayor a 4.3
    const goodBook = books.find(b => b.rating >= 4.3);
    //El primer libro de Neil Gaiman como autor
    const neilBook = books.find(b => (
    b.authors.includes('Neil Gaiman')
    ))

### filter(👓)

Crea un **nuevo array** con todos los elementos que cumpla con los parámetros de la función.

    const num = [9,8,7,6,5,4,3,2,1];
    const oods = nums.filter(n => {
    return n % 2 ===2;//la callback devuelve true o false
    //si devuelve true, n se incluye en el array filtrado
    })
    //9,7,5,3,1
    const smallNums = nums.filter(n => n < 5);
    //4,3,2,1

### some(🧑‍🤝‍🧑) & every(🤼)

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

### sort(🗂️)

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

### reduce(♻️)

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

### pop(🍿)

Remueve el último elemento de un array y devuelve ese elemento. Cambia la longitud del array.

    let gatos = ['Bob', 'Willy', 'Mini'];
    console.log(gatos.pop()); // 'Mini'
    console.log(gatos); // ['Bob', 'Willy']

### push(🚲)

Añade uno o más elementos al final de un array y a diferencia de pop(), devuelve la nueva longitud del array

    const animales = ['cerdo', 'cabra', 'oveja'];
    const cuenta = animals.push('vaca');
    console.log(cuenta); // 4
    console.log(animales); // ['cerdo', 'cabra', 'oveja', 'vaca]

### shift(➖)

Remueve el primer elemento de un array y devuelve ese elemento. Cambia la longitud del array.

    const miPescado = ['ángel', 'payaso', 'mandarín', 'cirujano'];
    const eliminado = miPescado.shift(); 
    console.log('Elemento eliminado: ' + eliminado);  // "Elemento eliminado: ángel"

### unshift(➕)

Añade uno o más elementos al inicio  de un array y a diferencia de pop(), devuelve la nueva longitud del array

    const array1 = [1, 2, 3];

    console.log(array1.unshift(4, 5));
    // expected output: 5

    console.log(array1);
    // expected output: Array [4, 5, 1, 2, 3]

### splice(💅)

Cambia el contenido de un array eliminando elementos existentes y/o agregando nuevos elementos.

    const months = ['Jan', 'March', 'April', 'June'];
    months.splice(1, 0, 'Feb');
    // inserts at index 1
    console.log(months);
    // expected output: Array ["Jan", "Feb", "March", "April", "June"]

### slice(🍰)

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
