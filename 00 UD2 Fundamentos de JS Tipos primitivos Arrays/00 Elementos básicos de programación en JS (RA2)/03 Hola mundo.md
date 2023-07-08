# Hola mundo
#javascript 

# Navegador

- Cuando abrimos el navegador web, todos tienen su versión de JS, tienen implementada su versión del ECMAScript.
- Microsoft Edge va por detrás en la implementación del estándar con respecto a Google Chrome.
- Mostramos las herramientas de desarrollo en Google Chrome con el menú o con F12.
- Entramos en la pestaña de consola:

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Hola%20mundo/Untitled.png)

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Hola%20mundo/Untitled%201.png)

`Console` es un objeto, `log` es un método de ese objeto.

Si hacemos:

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Hola%20mundo/Untitled%202.png)

# Terminal

Si abrimos un terminal (consola) (tenemos que tener instalado node):

```bash
node --version
```

Si ejecuto node:

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Hola%20mundo/Untitled%203.png)

# VSCode

![Untitled](00%20🌎%20DWEC%202022-2023/00%20UD2%20Fundamentos%20de%20JS%20Tipos%20primitivos%20Arrays/Anexos/Hola%20mundo/Untitled%204.png)

Creamos un fichero `index.html`. Con ! + tab se genera el estándar. Añadimos lo siguiente.

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
    <script>
        console.log('Hola mundo');
    </script>
</body>
</html>
```

- Podemos abrir el html y en la consola veremos lo que se muestra
- Vamos a ver cómo lo podemos hacer importándolo:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
  </head>
  <body>
    <script src="./app.js"></script>
  </body>
</html>
```

- También se puede poner en el head, pero lo suyo es ponerlo al final de la página (dentro del body), para que todo el documento esté renderizado.