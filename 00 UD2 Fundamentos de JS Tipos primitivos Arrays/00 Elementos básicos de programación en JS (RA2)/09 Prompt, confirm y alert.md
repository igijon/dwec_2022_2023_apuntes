# Prompt, confirm y alert
#javascript
# Distintos cuadros de diálogo bloqueantes

```jsx
alert('Hola mundo');

//Si acepto sin valor, obtengo cadena vacía, 
//si cancelo en el prompt obtengo null.
let nombre = prompt('¿Cuál es tu nombre?', 'Sin nombre');
console.log( nombre );

const seleccion = confirm('¿Está seguro de borrar esto?');
console.log(seleccion);
```

<aside>
💡 Veremos más adelante cómo usarlas sin bloquear

</aside>

Estos métodos son métodos dentro del objeto `window`

Si en la consola del navegador ponemos `window`

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Prompt,%20confirm%20y%20alert/Untitled.png)

<aside>
💡 En node, `global` es un objeto similar a `window` en el navegador web.

</aside>

<aside>
💡 En entornos backend, no podremos utilizar `alert`, `prompt` o `confirm`, porque están enfocados a un navegador web (cliente).

</aside>