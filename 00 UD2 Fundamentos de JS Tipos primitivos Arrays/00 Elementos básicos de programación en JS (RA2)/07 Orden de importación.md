# Orden de importación
#javascript
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <script src="./app.js"></script>
</head>
<body>
    <h1>Hola Mundo</h1>
    <hr>
    <p>Lo que sea</p>
</body>
</html>
```

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Orden%20de%20importación/Untitled.png)

Si ahora en `app.js`:

```jsx
alert('Hola desde app.js');

let d = 10, 
    e = 20, 
    c = 'Hola ',
    f = 'Spiderman',
    x = d + e;

const saludo = c + f;

c = 'Hola de nuevo';
```

<aside>
💡 Si lo pruebas verás que no se renderiza el documento hasta que no cerramos el alert. El `alert` es una instrucción bloqueante.

</aside>

Si lo hago aquí:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    
</head>
<body>
    <h1>Hola Mundo</h1>
    <hr>
    <p>Lo que sea</p>

    <script src="./app.js"></script>
</body>
</html>
```

<aside>
💡 En este caso, se ve el html antes del JS y le da la falsa sensación al usuario de una carga más rápida.

</aside>

<aside>
💡 No es normal tener los ficheros directamente en la raíz. Es más normal otra estructura de directorios (dependerá también de los frameworks)

</aside>

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Orden%20de%20importación/Untitled%201.png)

Nos tenemos que asegurar de esto:

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Orden%20de%20importación/Untitled%202.png)

Si tengo lo siguiente:

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Orden%20de%20importación/Untitled%203.png)

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Orden%20de%20importación/Untitled%204.png)

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Orden%20de%20importación/Untitled%205.png)

En la consola mostraría el nombre por el orden de importación, pero si lo importásemos al revés… no lo encontraría. 

Está definida como `var`, porque si no la definiésemos así, no se crearía en el objeto global y no podría ser accesible desde `alerts.js`, pero **NO ES BUENA PRÁCTICA.**