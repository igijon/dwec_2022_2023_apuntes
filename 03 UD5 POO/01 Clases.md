# Clases
#javascript
# Clases

```jsx
class Persona {
    constructor() {
        console.log('Hola!');
    }
}

const spiderman = new Persona();
```

![Untitled](00%20🌎%20DWEC%202022-2023/03%20UD5%20POO/Anexos/Clases%208780d165e3ba45839399d1f4f3497ff2/Untitled.png)

<aside>
💡 El constructor es el único que devuelve la instancia de un objeto, nunca undefined aunque pongamos `undefined`.

</aside>

```jsx
class Persona {
    //Por defecto, todas las clases JS tienen el use strict implementado
    nombre = '';
    codigo = '';
    frase  = '';
    
    constructor( nombre, codigo, frase ) {
        if(!nombre) throw Error('Necesitamos el nombre');
        if(!codigo) throw Error('Necesitamos el código');
        if(!frase) throw Error('Necesitamos la frase');

        this.nombre = nombre;
        this.codigo = codigo;
        this.frase  = frase;
    }
}

const spiderman = new Persona('Peter Parker', 'Spider', 'Soy tu amigable vecino Spiderman');
console.log(spiderman);
```

```jsx
class Persona {
    //Por defecto, todas las clases JS tienen el use strict implementado
    nombre = '';
    codigo = '';
    frase  = '';
    
    constructor( nombre = 'Sin nombre', codigo = 'Sin código', frase = 'Sin frase') {

        this.nombre = nombre;
        this.codigo = codigo;
        this.frase  = frase;
    }
}

const spiderman = new Persona('Peter Parker', 'Spider', 'Soy tu amigable vecino Spiderman');
const ironman = new Persona('Tony Stark', 'Ironman', 'Yo soy Ironman');
console.log(spiderman);
console.log(ironman);
```

![Untitled](00%20🌎%20DWEC%202022-2023/03%20UD5%20POO/Anexos/Clases%208780d165e3ba45839399d1f4f3497ff2/Untitled%201.png)

## Métodos

```jsx
class Persona {
    //Por defecto, todas las clases JS tienen el use strict implementado
    nombre = '';
    codigo = '';
    frase  = '';
    
    constructor( nombre = 'Sin nombre', codigo = 'Sin código', frase = 'Sin frase') {

        this.nombre = nombre;
        this.codigo = codigo;
        this.frase  = frase;
    }

    quienSoy() {
        console.log(`Soy ${this.nombre} y mi identidad es ${this.codigo}`);
    }

    miFrase() {
        this.quienSoy();
        console.log(`${this.codigo} dice: ${this.frase}`);
    }
}

const spiderman = new Persona('Peter Parker', 'Spider', 'Soy tu amigable vecino Spiderman');
const ironman = new Persona('Tony Stark', 'Ironman', 'Yo soy Ironman');

spiderman.miFrase();
ironman.miFrase();
```

![Untitled](00%20🌎%20DWEC%202022-2023/03%20UD5%20POO/Anexos/Clases%208780d165e3ba45839399d1f4f3497ff2/Untitled%202.png)

# Sets y Gets

<aside>
💡 Los set no pueden tener el mismo nombre que la propiedad que modifican porque si no entrarían en una recursividad infinita.

</aside>

```jsx
class Persona {
    //Por defecto, todas las clases JS tienen el use strict implementado
    nombre  = '';
    codigo  = '';
    frase   = '';
    _comida  = '';
    
    constructor( nombre = 'Sin nombre', codigo = 'Sin código', frase = 'Sin frase') {

        this.nombre = nombre;
        this.codigo = codigo;
        this.frase  = frase;
    }

    //No pueden tener el mismo nombre que la propiedad que modifican porque 
    //si no entran en bucle infinito
    set setComidaFavorita( comida ) {
        this._comida = comida;
    }

    quienSoy() {
        console.log(`Soy ${this.nombre} y mi identidad es ${this.codigo}`);
    }

    miFrase() {
        this.quienSoy();
        console.log(`${this.codigo} dice: ${this.frase}`);
    }
}

const spiderman = new Persona('Peter Parker', 'Spider', 'Soy tu amigable vecino Spiderman');
const ironman = new Persona('Tony Stark', 'Ironman', 'Yo soy Ironman');

spiderman.miFrase();

spiderman.setComidaFavorita = 'El pastel de cereza de la tía May';
//Esto añade propiedades sin dar error y también permite modificarlas si no las establecemos como
//privadas... CUIDADO!
spiderman.nemesis = 'Duende verde';

console.log(spiderman);
```

