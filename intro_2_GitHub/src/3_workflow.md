# Como vamos a trabajar en GitHub

Si bien git por si solo permite colaborar de manera ágil con miles de
personas en todo el mundo, GitHub no solo provee una plataforma para
alojar el código sino que da una variedad de herramientas que
facilitan la construccón colaborativa de software de calidad. En ITAM
For Code queremos utilizar estas herramientas para trabajar entre
nosotros y para contribuir a proyectos open source mucho más grandes.
Algunas de las cosas en las que nos estaremos enfocando son: _issues_,
_pull requests_, _milestones_ y _projects_.

Cada _repo_ puede tener asociados sus propios _issues_, etc... Puedes
encontrar la pestaña para accesarlos en la página principal del _repo_
como se muestra en la foto:

![Repo navbar](figs/repo_navbar.png)

## Pull Requests

Los _pull requests_ son el concepto más importante de este capítulo.
Si no puedes leer el resto del capítulo, es indispensable que leas por
lo menos esta sección.

Los _pull requests_, como su nombre sugiere, son peticiones que hace
una persona que hizo cambios a un repo para que las personas
encargadas del mantenimiento lo revisen y quizás incorporen los
cambios al código principal. Los pull requests se pueden hacer por
personas con permisos de modificar el código directamente, o por
personas que hayan hecho un _fork_ del _repo_ porque no tienen ese
permiso. Para las personas con permisos pueden ser una petición al
resto del equipo para que revisen su código y aprueben los cambios
hechos. Para las personas que hacen un _pull request_ mediante un
_fork_ es una prupuesta para incorporar sugerencias. Por ejemplo para
resolver un _issue_ creado o proponer nueva funcionalidad.

### ¿Cómo crear un _pull request_?

Esta guía está enfocada a la creación de _pull requests_ mediante
_forks_ porque es un caso de uso más común. Para eso, se necesita
tener un _fork_ listo. Retomamos el ejemplo de _fork_ en los primeros
capítulos de la guía. Digamos que después de haber clonado
`ÌTAM4Code/Cursos`, haberlo clonado, y hacer cambios a él[^1], una vez
sincronizado GitHub, aparecerá una pantalla similar a la siguiente en
la página principal del _repo_.

[^1]: Esto puede sonar muy vago, y lo es. Los detalles de cómo clonar,
  modificar y "sincronizar" cambios con GitHub están en la guía
  específica de git.

![Sugerencia de pull request](figs/repo_pr_suggestion.png)

En el área marcada con el rectángulo rojo se encuentra el área en la
que se muestra el mensaje de confirmación de los cambios más
recientes. En este caso, GitHub sabe que este _repo_ es un _fork_ de
otro repo, y además nota que están en versiones distintas. En este
caso el _fork_ está adelantado al original. Es decir, hay cambios en
el _fork_ que no están en el original, y por lo tanto se puede hacer
un pull request. Y efectivamente, en el lado derecho del recuadro
GitHub da un botón para crear uno nuevo. Al hacer click se puede ver
la siguiente pantalla:

![Primer paso de un PR](figs/pr_1st_step.png)

En esta primera pantalla GitHub muestra una comparación de los cambios
en el _fork_ vs. el original. Si no hay conflictos[^2] GitHub dará la
opción de crear un Pull Request y se puede continuar el proceso dando
click al botón verde.

[^2]: Otro concepto que se explora más en la guía de git

![Segundo paso de un PR](figs/pr_2nd_step.png)

En este paso vemos dos áreas para llenar información, una a la derecha
y otra a la izquierda. En la izquierda se puede llenar el título del
_pull request_ y el resto de información relevante. En la sección
sobre _issues_ detallamos un poco más sobre qué se puede incluír en
esta sección.

Del lado derecho hay una variedad de opciones:

1. Assignees
2. Labels
3. Projects
4. Milestones
5. Issues

Sin muchos detalles, esto es lo que cada campo se refiere:

1. Permite asignar personas o equipos específicos para que revisen
   este _issue_ en particular. Usualmente esto está reservado para las
   personas que administran el _repo_.

2. Los _labels_ son etiquetas que se dan al issue. Como se mencionaba
   un issue puede referirse a muchas cosas y esto ayuda a organizar
   _issues_ de la misma categoría. Puedes dar click y explorar las
   opciones, es común que cada proyecto decida qué labels quiere usar.

3. Los proyectos son tableros que permiten catalogar _issues_ en
   categorías como: por hacer, en progreso, y resueltas. Se hablará
   más de los proyectos más tarde.

4. Los _milestones_ son listas que se pueden crear con issues
   espcíficos ordenados por prioridad. Se crean cuando se tiene un
   deadline en mente y se quiere ir revisando el progreso.

5. Se pueden resolver _issues_ mediante _pull requests_. Si un _pull
   request_ culmina con éxito, el _issue_ asociado se resolverá.

### ¿Cómo cerrar un _pull request_?

