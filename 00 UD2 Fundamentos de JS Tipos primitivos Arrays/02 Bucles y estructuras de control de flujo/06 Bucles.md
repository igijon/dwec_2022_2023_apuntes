# Bucles
#javascript
# While y Do While

```jsx
const carros = ['Ford', 'Mazda', 'Honda', 'Toyota'];

let i = 0;

while( i < carros.length ) {
    console.log( carros[i] );
    i++;
}
i = 0;

//undefined
//null 
//false 
//son condiciones que harían que no se ejecutase

while (carros[i]) { //Va a recorrer mientras haya elementos
    console.log(carros[i]);
    i++;
}

i = 0;

while (carros[i]) { 
    if ( i === 1 ){
        break; //Con esto sólo dice el primer elemento, porque después
        //se sale del bucle
    }    
    console.log(carros[i]);
    i++;
}

i = 0;

while (carros[i]) { 
    if ( i === 1 ){
        continue; //con esto sólo muestra Ford
    }    
    console.log(carros[i]);
    i++;
}
```

![Untitled](Untitled_1.png)

```jsx
console.warn('Do While');
let j = 0;
do {
    console.log( carros[j]); //Aquí entra siempre la primera vez sin
    //comprobación
    j++;
}while(carros[j]);
```

![Untitled](Untitled%201_1.png)

# For - For in - For of

```jsx
const heroes = ['Batman', 'Superman', 'Mujer maravilla','Aquaman'];

console.warn('For tradicional');

for (let i = 0; i<heroes.length; i++) {
    console.log( heroes[i] );
}

console.warn('For in');

for (let i in heroes) {
    console.log( heroes[i] );
}

console.warn('For of');

for( let heroe of heroes) {
    console.log(heroe);
}
```

![Untitled](Untitled%202_1.png)