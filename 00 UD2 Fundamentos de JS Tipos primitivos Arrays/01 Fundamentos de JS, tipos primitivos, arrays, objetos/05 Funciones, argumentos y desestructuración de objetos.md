#javascript
# Funciones, argumentos y desestructuración de objetos

<aside>
💡 Todo este código es lo mismo

</aside>

```jsx
function crearPersona(nombre, apellido) {
    return {
        nombre: nombre,
        apellido: apellido
    }
}

const persona = crearPersona( 'Inma', 'Gijón');

console.log( persona );
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Funciones,%20argumentos%20y%20desestructuración/Untitled.png)

```jsx
function crearPersona(nombre, apellido) {
    return {
        nombre,
        apellido
    }
}

const persona = crearPersona( 'Inma', 'Gijón');

console.log( persona );
```

```jsx
function crearPersona(nombre, apellido) {
    return { nombre, apellido }
}

const persona = crearPersona( 'Inma', 'Gijón');

console.log( persona );
```

```jsx
// function crearPersona(nombre, apellido) {
//     return { nombre, apellido }
// }

//para que devuelva el resultado correcto debe ir entre paréntesis
const crearPersona = ( nombre, apellido ) => ({nombre, apellido});

const persona = crearPersona( 'Inma', 'Gijón');

console.log( persona );
```

```jsx
function imprimeArgumentos() {
    console.log( arguments);
}

imprimeArgumentos( 10, true, false, 'Pepe', 'Hola');
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Funciones,%20argumentos%20y%20desestructuración/Untitled%201.png)

```jsx
function imprimeArgumentos() {
    console.log( arguments);
}

//Los tres puntos le indican que todos los argumentos que reciban, es un parámetro rest
//Despùés de ese parámetro no puedo añadir nada
const imprimeArgumentos2 = ( edad,...args ) => {
    console.log( {edad, args} );
}

imprimeArgumentos( 10, true, false, 'Pepe', 'Hola');
imprimeArgumentos2(10, true, false, 'Pepe', 'Hola');
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Funciones,%20argumentos%20y%20desestructuración/Untitled%202.png)

```jsx
function imprimeArgumentos() {
    console.log( arguments);
}

//Los tres puntos le indican que todos los argumentos que reciban, es un parámetro rest
//Despùés de ese parámetro no puedo añadir nada
const imprimeArgumentos2 = ( edad,...args ) => {
    // console.log( {edad, args} );
    return args;
}

imprimeArgumentos( 10, true, false, 'Pepe', 'Hola');
const argumentos = imprimeArgumentos2(10, true, false, 'Pepe', 'Hola');
console.log( { argumentos }); //Obtengo los argumentos a partir del booleano
```

# Desestructuración

```jsx
function imprimeArgumentos() {
    console.log( arguments);
}

//Los tres puntos le indican que todos los argumentos que reciban, es un parámetro rest
//Despùés de ese parámetro no puedo añadir nada
const imprimeArgumentos2 = ( edad,...args ) => {
    // console.log( {edad, args} );
    return args;
}

imprimeArgumentos( 10, true, false, 'Pepe', 'Hola');
// const argumentos = imprimeArgumentos2(10, true, false, 'Pepe', 'Hola');
// console.log( { argumentos });
const [ casado, vivo, nombre, saludo ] = imprimeArgumentos2(10, true, false, 'Pepe', 'Hola');
console.log( { casado, vivo, nombre, saludo });
```

```jsx
//Si sólo me interesase el apellido aunque devuelva las dos cosas
const {apellido} = crearPersona('Inma', 'Gijón');

console.log( {apellido });
```

Si le quiero cambiar el nombre a la variable:

```jsx
//Si sólo me interesase el apellido aunque devuelva las dos cosas
const {apellido: nuevoApellido} = crearPersona('Inma', 'Gijón');

console.log( {nuevoApellido });
```

```jsx
const imprimePropiedades = ( personaje ) => {
        console.log( 'nombre ', personaje.nombre );
        console.log( 'codeName', personaje.codeName );
        console.log( 'vivo', personaje.vivo );
        console.log( 'edad', personaje.edad );
        console.log( 'trajes', personaje.trajes );
}

imprimePropiedades();
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Funciones,%20argumentos%20y%20desestructuración/Untitled%203.png)

```jsx
//si no viene la edad, coge el valor por defecto
const imprimePropiedades = ( { nombre, codeName, vivo, edad = 15, trajes} ) => {
        console.log({nombre});
        console.log({codName});
        console.log({vivo});
        console.log({edad});
        console.log({trajes});
}
imprimePropiedades();
```