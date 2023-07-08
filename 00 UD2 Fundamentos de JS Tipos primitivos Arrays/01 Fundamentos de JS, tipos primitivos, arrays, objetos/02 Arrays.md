# Arrays
#javascript
```jsx
const arr = new Array(10); //No se suele utilizar
console.log(arr);
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Arrays/Untitled.png)

```jsx
const arr = [];
console.log(arr);
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Arrays/Untitled%201.png)

```jsx
let videoJuegos = [ 'Mario 3', 'Megaman', 'Chrono Trigger' ];
console.log( { videoJuegos } );
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Arrays/Untitled%202.png)

```jsx
// const arr = new Array(10); //No se suele utilizar
// const arr = [];
// console.log(arr);

let videoJuegos = [ 'Mario 3', 'Megaman', 'Chrono Trigger' ];
console.log( { videoJuegos } );

console.log( videoJuegos[0] );

let arrayCosas = [
    true,
    123,
    'Inma',
    1 + 2,
    function(){},
    ()=>{},
    {a: 1},
    ['X', 'Megaman', 'Zero', 'Dr. Light', [
        'Dr. Willy',
        'Woodman'
    ]]
];

console.log( {arrayCosas} );
console.log( arrayCosas[0] ); //true
console.log( arrayCosas[2] ); //Inma
console.log( arrayCosas[7][3] ); //Dr. Light
console.log( arrayCosas[7][4][1] ); //Woodman
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Arrays/Untitled%203.png)

<aside>
💡 Los métodos son funciones dentro de los arrays y también tenemos propiedades

</aside>

# Métodos y propiedades

```jsx
let juegos = ['Zelda', 'Mario', 'Metroid', 'Chrono'];
console.log('Longitud: ', juegos.length);

let primero = juegos[0];
let ultimo = juegos[juegos.length-1];

juegos.forEach( (elemento, indice, arr) => {
    console.log({elemento, indice, arr});
})

let nuevaLongitud = juegos.push('F-Zero');
//Con las llaves, juegos se computa y al ser una referencia muestra el valor
//resultado de todas las operaciones, cuando lo ponemos sin llaves, es el valor
//que tiene en este momento... veremos las referencias más adelante.
console.log({nuevaLongitud, juegos});
console.log(juegos);

//Inserta elementos al princpio del array
nuevaLongitud = juegos.unshift('Fire Emblem');
console.log({nuevaLongitud, juegos});
console.log(juegos);

//borrar el elemento del final
let elementoBorrado = juegos.pop();
console.log({elementoBorrado, juegos});
console.log(juegos);

let pos = 1;

let juegosBorrados = juegos.splice( pos, 2); //Borra a partir de la posición pos, 2 elementos 
console.log({juegosBorrados, juegos});
console.log(juegos);

let metroidIndex = juegos.indexOf('Metroid'); //CaSeSeNSiTiVe
console.log({metroidIndex});
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Arrays/Untitled%204.png)