# Métodos de Arrays

### forEach()

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

### map()

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

### find( )

Devuelve el valor del primer elemento del array que cumpla con los parámetros de la función.

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

### filter()
 
- toString()
- join()
- pop()
- push()
- shift()
- unshift()
- splice()
- concat()
- slice()
- sort()
-every( )
-some()
- includes()
- join()
- reduce()
- findIndex( )
- indexOf( )
- fill( )
- reverse( )