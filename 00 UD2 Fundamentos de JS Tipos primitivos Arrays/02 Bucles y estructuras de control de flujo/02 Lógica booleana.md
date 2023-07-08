# Lógica booleana
#javascript
```jsx
const regresaTrue = () => {
    console.log('Regresa true');
    return true;
}
const regresaFalse = () => {
    console.log('Regresa false');
    return false;
}

console.warn('Not o la negación');
console.log( true );
console.log(!true); //false
console.log(!false); //true

console.log(!regresaFalse()); //true

console.warn('And'); //true si todos los valores son verdaderos
console.log( true && true); //true
console.log( true && false); //false
console.log( true && !false); //true
console.log( false && true); //false
console.log( false && false); //false

console.log('==========');
console.log(regresaFalse() && regresaTrue()); //false y sólo entra en la primera función
console.log(regresaTrue() && regresaFalse()); //false y entra en las dos

console.warn('Or');

console.log( true || false); //true
console.log(false || false); //false

console.log( regresaTrue() || regresaFalse()); //true y sólo evalúa el primero
console.log( regresaFalse() || regresaTrue()); //true y evalúa ambos
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Untitled%208.png)