# Asignaciones con operadores
#javascript
```jsx
console.warn('Asignaciones');

const soyUndefined = undefined;
const soyNull = null;
const soyFalso = false;

const a1 = true && 'Hola mundo' && 150; //150
const a2 = false && 'Hola mundo' && 150; //false
const a3 = true && 'Hola mundo' && soyFalso; //false
console.log({a1, a2, a3});

const a4 = soyFalso || 'Ya no soy falso'; //ya no soy falso
const a5 = soyFalso || soyUndefined || soyNull || 'Ya no soy falso de nuevo' || true; //ya no soy falso de nuevo
const a6 = soyFalso || soyUndefined || regresaTrue() || 'Ya no soy falso de nuevo'; //true
console.log({a4, a5, a6});
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Untitled%202.png)