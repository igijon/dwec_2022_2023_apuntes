# Babel
#javascript #babel

# Necesidad de Babel

Aumenta la compatibilidad de nuestro código en distintos navegadores web.

[Babel · The compiler for next generation JavaScript](https://babeljs.io/)

Lo instalamos en nuestro proyecto.

```jsx
npm install --save-dev babel-loader @babel/core
npm install @babel/preset-env --save-dev
```

Todo lo que estamos instalando son **dependencias de desarrollo.**

**babel.config.json** (lo creamos en la raíz)

```jsx
{
  "presets": ["@babel/preset-env"]
}
```

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
            },
            {
                test: /\.m?js$/,
                exclude: /node_modules/,
                use: {
                  loader: "babel-loader",
                  options: {
                    presets: ['@babel/preset-env']
                  }
                }
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

Este código funcionará exactamente igual pero estará optimizado para que funcione para distintos navegadores.

Babel se asegura de que usemos características nuevas de JS y lo traduce para que sea compatible con todos los navegadores.

<aside>
💡 Babel y Typescript no son excluyentes. Typescript también se encarga de la traducción pero se encarga del tipado también.

</aside>