# DOM, eventos
#javascript

[GitHub - igijon/javascript-blackjack: Iniciación de JavaScript (sintaxis básica, DOM y eventos)](https://github.com/igijon/javascript-blackjack)

El *DOM* (Document Object Model en español **Modelo de Objetos del Documento**) es una [API](https://developer.mozilla.org/es/docs/Glossary/API) definida para representar e interactuar con cualquier documento [HTML](https://developer.mozilla.org/es/docs/Glossary/HTML) o [XML](https://developer.mozilla.org/es/docs/Glossary/XML). El DOM es un modelo de documento que se carga en el [navegador web](https://developer.mozilla.org/es/docs/Glossary/Browser) y que representa el documento como un árbol de nodos, en donde cada nodo representa una parte del documento (puede tratarse de un [elemento](https://developer.mozilla.org/es/docs/Glossary/Element), una cadena de texto o un comentario).

El DOM es una de las APIs más usadas en la [Web](https://developer.mozilla.org/es/docs/Glossary/World_Wide_Web), pues permite ejecutar código en el navegador para acceder e interactuar con cualquier nodo del documento. Estos nodos pueden crearse, moverse o modificarse. Pueden añadirse a estos nodos manejadores de eventos (*event listeners* en inglés) que se ejecutarán/activarán cuando ocurra el evento indicado en este manejador.

El DOM surgió a partir de la implementación de [JavaScript](https://developer.mozilla.org/es/docs/Glossary/JavaScript) en los navegadores.

`document` hace referencia a todo el documento.

# Selección de elementos

Desde los elementos (herramientas de desarrollo de Chrome) puedo acceder a todos los elementos del DOM y todo esto se puede manipular desde la sintaxis que vemos en el proyecto.

![Untitled](00%20🌎%20DWEC%202022-2023/01%20UD3%20DOM%20y%20eventos%20Proyecto%20Blackjack/Anexos/Untitled.png)

![Untitled](00%20🌎%20DWEC%202022-2023/01%20UD3%20DOM%20y%20eventos%20Proyecto%20Blackjack/Anexos/Untitled%201.png)

![Untitled](00%20🌎%20DWEC%202022-2023/01%20UD3%20DOM%20y%20eventos%20Proyecto%20Blackjack/Anexos/Untitled%202.png)

![Untitled](00%20🌎%20DWEC%202022-2023/01%20UD3%20DOM%20y%20eventos%20Proyecto%20Blackjack/Anexos/Untitled%203.png)

![Untitled](00%20🌎%20DWEC%202022-2023/01%20UD3%20DOM%20y%20eventos%20Proyecto%20Blackjack/Anexos/Untitled%204.png)

Hay que intentar minimizar las llamadas a `querySelector` porque cada vez que se hacen, JS hace un barrido al HTML.

[Underscore.js](https://underscorejs.org/)

# Creación de elementos

Ponemos un id al div de botones, y vamos a ver cómo añadir un botón al div y añadir clases a este botón.

![Untitled](00%20🌎%20DWEC%202022-2023/01%20UD3%20DOM%20y%20eventos%20Proyecto%20Blackjack/Anexos/Untitled%205.png)

![Untitled](00%20🌎%20DWEC%202022-2023/01%20UD3%20DOM%20y%20eventos%20Proyecto%20Blackjack/Anexos/Untitled%206.png)

Dependiendo del tipo de elemento que manipulemos tendremos unas propiedades a las que accederemos.