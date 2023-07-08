# Objetos literales
#javascript
<aside>
💡 JS tiene tipos de datos primitivos y objetos. También tenemos objetos literales, que es un objeto que tiene pares de valores.

</aside>

<aside>
💡 Los objetos literales son como los diccionarios en Python.

</aside>

```jsx
let personaje = {
    nombre: 'Tony Stark',
    codeName: 'Ironman',
    vivo: false,
    edad: 40,
    coords: {
        lat: 34.034,
        lng: -118.70
    },
    trajes: ['Mark I', 'Mark V', 'Hulkbuster'],
    direccion: {
        zip: '10880, 90265',
        ubicacion: 'Malibu, California'
    },
    'ultima-pelicula': 'Infinity War' //No es recomendable poner caracteres especiales pero se haría así.
};

console.log( personaje ); // Se imprime por orden alfabético
console.log('Nombre', personaje.nombre);
console.log('Nombre', personaje['nombre']); //Equivalente a la anterior
console.log('Edad', personaje.edad);

console.log('Coors', personaje.coords);
console.log('Lat', personaje.coords.lat);

console.log('Num. Trajes', personaje.trajes.length);
console.log('Último traje', personaje.trajes[personaje.trajes.length-1]);

const x = 'vivo';
console.log('Vivo', personaje[x]);

console.log('Última película: ', personaje['ultima-pelicula']); //En este caso no se puede utilizar la notación punto.
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Objetos%20literales/Untitled.png)

```jsx
//OTROS DETALLES 

//Borrar propiedades
delete personaje.edad;
console.log(personaje);

//Añadirá la propiedad
personaje.casado = true;

const entriesPares = Object.entries( personaje );
console.log(entriesPares);

//si establezco el personaje como const, lo hago inmutable, puedo modificar 
//propiedades pero no hacer asignaciones nuevas. 
console.log( personaje );

//Si quiero congelar el estado del objeto y que nos e puedan añadir ni modificar
//propiedades, puedo hacer
Object.freeze( personaje );

personaje.dinero = 10000000000000;
personaje.casado = false; 
console.log( personaje ); //No tendré el objeto dinero ni habrá cambiado el valor de casado.
//Yo sí puedo cambiar la ubicación de la dirección...
personaje.direccion.ubicacion = 'Costa Rica'; //Esto sí va a tener efecto.

const propiedades = Object.getOwnPropertyNames( personaje );
const valores = Object.values( personaje );
console.log( propiedades, valores ); //Array con las propiedades en el orden en el que fueron creadas y los valores
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Objetos%20literales/Untitled%201.png)

[Object - JavaScript | MDN](https://developer.mozilla.org/es/docs/Web/JavaScript/Reference/Global_Objects/Object)