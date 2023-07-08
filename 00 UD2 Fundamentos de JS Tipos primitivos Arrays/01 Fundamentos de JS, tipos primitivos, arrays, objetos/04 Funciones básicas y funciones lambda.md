# Funciones básicas y funciones lambda.
#javascript
<aside>
💡 Una función centraliza la lógica de un procedimiento que podemos ejecutar varias veces.

</aside>

```jsx
//Forma tradicional pero no muy recomendable
function saludar() {
    console.log('Hola Mundo');
}

//Si hago esto:
var saludar = 123;

saludar(); //Esto da un error
```

```jsx
//Forma tradicional pero no muy recomendable
function saludar( nombre ) {
    console.log('Hola '+nombre);
}

//Función anónima que no se puede reasignar
const saludar2 = function() {
    console.log('Hola Mundo');
}

saludar('chic@s'); 
saludar2();
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Funciones%20básicas%20y%20funciones%20lambda/Untitled.png)

```jsx
//Forma tradicional pero no muy recomendable
function saludar( nombre ) {
    //Las funciones tradicionales tienen el objeto arguments implícito
    console.log( arguments );
    console.log('Hola '+nombre);
}

//Función anónima
const saludar2 = function( nombre ) {
    console.log('Hola '+ nombre);
}

const saludarLambda = () => {
    console.log('Hola lambda');
}

const saludarLambda2 = ( nombre ) => {
    console.log('Hola lambda '+nombre);
}

saludar('chic@s'); 
saludar('chic@s', 40, true, 'España'); //No da error, ignora los argumentos 
saludar2('Luis');
saludarLambda();
saludarLambda2('Martín');
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Funciones%20básicas%20y%20funciones%20lambda/Untitled%201.png)

# Return

```jsx
function sumar (a , b) {
    return a+b;
}

const sumar2 = (a,b) => {
    return a+b;
} 

//Sólo podemos hacer esto si la única línea en la función es el return.
const sumar3 = (a,b) => a+b;

function getAleatorio() {
    return Math.random();
}

const getAleatorioLambda = () => Math.random();

console.log( sumar(1,2) );//3
console.log( sumar2(1,2) );//3
console.log( sumar3(1,2)); //3
console.log( getAleatorio() ); //Cada vez que recargo tendré un número aleatorio
console.log( getAleatorioLambda());
```