# Tipos de datos primitivos
#javascript
- JS es un lenguaje débilmente tipado, infiere el tipo de datos.
- Información que no es un objeto y son inmutables. Los valores pueden ser reasignados pero no se puede cambiar el valor como lo haría un objeto.

- Tipos:
    - Boolean: true / false.
    - Null: sin valor
    - Undefined: variable declarada pero sin valor
    - Number: integer, floats…
    - String: cadena de caracteres
    - Symbol: tipo de dato con valor único (lo veremos más adelante).
    

```jsx
let nombre = 'Peter Parker';
console.log( nombre );

nombre = 'Ben Parker'; //Más ligero que el doble
console.log( nombre );

nombre = "Tía May"; //A veces este hace que sea más fácil de ver
nombre = `Tía May`; //Back tick

console.log( typeof nombre);

nombre = 123;
console.log( typeof nombre );

let esMarvel = true;
console.log( typeof esMarvel );

let edad = 33;
console.log( typeof edad );

edad = 33.034;
console.log( typeof edad );

//La mayor parte de los desarrolladores establecen como nomenclatura para la 
//declaración de variables, camelCase.
//snake_case por ejemplo es el estándar en Python.

let superPoder;
console.log( typeof superPoder ); //undefined

let soyNull = null;
console.log( typeof soyNull ); //object

let symbol1= Symbol('a');  //Los símbolos permiten crear identificadores únicos 
let symbol2 = Symbol('a'); 

console.log( typeof symbol1 );
console.log( symbol1 === symbol2 );
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Tipos%20de%20datos%20primitivos/Untitled.png)