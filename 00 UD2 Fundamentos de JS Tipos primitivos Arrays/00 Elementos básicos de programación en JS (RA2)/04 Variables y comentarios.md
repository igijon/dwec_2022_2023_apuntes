# Variables y comentarios
#javascript
- **Variable**: contenedor de información que apunta a un contenedor de memoria y puede variar en el futuro.
- **ES5:** soportado por la mayoría de los navegadores web.
- **ES6 (2015), 2016, 2017…** pierde la compatibilidad con navegadores muy muy viejos. Muchas características pueden ser implementadas con **polyfill** que permite ejecutar características modernas en versiones viejas de JS.

```jsx
// console.log('Hola mundo');

let a = 10; //Aquí creo una variable y le asigno el valor 10
var b = 10;  // Aquí creo una variable y le asigno el valor 10. 
// Var era la forma antigua de crear variables. Se mantiene por compatibilidad.
const c = 10; //Hace referencia a un valor de memoria que no cambia

//Esto dará error
// c = 20;

//Esto no da error
// a = 20;
// b = 30;

let d = 10, e = 20, f = 4;
```

```jsx
// console.log('Hola mundo');

let a = 10; //Aquí creo una variable y le asigno el valor 10
var b = 10;  // Aquí creo una variable y le asigno el valor 10. 
// Var era la forma antigua de crear variables. Se mantiene por compatibilidad.
const c = 10; //Hace referencia a un valor de memoria que no cambia

//Esto dará error
// c = 20;

//Esto no da error
// a = 20;
// b = 30;

let d = 10, 
    e = 20, 
    f = 4;
```

<aside>
💡 Cuanto usamos `var` se coloca dentro de un objeto global llamado `window`. Esto no es buena práctica actualmente.

</aside>