Una vez creado un _pull request_ aparecerá en la pestaña de _pull
requests_ en la página principal del _repo_. Si se da click sobre uno
en específico se puede ver una pantalla como esta:

![Página de un pull request](figs/pr_page.png)

Aqui se pueden revisar los cambios dando click en las pestañas de
Commits o Files Changed. GitHub mostrará una página de comparación
entre el código del _fork_ y el original. En la página principal se
pueden hacer comantarios con respecto a los cambios, y sugerir otras
modificaciones para poder aceptar el _pull request_. Si después de ese
proceso se desea hacer _merge_, se puede dar click al botón verde
marcado para eso. En caso de que se rechacen los cambios se puede
cerrar sin hacer _merge_

Nota: _Merge_ es un término particular de git. Se usa para referirse
al proceso de mezclar dos versiones distintas de código a un destino.
En este caso, a el _repo_ original.

## Issues

> Every non-trivial program contains at least one bug
>
> --Murphy computer laws

Cuando se comparte software, es casi una garantía que la comunidad que
lo usa va a encontrar _bugs_ (o errores) en el funcionamiento del
código. Lo mejor que se puede hacer en estos casos es informar a quien
se encarga de dar mantenimiento al proyecto, pero hacerlo por ejemplo
por emails individuales es muy ineficiente. ¿Qué pasa si yo encuentro
un _bug_ que ya fue descubierto hace semanas y lo reporto? Estaré
duplicando información y haciendo más dificil arreglarlo.

Para mantener toda la información organizada para quien trabaje en el
proyecto y las personas que lo usan hacemos _issues_ en el repo. Los
_issues_ sirven como reportes con toda la inforamción que podría
ayudar a resolver el problema, y además también son útiles para los
usarios ya que pueden buscar ahí un problema que hayan tenido y quizás
ahi esté la solución[^1]. Los _issues_ se pueden crear por muchas
razones. Por ejemplo para reportar erroes, comportamiento inesperado,
o incluso para pedir que se agreguen cosas que nos gustaría usar. Por
ahora nos enfocaremos en reportar errores.

[^1]: Pro tip: Si estás usando software open source y te encuentras
  con un _bug_ es muy buena idea empezar a buscar soluciones en la
  pestaña de bugs en el repo que tiene el código fuente. Es posible
  que encuentres la solución, y si no es asi, podrás crear un reporte.
  Eso también es ayudar a la comunidad!

### ¿Cómo creo un _issue_?

Para crear un _issue_ pues dar click a la pestaña issues en la página
princial del repo. Ahi verás una pantalla como la siguiente:

![Patalla issues](figs/issues_page.png)

Si das click en el botón verde enorme que dice "New Issue" podrás ver
la pantalla siguiente y ahi empezar a llenar un reporte[^2].

[^2]: Algunos repos te mostrarán una pequeña página con _templates_ de
  issues. Si los usas y llenas la información qu te piden podrás
  ayudar aún mejor a que se resuelva el problema.

![Nuevo issue](figs/new_issue.png)

El la parte izquierda podrás elegir un título y llenar más
información. Trata de elegir un título corto pero ilustrativo. Abajo
del título puedes hacer comentarios más extensos, y en muchas
ocasiones se pide que se de mucha información. Puedes incorporar
código, listas, links, y todo lo que permite
[markdown](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).
Incluso puedes hacer referencia a otros _issues_ por su número de
_issue_, mencionar personas o equipos con @, o hace referencia a
commit con su número de hash[^3].

[^3]: Un número de hash es un código alfanumérico que identifica
  únicamente a un commit específico. Qué es un commit y qué es un hash
  se discuten con más claridad en las notas de git. Por ahora basta
  con pensar en un _commit_ como una versión específica del código.

En la parte derecha de la pantalla vemos las mismas opciones que las
discutidas en la sección sobre _pull requests_. Salvo que ahora
estamos ligando _issues_ a _pull request_ y no al revés.

### ¿Cómo marco un issue como resuelto?

En esencia hay dos maneras de resolver un issue:

1. Cerrarlo mediante un _pull request_
2. Cerrarlo manualmente

La primera opción es sencilla conceptualmente. Si el _issue_ actual
fue mencionado en un _pull request_, y ese recibe aprobación de
_merge_ entonces el _issue_ se cerrará automáticamente. Esto también
se puede hacer haciendo el mensaje de _commit_ algo del estilo
`closes` o `fixes` seguido de `#n` donde _n_ es el número de _issue_
que se puede ver al lado de su título en la página de _issues_. Cada
_issue_ y _pull request_ se numera en orden sucesivo a medida que se
crea.

Para cerrar un _issue_ manualmente el proceso es muy simple. Al final
de todos los comentarios hay un botón rojo que dice algo como "close
issue". Esto solo se puede hacer si tienes permisos de escritura sobre
el _repo_. Es decir, si formas parte del equipo al cual le pertenece o
si tienes invitación para colaborar.
