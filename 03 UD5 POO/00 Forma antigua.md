# Forma antigua
#javascript
```jsx
const car = {
    nombre: 'Carlos',
    edad: 30,
    imprimir() {
        console.log(`Nombre: ${ this.nombre } - edad: ${ this.edad }`);
    }
}

const pedro = {
    nombre: 'Pedro',
    edad: 15,
    imprimir() {
        console.log(`Nombre: ${ this.nombre } - edad: ${ this.edad }`);
    }
}

//ESta funciión me va a permitir crear instancias y por
//eso la ponemos en mayúscula
function Persona(nombre, edad) {
    console.log('Se ejecutó esta línea');
    return;
}

//Con la palabra new indicamos que queremos crear una nueva instancia
//de Persona
const maria = new Persona('María', 15);
```

![Untitled](00%20🌎%20DWEC%202022-2023/03%20UD5%20POO/Anexos/Forma%20antigua%20b9e2e0896b894182849930bbc86b28dd/Untitled.png)

[Can I use... Support tables for HTML5, CSS3, etc](https://caniuse.com/)

<aside>
💡 `Prototype` nos da información de qué objeto hereda.

</aside>

```jsx
//Esto antes era el estándar de creación de objetos en JS pero ya no
//Si no indicamos que se debe crear con la palabra new, no se crearán
//instancias nuevas

//ESta funciión me va a permitir crear instancias y por
//eso la ponemos en mayúscula
function Persona(nombre, edad) {
    this.nombre = nombre;
    this.edad = edad;
    this.imprimir = function() {
        console.log(`Nombre: ${ this.nombre } - edad: ${ this.edad }`);
    }
}

//Con la palabra new indicamos que queremos crear una nueva instancia
//de Persona
const maria = new Persona('María', 15);
const melissa = new Persona('Melisssa', 35);
console.log(maria);
maria.imprimir();
melissa.imprimir();
```

![Untitled](00%20🌎%20DWEC%202022-2023/03%20UD5%20POO/Anexos/Forma%20antigua%20b9e2e0896b894182849930bbc86b28dd/Untitled%201.png)