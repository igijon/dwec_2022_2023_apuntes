# If-else
#javascript 
```jsx
let a = 5;

if ( a >= 10 ) { //hay excepciones: undefined, null, una asignación
    console.log( 'a es mayor o igual que 10');
} else {
    console.log( 'a es menor que 10' );
}

console.log('Fin de programa');
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Untitled%209.png)

```jsx

const hoy = new Date(); //Obtenemos la información del momento actual
console.log( hoy );

let dia = hoy.getDay(); //0: Domingo, 1: Lunes...
console.log( {dia} );

if ( dia === 0 ) { //El triple igual comprueba el valor y el tipado
    console.log('Domingo');
} else if ( dia === 1) {
        console.log( 'Lunes' );
} else {
    console.log( 'No es lunes ni domingo' );
}
```

Alternativa a if-else:

```jsx
const diasLetras = {
    0: 'domingo',
    1: 'lunes',
    2: 'martes',
    3: 'miércoles',    
    4: 'jueves',
    5: 'viernes',
    6: 'sábado' 
};

console.log(diasLetras[dia]);
```

![Untitled](Untitled%201%202.png)