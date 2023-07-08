# Singleton
#javascript
<aside>
💡 Singleton es una instancia única de mi clase. La tendré de manera global en toda la aplicación. Por ejemplo, una BDD, un servicio de manera global…
Aunque yo haga new muchas veces, siempre obtengo la misma instancia.

</aside>

```jsx
class Singleton {
    //Se podría implementar como propiedad privada
    static instancia; //Esta será la instancia inicializada de mi clase
    nombre = '';

    constructor( nombre = '' ) {

        //si lo pongo con !! trabaja con false en lugar de con undefined
        //si ya existe una instancia, la devuelve
        if(!!Singleton.instancia) {
            return Singleton.instancia;
        }

        Singleton.instancia = this;
        this.nombre = nombre;

        //Opcional, si no lo pongo hace lo mismo
        return this;
    }
}

const instancia1 = new Singleton('Totoro');
const instancia2 = new Singleton('Nicky');
const instancia3 = new Singleton('Calcifer');

console.log(`Nombre en la instancia1 es ${instancia1.nombre}`);
console.log(`Nombre en la instancia2 es ${instancia2.nombre}`);
```

![Untitled](00%20🌎%20DWEC%202022-2023/03%20UD5%20POO/Anexos/Singleton%20cfec002eca65465dad4aa136b34abf57/Untitled.png)