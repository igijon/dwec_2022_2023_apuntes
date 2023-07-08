# UD8. Callbacks y promesas
#javascript 

[GitHub - igijon/javascript-callbacks-promesas: Proyecto de ejemplo de JS de callbacks y promesas. Proyecto usando webpack.](https://github.com/igijon/javascript-callbacks-promesas)

# Callbacks

Se tienden a desaparecer en virtud de las promesas.

<aside>
💡 Mandar una función como argumento de otra función. El objetivo es que dentro de la función que lo recibe como argumento se pueda disparar esa función.

</aside>

# Promesas

Es algo fundamental actualmente de forma nativa en JS.

<aside>
💡 Promesa es el compromiso ante la realización de algo y avisamos cuando se ha terminado el trabajo o si no se puede cumplir dicha promesa, la notificación del error.

</aside>

Las promesas no son síncronas… primero se ejecuta la función pero la promesa pasa a otro plano sin bloquear la ejecución del resto. 

Las promesas no bloquean la ejecución del programa.

# Propuesto: Buscador de personajes de Ghibli

Utilizando promesas y lo visto en el repo de ejemplo, desarrolla un programa que realice los siguiente:

- Solicite el nombre de una película al usuario, dado el nombre busque las películas que contengan dicha cadena (puede ser una única palabra).
- Además, de cada película mostrará también los personajes que aparecen en dicha película.
- Debe mostrar el resultado en un documento html y de cada película mostrará los datos más importantes como: ******************título, título original, descripción, director, fecha de lanzamiento, imagen y personajes.******************
- De los personajes mostrará: ******************************************nombre, género y edad.******************************************

Utiliza para este ejercicio el siguiente gist con algunos datos de Ghibli:

 

[JSON con datos de películas y personajes de Ghibli](https://gist.github.com/igijon/8f35f943efb4dc65ea6c194828aa714d)