![Untitled](00%20🌎%20DWEC%202022-2023/03%20UD5%20POO/Anexos/Clases%208780d165e3ba45839399d1f4f3497ff2/Untitled%203.png)

```jsx
class Persona {
    //Por defecto, todas las clases JS tienen el use strict implementado
    nombre  = '';
    codigo  = '';
    frase   = '';
    _comida  = '';
    
    constructor( nombre = 'Sin nombre', codigo = 'Sin código', frase = 'Sin frase') {

        this.nombre = nombre;
        this.codigo = codigo;
        this.frase  = frase;
    }

    //No pueden tener el mismo nombre que la propiedad que modifican porque 
    //si no entran en bucle infinito
    set setComidaFavorita( comida ) {
        this._comida = comida.toUpperCase();
    }

    get getComidaFavorita() {
        return `La comida favorita de ${this.nombre} es ${this._comida}`;
    }

    quienSoy() {
        console.log(`Soy ${this.nombre} y mi identidad es ${this.codigo}`);
    }

    miFrase() {
        this.quienSoy();
        console.log(`${this.codigo} dice: ${this.frase}`);
    }
}

const spiderman = new Persona('Peter Parker', 'Spider', 'Soy tu amigable vecino Spiderman');
const ironman = new Persona('Tony Stark', 'Ironman', 'Yo soy Ironman');

spiderman.miFrase();

spiderman.setComidaFavorita = 'El pastel de cereza de la tía May';

console.log(spiderman.getComidaFavorita);
console.log(spiderman);
```

![Untitled](00%20🌎%20DWEC%202022-2023/03%20UD5%20POO/Anexos/Clases%208780d165e3ba45839399d1f4f3497ff2/Untitled%204.png)

## Estáticos

```jsx
class Persona {

    static _conteo = 0;

    //Por defecto, todas las clases JS tienen el use strict implementado
    nombre  = '';
    codigo  = '';
    frase   = '';
    _comida  = '';
    
    constructor( nombre = 'Sin nombre', codigo = 'Sin código', frase = 'Sin frase') {

        this.nombre = nombre;
        this.codigo = codigo;
        this.frase  = frase;

        Persona._conteo++; 
    }

    //No pueden tener el mismo nombre que la propiedad que modifican porque 
    //si no entran en bucle infinito
    set setComidaFavorita( comida ) {
        this._comida = comida.toUpperCase();
    }

    get getComidaFavorita() {
        return `La comida favorita de ${this.nombre} es ${this._comida}`;
    }

    quienSoy() {
        console.log(`Soy ${this.nombre} y mi identidad es ${this.codigo}`);
    }

    miFrase() {
        this.quienSoy();
        console.log(`${this.codigo} dice: ${this.frase}`);
    }
}

const spiderman = new Persona('Peter Parker', 'Spider', 'Soy tu amigable vecino Spiderman');
const ironman = new Persona('Tony Stark', 'Ironman', 'Yo soy Ironman');

console.log('Conteo estático', Persona._conteo );
```

![Untitled](00%20🌎%20DWEC%202022-2023/03%20UD5%20POO/Anexos/Clases%208780d165e3ba45839399d1f4f3497ff2/Untitled%205.png)

```jsx
class Persona {

    static _conteo = 0;

    static get conteo() {
        return Persona._conteo + 'instancias';
    }

    //Por defecto, todas las clases JS tienen el use strict implementado
    nombre  = '';
    codigo  = '';
    frase   = '';
    _comida  = '';
    
    constructor( nombre = 'Sin nombre', codigo = 'Sin código', frase = 'Sin frase') {

        this.nombre = nombre;
        this.codigo = codigo;
        this.frase  = frase;

        Persona._conteo++; 
    }

    //No pueden tener el mismo nombre que la propiedad que modifican porque 
    //si no entran en bucle infinito
    set setComidaFavorita( comida ) {
        this._comida = comida.toUpperCase();
    }

    get getComidaFavorita() {
        return `La comida favorita de ${this.nombre} es ${this._comida}`;
    }

    quienSoy() {
        console.log(`Soy ${this.nombre} y mi identidad es ${this.codigo}`);
    }

    miFrase() {
        this.quienSoy();
        console.log(`${this.codigo} dice: ${this.frase}`);
    }
}

const spiderman = new Persona('Peter Parker', 'Spider', 'Soy tu amigable vecino Spiderman');
const ironman = new Persona('Tony Stark', 'Ironman', 'Yo soy Ironman');

console.log('Conteo estático', Persona._conteo );
console.log(Persona.conteo); //Get estático
```

![Untitled](00%20🌎%20DWEC%202022-2023/03%20UD5%20POO/Anexos/Clases%208780d165e3ba45839399d1f4f3497ff2/Untitled%206.png)

