# Varios constructores
#javascript
<aside>
💡 JS no permite varios constructores como en Java. Hay un truco y se usa muchísimo sobre todo cuando recibamos JSON de peticiones HTTP.

</aside>

```jsx
class Persona {

    //como JS no permite varios constructores, creará una instancia utilizando 
    //el método estático y la desestructuración
    static porObjeto( {nombre, apellido, pais} ) {
        return new Persona(nombre, apellido, pais);
    }

    constructor( nombre, apellido, pais ){
        this.nombre = nombre;
        this.apellido = apellido;
        this.pais = pais;
    }

    getInfo() {
        console.log(`info: ${this.nombre} ${this.apellido}, ${this.pais}`);
    }
}

const nombre    = 'Lola',
      apellido1 = 'Flores',
      pais      = 'España';

const antonio = {
    nombre: 'Antonio',
    apellido: 'Flores',
    pais: 'España'
}

const persona1 = new Persona(nombre, apellido1, pais);
const persona2 = Persona.porObjeto(antonio);

persona1.getInfo();
persona2.getInfo();
```

![Untitled](00%20🌎%20DWEC%202022-2023/03%20UD5%20POO/Anexos/Varios%20constructores%206fe113b570e546aaa1401d25510bcbee/Untitled.png)