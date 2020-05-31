# Constructors

El método constructor es un metodo especial para crear e inicializar un objeto creado a partir de una clase.

Un constructor puede utilizar la palabra clave **super** para llamar al constructor de una clase padre.

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