```jsx
class Persona {

    static _conteo = 0;

    static get conteo() {
        return Persona._conteo + 'instancias';
    }

    static mensaje() {
        console.log(this.nombre); //undefined porque no es sobre la instancia.
        console.log('Hola a todos, soy un método estático');
    }

    //Por defecto, todas las clases JS tienen el use strict implementado
    nombre  = '';
    codigo  = '';
    frase   = '';
    _comida  = '';
    
    constructor( nombre = 'Sin nombre', codigo = 'Sin código', frase = 'Sin frase') {

        this.nombre = nombre;
        this.codigo = codigo;
        this.frase  = frase;

        Persona._conteo++; 
    }

    //No pueden tener el mismo nombre que la propiedad que modifican porque 
    //si no entran en bucle infinito
    set setComidaFavorita( comida ) {
        this._comida = comida.toUpperCase();
    }

    get getComidaFavorita() {
        return `La comida favorita de ${this.nombre} es ${this._comida}`;
    }

    quienSoy() {
        console.log(`Soy ${this.nombre} y mi identidad es ${this.codigo}`);
    }

    miFrase() {
        this.quienSoy();
        console.log(`${this.codigo} dice: ${this.frase}`);
    }
}

const spiderman = new Persona('Peter Parker', 'Spider', 'Soy tu amigable vecino Spiderman');
const ironman = new Persona('Tony Stark', 'Ironman', 'Yo soy Ironman');

console.log('Conteo estático', Persona._conteo );
console.log(Persona.conteo); //Get estático
Persona.mensaje();
```

![Untitled](00%20🌎%20DWEC%202022-2023/03%20UD5%20POO/Anexos/Clases%208780d165e3ba45839399d1f4f3497ff2/Untitled%207.png)

<aside>
💡 No es recomendable, pero en JS se pueden realizar métodos estáticos fuera de la clase.
Persona.propiedadExterna = ‘Hola mundo’; crearía una propiedad estática fuera de la clase.

</aside>

# Herencia

```jsx
class Heroe extends Persona{
    
    clan = 'sin clan';

}

const spiderman = new Heroe('Peter Parker', 'Spider', 'Soy tu amigable vecino Spiderman');

console.log(spiderman);
```

![Untitled](00%20🌎%20DWEC%202022-2023/03%20UD5%20POO/Anexos/Clases%208780d165e3ba45839399d1f4f3497ff2/Untitled%208.png)

<aside>
💡 Puedo llamar a los métodos del padre

</aside>

```jsx
class Heroe extends Persona{
    
    clan = 'sin clan';

    constructor( nombre, codigo, frase ) {
        super( nombre, codigo, frase ); //siempre al principio, porque no se puede utilizar la instancia antes
        this.clan = 'Los Avengers';
    }

    quienSoy() {
        console.log(`Soy ${this.nombre}, ${this.clan}`);
        super.quienSoy();
    }
}

const spiderman = new Heroe('Peter Parker', 'Spider', 'Soy tu amigable vecino Spiderman');

console.log(spiderman);
spiderman.quienSoy();
```

![Untitled](00%20🌎%20DWEC%202022-2023/03%20UD5%20POO/Anexos/Clases%208780d165e3ba45839399d1f4f3497ff2/Untitled%209.png)

## Propiedades privadas

[JavaScript classes: Private class fields | Can I use... Support tables for HTML5, CSS3, etc](https://caniuse.com/mdn-javascript_classes_private_class_fields)

<aside>
💡 Puedo cambiar las propiedades de forma intencionada o accidental

</aside>

```jsx
class Rectangulo {
    area = 0;

    constructor(base = 0, altura = 0) {
        this.base = base;
        this.altura = altura;

        this.area = base * altura;
    }

}

const rectangulo = new Rectangulo(10, 15);
rectangulo.area = 100; //NO DEBERÍAMOS PODER MODIFICARLA DIRECTAMENTE. DEBERÍA SER PRIVADA
console.log(rectangulo);
```

<aside>
💡 # con esto se establece como privada

</aside>

```jsx
class Rectangulo {
    #area = 0;

    constructor(base = 0, altura = 0) {
        this.base = base;
        this.altura = altura;

        this.#area = base * altura;
    }

}

const rectangulo = new Rectangulo(10, 15);
rectangulo.#area = 100; 
console.log(rectangulo);
```

![Untitled](00%20🌎%20DWEC%202022-2023/03%20UD5%20POO/Anexos/Clases%208780d165e3ba45839399d1f4f3497ff2/Untitled%2010.png)

<aside>
💡 Aún no tenemos métodos privados implementados

</aside>