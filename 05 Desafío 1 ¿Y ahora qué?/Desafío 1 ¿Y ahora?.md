#javascript #webpack

# ¿Y ahora?

# Desafío 1

Vamos a desarrollar una herramienta simplificada para planificación y gestión de tareas.

Esta herramienta tendrá una apariencia similar a la siguiente:

![Untitled](00%20🌎%20DWEC%202022-2023/05%20Desafío%201%20¿Y%20ahora%20qué?/Anexos/Untitled.png)

Tendremos la siguiente funcionalidad:

- De forma preestablecida (no parametrizable), tendremos 3 paneles como puedes ver en la figura: **Lista de tareas, En proceso y Hecho**.
- Cada panel contendrá una serie de tarjetas que podremos **crear, borrar y editar**.
- Cada tarjeta se corresponderá con una **tarea**.
- Una tarea deberá contener como mínimo la siguiente información:
    - **Label**
    - **Etiqueta**
    - **Imagen** (link externo)
    - **Checklist** (subtareas completadas)
- Las etiquetas de una tarea serán también fijas y establecerán prioridades: **Alta, Media, Baja.**
- Las subtareas de una tarjeta se podrán ir completando:

![Untitled](00%20🌎%20DWEC%202022-2023/05%20Desafío%201%20¿Y%20ahora%20qué?/Anexos/Untitled%201.png)

- Además, las tarjetas podremos desplazarlas mediante `drag and drop` entre los distintos paneles.
- Cuando el usuario cierre el navegador, y vuelva a abrirlo deberá ver las tareas que tiene y el estado actual de éstas (utilizaremos persistencia mediante `LocalStorage`)

# Requisitos de Desarrollo Web en Entorno Cliente

- Generación de código utilizando POO.
- Utilización correcta de funciones.
- Utilización correcta de las estructuras de almacenamiento en JS.
- Utilización correcta de los métodos de almacenamiento en el navegador del cliente.
- Estructuración del proyecto en distintos módulos e importaciones optimizadas.
- Generación de un proyecto utilizando `webpack`.
- Iniciación a la metodología **agile SCRUM:**
    - Planificación de tareas por unidades funcionales completas. Coherencia.
    - Sprints desarrollando lo planificado.
    - Proyecto sincronizado con un repositorio en Github que se envía al profesor para su seguimiento.

# Requisitos de Diseño de Interfaces Web

- La generación de todo nuestro CSS lo vamos a hacer por medio de SASS.
- Para este desafío vamos a utilizar como framework base: skeleton y haremos las modificaciones necesarias para conseguir nuestros objetivos. Estas modificaciones deben sobreescribir la hoja de estilo de skeleton, es decir, dejaremos su hoja tal cual. Deben estar incluidos, al menos, los elementos que se pidieron como componentes en el foro de "modificaciones de skeleton": menu vertical, menu horizontal, menu desplegable, menu pestañas y acordeon.
- Vamos a crear 2 estilos generales ( o temas ) para aplicar a nuestro sitio web. Estos estilos se podrán aplicar al mismo [HTML](https://aulasciclos2223.castillalamancha.es/mod/resource/view.php?id=55910) cambiando solo una clase del body, por lo tanto los selectores deben estar bien definidos pues se deben usar la menor cantidad de clases posibles. Los temas deben diferenciarse al menos en los elementos definidos en la guía de estilo.
- Un mismo menú de navegación se verá en formato de pestañas y otro en formato de menú horizontal, dependiendo del estilo aplicado.
- Se deben diseñar 2 maquetaciones diferentes de los elementos. Una con el menú de navegación en la parte superior y el otro con el menú en la parte izquierda.
- Aunque no sean funcionales se debe un menu para poder realizar la interfaz.
- Como documentación se debe entregar lo siguiente:
1. Guía de estilo.
2. Wireframes de las pantallas principales, en formato PC y movil.
3. En la Wiki de Github se crearán una sección: "componentes adicionales de skeleton", donde se explicará como se usan los componentes creados a modo de snippet.