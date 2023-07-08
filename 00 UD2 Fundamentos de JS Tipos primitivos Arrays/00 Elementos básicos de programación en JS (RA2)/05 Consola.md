# Consola
#javascript
```jsx
let d = 10, 
    e = 20, 
    f = 4,
    x = d + e;

console.log(x);
console.warn(x);
console.error(x);
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Consola/Untitled.png)

```jsx
let d = 10, 
    e = 20, 
    f = 4,
    x = d + e;

console.log('x', x);
console.warn('x', x);
console.error('x', x);
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Consola/Untitled%201.png)

```jsx
let d = 10, 
    e = 20, 
    f = 4,
    x = d + e;

console.log({x});
console.warn({x});
console.error({x});
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Consola/Untitled%202.png)

Incluso se puede cambiar el color y la forma en la que aparece el texto en consola, con propiedades de `CSS`.

```jsx
let d = 10, 
    e = 20, 
    c = 'Hola',
    f = 'Spiderman',
    x = d + e;

console.table({d, e, c, f, x});
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Consola/Untitled%203.png)

<aside>
💡 Las constantes son más ligeras que las variables porque no llevan las propiedades para cambiar el valor. Usarlas correctamente optimiza el código.

</aside>

<aside>
💡 Las constantes de entorno irán en mayúsculas pero las constantes restantes van en minúsculas en JS.

</aside>

```jsx
let d = 10, 
    e = 20, 
    c = 'Hola ',
    f = 'Spiderman',
    x = d + e;

const saludo = c + f;
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Consola/Untitled%204.png)