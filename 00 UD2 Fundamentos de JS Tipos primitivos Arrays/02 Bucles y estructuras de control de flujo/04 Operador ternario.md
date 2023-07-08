# Operador ternario
#javascript
# Sin operador ternario

```jsx
/**
 * Días de semana abrimos a las 11
 * pero los fines de semana abrimos a las 9
 */

//Entra a un sitio web para consultar si está abierto hoy
const dia = 0; //0:domingo, 1:lunes...
const horaActual= 10;

let horaApertura;
let mensaje; //Está abierto, Está cerrado, hoy abrimos a las XX

//Sin operador ternario
// if ( dia === 0 || dia === 6 ) {
if ( [0,6].includes(dia) ){
    console.log('Fin de semana');
    horaApertura = 9;
} else {
    console.log('Día de semana');
    horaApertura = 11;
}

if(horaActual >= horaApertura) {
    mensaje = 'Está abierto';
} else {
    mensaje = `Está cerrado, hoy abrimos a las ${horaApertura}`; //Back tip
}

console.log({horaApertura, mensaje});
```

# Con operador ternario

```jsx
/**
 * Días de semana abrimos a las 11
 * pero los fines de semana abrimos a las 9
 */

//Entra a un sitio web para consultar si está abierto hoy
const dia = 0; //0:domingo, 1:lunes...
const horaActual= 10;

let horaApertura;
let mensaje; //Está abierto, Está cerrado, hoy abrimos a las XX

horaApertura = ([0,6].includes(dia)) ? 9 : 11;
mensaje = (horaActual >= horaApertura) ? 'Está abierto' : `Está cerrado, hoy abrimos a las ${horaApertura}`;

console.log({horaApertura, mensaje});
```

# Aplicaciones del operador ternario

```jsx
const elMayor = (a,b) => (a > b) ? a: b;

const pertenece = (miembro) => miembro ? '2 euros' : '10 euros';

console.log(elMayor(20,3));
console.log(pertenece(false));

const amigo = true;
const amigosArr = [
    'Peter',
    'Tony',
    'Dr. Strange',
    amigo ? 'Thor' : 'Loki',
    (() => 'Nick fury') (), //Función anónima autoinvocada
    elMayor(10,15)
];

console.log(amigosArr);

const nota = 65; //A+ A B+...
const grado = nota >= 95 ? 'A+':
              nota >= 90 ? 'A' :
              nota >= 85 ? 'B+':
              nota >= 80 ? 'B' :
              nota >= 75 ? 'C+':
              nota >= 70 ? 'C' : 'F';

console.log(nota, grado);
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Untitled%207.png)