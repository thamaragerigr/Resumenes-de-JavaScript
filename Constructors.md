# 💡 Clases y Constructors

<!-- * Classes in JavaScript are a special syntax for its prototypical inheritance model that is a comparable inheritance in class-based object oriented languages. Classes are just special functions added to ES6 that are meant to mimic the class keyword from these other languages. In JavaScript, we can have class declarations and class expressions, because they are just functions. So like all other functions, there are function declarations and function expressions.

* Classes serve as templates to create new objects.

* The most important thing to remember: Classes are just normal JavaScript functions and could be completely replicated without using the class syntax. It is special syntactic sugar added in ES6 to make it easier to declare and inherit complex objects.

* To declare a class, we use the class keyword.

* Class declarations aren’t hoisted so they can’t be used before they are defined in the code, as the JavaScript interpreter will not automatically pull them up to the top.

* We can also define a class by a class expression, which is an alternative syntax. They can be named or unnamed. We can also assign a class to a variable like we do with functions. 

    let Person = class {
    constructor(firstName, lastName) {
        this.firstName = firstName;
        this.lastName = lastName;
    }
    }

* Classes in JavaScript also have a constructor method that lets us set fields when the object is instantiated with a class. Each class can only have one constructor method in it

* A constructor can also call the super method to call the constructor of the super class if the class extends a parent class. -->

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


<!-- Getters and Setters

JavaScript classes can have getter and setter functions. Getters, as the name suggests, is a method that lets us get some data from a class. Setters are methods that gives us the ability to set some fields of the class. We denote getter functions with the get keyword and setters with the set keyword

JavaScript Inheritance

In JavaScript, we can create classes where the properties can be included in the properties of a child class.
So, we can have a high-level class that contains the properties that are common to all the child classes, and the child class can have its own special properties that are not in any other classes.  

with the èxtends`keyword -->