# Valor, referencia y romper la referencia
#javascript
# Valor

```jsx
let a = 10;
let b = a;
a = 30;

//Cuando trabajamos por primitivos, trabajamos por valor,
//no afectamos el mismo espacio de memoria
console.log({a, b});
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Untitled%203.png)

# Referencia

```jsx
 //En JS todos los objetos son pasados por referncia.
let juan = { nombre: 'Juan' };
let ana = juan;
ana.nombre = 'Ana';

console.log( {juan, ana} );
```

![Untitled](Untitled%201%201.png)

<aside>
💡 En JS todos los elementos son objetos menos los primitivos

</aside>

```jsx
const cambiaNombre = ( persona ) => {
    persona.nombre = 'Tony';
    return persona;
}

let peter = {nombre: 'Peter'};
let tony = cambiaNombre ( peter );
console.log( {peter, tony} );
```

![Untitled](Untitled%202%201.png)

# Romper la referencia

```jsx
//En JS todos los objetos son pasados por referncia.
let juan = { nombre: 'Juan' };
let ana = { ...juan }; //Esto genera una copia porque genera un nuevo objeto
//Y el operador spread separa todas las propiedades del objeto juan
//Es diferente al parámetro rest cuando va como parámetro en una función.
ana.nombre = 'Ana';

console.log( {juan, ana} );

const cambiaNombre = ( {...persona} ) => {
    persona.nombre = 'Tony';
    return persona;
}

let peter = {nombre: 'Peter'};
let tony = cambiaNombre ( peter );
console.log( {peter, tony} );
```

![Untitled](Untitled%203%201.png)

Mismo ejercicio pero con arreglos

```jsx
//Array
const frutas = ['Manzana', 'Pera', 'Piña'];
const otrasFrutas = frutas;
otrasFrutas.push('Mango');
console.table({frutas, otrasFrutas});
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Untitled%204.png)

```jsx
//Array
const frutas = ['Manzana', 'Pera', 'Piña'];
const otrasFrutas = [...frutas];
otrasFrutas.push('Mango');
console.table({frutas, otrasFrutas});
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Untitled%205.png)

```jsx
//Array
const frutas = ['Manzana', 'Pera', 'Piña'];
const otrasFrutas = frutas.slice(); //Produce el mismo efecto que spread. 
otrasFrutas.push('Mango');
console.table({frutas, otrasFrutas});
```

Veamos cuál es más eficiente

```jsx
console.time('slice');
const otrasFrutas = frutas.slice();
console.timeEnd('slice');

console.time('spread');
const otrasFrutas2 = [...frutas];
console.timeEnd('spread');
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Untitled%206.png)