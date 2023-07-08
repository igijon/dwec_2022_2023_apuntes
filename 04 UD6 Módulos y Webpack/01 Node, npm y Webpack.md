# Node, npm y Webpack
#javascript #webpack 
<aside>
💡 Necesitamos separar nuestras aplicaciones por módulos.

</aside>

<aside>
💡 Necesitamos tareas automáticas:
- Live reload de cambios.
- Minimizar el código (no manualmente).
- Los archivos tendrán un hash por seguridad. Ofuscación.
- Incrementar compatibilidad con navegadores.

</aside>

<aside>
💡 [Node](https://nodejs.org/es/) permite correr código JS en el lado del servidor. Podemos escribir con JS aplicaciones tanto en el front como en el back.
También podemos trabajar en local como si fuese un servidor de desarrollo.

</aside>

<aside>
💡 [Babel](https://babeljs.io/) es un paquete que está en node, que por ejemplo permite traducir una aplicación JS moderna para que se ejecute en navegadores antiguos.

</aside>

<aside>
💡 npm es un gestor de paquetes de node y podemos obtener muchísimos paquetes con implementaciones que nos permitirán evitar **reinventar la rueda.**

</aside>

<aside>
💡 [webpack](https://webpack.js.org/) es un empaquetador de módulos. Nos ayudará a:
**- Gestionar las dependencias (junto con npm).
- Montamos un servidor de desarrollo y pruebas.
- Cargar módulos (permite segmentar la aplicación en distintos archivos).
- Convertir a distintos formatos… entre distintas versiones de ECMAScript por ejemplo.
- Minimizar código.
- Compila SASS a CSS y se ven los cambios de forma automática.
- Transcribe TS a JS.
- Nos permite trabajar con JS moderno.**

</aside>

<aside>
💡 Webpack tiene como inconvenientes: **la configuración inicial es compleja y detectar problemas en los paquetes no es trivial.**

</aside>

# Creación proyecto

![Untitled](00%20🌎%20DWEC%202022-2023/04%20UD6%20Módulos%20y%20Webpack/Anexos/Node,%20npm%20y%20Webpack%202d5a0012dc75467499df44303eb09e7a/Untitled.png)

![Untitled](00%20🌎%20DWEC%202022-2023/04%20UD6%20Módulos%20y%20Webpack/Anexos/Node,%20npm%20y%20Webpack%202d5a0012dc75467499df44303eb09e7a/Untitled%201.png)

![Untitled](00%20🌎%20DWEC%202022-2023/04%20UD6%20Módulos%20y%20Webpack/Anexos/Node,%20npm%20y%20Webpack%202d5a0012dc75467499df44303eb09e7a/Untitled%202.png)

# Necesidad de Webpack

[GitHub - igijon/javascript-node-webpack: Esqueleto proyecto JS, node, webpack](https://github.com/igijon/javascript-node-webpack)

[webpack](https://webpack.js.org/)

[Getting Started | webpack](https://webpack.js.org/guides/getting-started/)

## Instalación y configuración

![Untitled](00%20🌎%20DWEC%202022-2023/04%20UD6%20Módulos%20y%20Webpack/Anexos/Node,%20npm%20y%20Webpack%202d5a0012dc75467499df44303eb09e7a/Untitled%203.png)

Webpack sólo funciona en desarrollo.

Al instalarse se crea una carpeta `node_modules` y se añaden dependencias de desarrollo en `package.json`.

Añadimos en `package.json` una línea en script para que con el comando “build”, ejecute webpack:

```yaml
{
  "name": "03-webpack-inicial",
  "version": "1.0.0",
  "description": "Este es un cascarón para un proyecto de webpack",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "build": "webpack"
  },
  "author": "Inma Gijón",
  "license": "ISC",
  "devDependencies": {
    "webpack": "^5.74.0",
    "webpack-cli": "^4.10.0"
  }
}
```

Para ejecutarlo, tenemos que hacer:

```yaml
npm run build
```

Esto genera una carpeta dist con un fichero `main.js`. Este fichero lo enlazamos en el index y exportamos las funciones de los otros módulos.

# Configuración Webpack

[Configuration | webpack](https://webpack.js.org/configuration/)

Añadimos el fichero `webpack.config.js` y al hacer el `npm run build`, el fichero `main.js` de `dist` se ha generado de forma diferente (más legible) pero sigue funcionando igual.

[html-loader | webpack](https://webpack.js.org/loaders/html-loader/)

[HtmlWebpackPlugin | webpack](https://webpack.js.org/plugins/html-webpack-plugin/)

Una vez configurado, en html no necesitamos añadir el script, porque webpack lo añade por nosotros.

Necesitamos instalar también el `webpack-dev-server`

```bash
npm i -D webpack-dev-server #Lo instalo como dependencia de desarrollo -D
```

Creamos también el script `start` para poder lanzarlo:

```json
{
  "name": "03-webpack-inicial",
  "version": "1.0.0",
  "description": "Este es un cascarón para un proyecto de webpack",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "build": "webpack --config webpack.config.js",
    "start": "webpack serve --config webpack.config.js --open --port=8080"
  },
  "author": "Inma Gijón",
  "license": "ISC",
  "devDependencies": {
    "html-loader": "^4.1.0",
    "html-webpack-plugin": "^5.5.0",
    "webpack": "^5.74.0",
    "webpack-cli": "^4.10.0",
    "webpack-dev-server": "^4.11.0"
  }
}
```

```bash
npm run start #También sirve npm start
```

`webpack.config.js`

```jsx
const HtmlWebPackPlugin = require('html-webpack-plugin');

module.exports = {
    mode: 'development',
    output: {
        clean: true
    },
    module: {
        rules: [
            {
                test: /\.html$/,
                loader: 'html-loader',
                options: {
                    sources: false
                }
            }
        ]
    },
    optimization: {},
    plugins: [
        new HtmlWebPackPlugin({
            title: 'Mi Webpack App',
            //filename: 'index.html',
            template: './src/index.html'
        })
    ]
};
```

De este modo los cambios son dinámicos… cualquier cambio se va a refrescar automáticamente.

# Carga de estilos de forma dinámica

[style-loader | webpack](https://webpack.js.org/loaders/style-loader/)

[css-loader | webpack](https://webpack.js.org/loaders/css-loader/)

```jsx
//Fichero webpack.config.js
const HtmlWebPackPlugin = require('html-webpack-plugin');

module.exports = {
    mode: 'development',
    output: {
        clean: true
    },
    module: {
        rules: [
            {
                test: /\.html$/,
                loader: 'html-loader',
                options: {
                    sources: false
                }
            },
            {
                test: /\.css$/,
                use: ['style-loader', 'css-loader']
            },
        ]
    },
    optimization: {},
    plugins: [
        new HtmlWebPackPlugin({
            title: 'Mi Webpack App',
            //filename: 'index.html',
            template: './src/index.html'
        })
    ]
};
```

Css no se copiará en el build, se incorpora embebido en el .js.

# CSS de forma global en la aplicación

[MiniCssExtractPlugin | webpack](https://webpack.js.org/plugins/mini-css-extract-plugin/)

```bash
npm install -D mini-css-extract-plugin
```

```jsx
//webpack.config.js
const HtmlWebPackPlugin = require('html-webpack-plugin');
const MiniCssExtractPlugin = require('mini-css-extract-plugin');

module.exports = {
    mode: 'development',
    output: {
        clean: true
    },
    module: {
        rules: [
            {
                test: /\.html$/,
                loader: 'html-loader',
                options: {
                    sources: false
                }
            },
            {
                test: /\.css$/,
                exclude: /styles.css$/,
                use: ['style-loader', 'css-loader']
            },
            {
                test: /styles.css$/,
                use: [ MiniCssExtractPlugin.loader, 'css-loader']
            }
        ]
    },
    optimization: {},
    plugins: [
        new HtmlWebPackPlugin({
            title: 'Mi Webpack App',
            //filename: 'index.html',
            template: './src/index.html'
        }),
        new MiniCssExtractPlugin({
            filename: '[name].css',
            ignoreOrder: false
        })
    ]
};
```

# Manejo de imágenes

[file-loader | webpack](https://v4.webpack.js.org/loaders/file-loader/)

```bash
npm install -D file-loader
```

`webpack.config.js`

![Untitled](00%20🌎%20DWEC%202022-2023/04%20UD6%20Módulos%20y%20Webpack/Anexos/Node,%20npm%20y%20Webpack%202d5a0012dc75467499df44303eb09e7a/Untitled%204.png)

`componentes.js`

![Untitled](00%20🌎%20DWEC%202022-2023/04%20UD6%20Módulos%20y%20Webpack/Anexos/Node,%20npm%20y%20Webpack%202d5a0012dc75467499df44303eb09e7a/Untitled%205.png)

## Con Copy-webpack-plugin

Con esto consigo que webpack copie las imágenes en el directorio de distribución.

`webpack.config.js`

```jsx
const HtmlWebPackPlugin = require('html-webpack-plugin');
const MiniCssExtractPlugin = require('mini-css-extract-plugin');
const CopyPlugin = require("copy-webpack-plugin");

module.exports = {
    mode: 'development',
    output: {
        clean: true
    },
    module: {
        rules: [
            {
                test: /\.html$/,
                loader: 'html-loader',
                options: {
                    sources: false
                }
            },
            {
                test: /\.css$/,
                exclude: /styles.css$/,
                use: ['style-loader', 'css-loader']
            },
            {
                test: /styles.css$/,
                use: [ MiniCssExtractPlugin.loader, 'css-loader']
            },
            {
                test: /\.(png|jpe?g|gif)$/,
                loader: 'file-loader'
            }
        ]
    },
    optimization: {},
    plugins: [
        new HtmlWebPackPlugin({
            title: 'Mi Webpack App',
            //filename: 'index.html',
            template: './src/index.html'
        }),
        new MiniCssExtractPlugin({
            filename: '[name].css',
            ignoreOrder: false
        }),
        new CopyPlugin({
            patterns: [
                {from: 'src/assets/', to: 'assets/'}
            ]
        })
    ]
};
```

```bash
npm run build #Al hacer esto se genera en la carpeta de distribución la carpeta con la imagen.
```

# Modo producción

Creamos un fichero **webpack.prod.js**

```bash
const HtmlWebPackPlugin = require('html-webpack-plugin');
const MiniCssExtractPlugin = require('mini-css-extract-plugin');
const CopyPlugin = require("copy-webpack-plugin");

module.exports = {
    mode: 'production',
    output: {
        clean: true
    },
    module: {
        rules: [
            {
                test: /\.html$/,
                loader: 'html-loader',
                options: {
                    sources: false
                }
            },
            {
                test: /\.css$/,
                exclude: /styles.css$/,
                use: ['style-loader', 'css-loader']
            },
            {
                test: /styles.css$/,
                use: [ MiniCssExtractPlugin.loader, 'css-loader']
            },
            {
                test: /\.(png|jpe?g|gif)$/,
                loader: 'file-loader'
            }
        ]
    },
    optimization: {},
    plugins: [
        new HtmlWebPackPlugin({
            title: 'Mi Webpack App',
            //filename: 'index.html',
            template: './src/index.html'
        }),
        new MiniCssExtractPlugin({
            filename: '[name].css',
            ignoreOrder: false
        }),
        new CopyPlugin({
            patterns: [
                {from: 'src/assets/', to: 'assets/'}
            ]
        })
    ]
};
```

En **package.json:**

```jsx
{
  "name": "03-webpack-inicial",
  "version": "1.0.0",
  "description": "Este es un cascarón para un proyecto de webpack",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "build": "webpack --config webpack.prod.js",
    "build:dev": "webpack --config webpack.config.js",
    "start": "webpack serve --config webpack.config.js --open --port=8080"
  },
  "author": "Inma Gijón",
  "license": "ISC",
  "devDependencies": {
    "copy-webpack-plugin": "^11.0.0",
    "css-loader": "^6.7.1",
    "file-loader": "^6.2.0",
    "html-loader": "^4.1.0",
    "html-webpack-plugin": "^5.5.0",
    "mini-css-extract-plugin": "^2.6.1",
    "style-loader": "^3.3.1",
    "webpack": "^5.74.0",
    "webpack-cli": "^4.10.0",
    "webpack-dev-server": "^4.11.0"
  }
}
```

Si queremos añadir a los ficheros un hash para que cuando se hace un build de producción

**webpack.prod.js**

```jsx
const HtmlWebPackPlugin = require('html-webpack-plugin');
const MiniCssExtractPlugin = require('mini-css-extract-plugin');
const CopyPlugin = require("copy-webpack-plugin");

module.exports = {
    mode: 'production',
    output: {
        clean: true,
        file: 'main.[contenthash].js'
    },
    module: {
        rules: [
            {
                test: /\.html$/,
                loader: 'html-loader',
                options: {
                    sources: false
                }
            },
            {
                test: /\.css$/,
                exclude: /styles.css$/,
                use: ['style-loader', 'css-loader']
            },
            {
                test: /styles.css$/,
                use: [ MiniCssExtractPlugin.loader, 'css-loader']
            },
            {
                test: /\.(png|jpe?g|gif)$/,
                loader: 'file-loader'
            }
        ]
    },
    optimization: {},
    plugins: [
        new HtmlWebPackPlugin({
            title: 'Mi Webpack App',
            //filename: 'index.html',
            template: './src/index.html'
        }),
        new MiniCssExtractPlugin({
            filename: '[name].[fullhash].css',
            ignoreOrder: false
        }),
        new CopyPlugin({
            patterns: [
                {from: 'src/assets/', to: 'assets/'}
            ]
        })
    ]
};
```

Si queremos compactar más el css: instalamos **css-minimizer-webpack-plugin y terser-webpack-plugin**

**webpack.prod.js**

```jsx
const HtmlWebPackPlugin = require('html-webpack-plugin');
const MiniCssExtractPlugin = require('mini-css-extract-plugin');
const CopyPlugin = require("copy-webpack-plugin");

const CssMinimizer = require('css-minimizer-webpack-plugin');
const Terser = require('terser-webpack-plugin');

module.exports = {
    mode: 'production',
    output: {
        clean: true,
        filename: 'main.[contenthash].js'
    },
    module: {
        rules: [
            {
                test: /\.html$/,
                loader: 'html-loader',
                options: {
                    sources: false
                }
            },
            {
                test: /\.css$/,
                exclude: /styles.css$/,
                use: ['style-loader', 'css-loader']
            },
            {
                test: /styles.css$/,
                use: [ MiniCssExtractPlugin.loader, 'css-loader']
            },
            {
                test: /\.(png|jpe?g|gif)$/,
                loader: 'file-loader'
            }
        ]
    },
    optimization: {
        minimize: true,
        minimizer: [
            new CssMinimizer(),
            new Terser(),
        ]
    },
    plugins: [
        new HtmlWebPackPlugin({
            title: 'Mi Webpack App',
            //filename: 'index.html',
            template: './src/index.html'
        }),
        new MiniCssExtractPlugin({
            filename: '[name].[fullhash].css',
            ignoreOrder: false
        }),
        new CopyPlugin({
            patterns: [
                {from: 'src/assets/', to: 'assets/'}
            ]
        })
    ]
};
```

![Untitled](00%20🌎%20DWEC%202022-2023/04%20UD6%20Módulos%20y%20Webpack/Anexos/Node,%20npm%20y%20Webpack%202d5a0012dc75467499df44303eb09e7a/Untitled%206.png)