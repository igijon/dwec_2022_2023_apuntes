#typescript #angular
# 3. Estructura del proyecto

- package.json: no debemos modificarlo manualmente. Tiene los paquetes y dependencias de nuestro proyecto entre otras cosas.
- tslint.json: fichero de configuración del lint con reglas que nos obligan para programar de cierta manera. De momento no lo modificaremos.
- tslint.spec.json: añade cosas al tslint.json porque son para pruebas (unitarias o de integración)
- karma.conf.js: fichero de configuración de pruebas karma
- angular.json: configuraciones importantes de la aplicación. Carga los assets (recursos estáticos de la aplicación). Raíz inicial del .css…
- .gitignore: para no dar seguimiento en el proyecto.
- src: carpeta sources: estos ficheros son el componente principal (vista, estilos y comportamientos)
    - app.component.css
    - app.component.html
    - app.component.spec.ts (pruebas)
    - app.component.ts: es una clase con un decorador concreto que recibe un objeto con el selector del componente, el template (html), css…
    - app.module.ts: los módulos que componen la aplicación. Es como un agrupador de componentes. Es una clase con un decorador concreto que la convierte en módulo.
    
    ****************************Vemos que en index.html se inyecta el componente <app-root> que es el generado por app.component.ts.****************************
    
    - environments: directorio donde tenemos las variables de entorno. Podemos tener un fichero para desarrollo y otro para producción.
    - main.ts no se suele tocar porque tiene que ver con el punto de arranque.
    - styles.css se aplica a nivel general.
- node_modules: dependencias y descargas
- e2e: carpeta para testing

[GitHub - igijon/angular-bases: Proyecto base de Angular](https://github.com/igijon/angular-bases)