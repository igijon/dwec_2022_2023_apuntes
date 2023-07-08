# Principal problema con var
#javascript
```jsx
console.log(window.outerHeight);
console.log(window.outerWidth);
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Principal%20problema%20con%20var/Untitled.png)

Si a alguien se le ocurre la feliz idea de declarar:

```jsx
var outerHeight = 1000000;
```

<aside>
💡 Esto machacaría el valor y tendríamos muchos problemas en desarrollo. Además esto es muy difícil de rastrear y encontrar el problema.

</aside>

<aside>
💡 La forma correcta actualmente de crear variables y constantes es `let` y `const`. Esto no sobreescribe el objeto global `window`.

</aside>