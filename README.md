# Angular y el maravilloso mundo de las SPAs

## Introducción al concepto de Single Page Applications

Esta clase tiene como objetivo introducirlos en el concepto de las SPAs y comenzar a ver a Angular como una tecnología para lograrlo.
Es interesante ver cómo esta "nueva"  forma de contruir aplicaciones web (aunque hoy en día ya tiene sus años) 
se diferencia de las maneras más "tradicionales", teniendo como objetivo entender qué diferencias residen entre una modalidad y otra.

### ¿Cómo funcionaban las web applications tradicionalmente? 

En el pasado, el flujo que exista en una aplicación web era algo así:

1) Se tenía un **Web Server** que provee "al mundo" el contenido de nuestro sitio (html, js, css, etc).
2) Luego, se utilizaba un **Browser** para ir a buscar dicho contenido, a partir de una solicitud HTTP.  Por ejemplo, cada vez que entramos a **http://www.starwars.es/**

En el momento en el que obteníamos la página, nuestro **Browser/Explorador** tenía la lógica para mostrarla (renderizarla), y, en cada interacción/clic/evento subsiguiente que nosotros dispararamos sobre dicho html,
el browser se encargaba de ir a pedir un nuevo .html al Web Server para mostrar el contenido asociado al mismo.

IMAGEN - Intercambio Requests

Este tipo de aplicaciones son conocidas como **Round-Trip Applications** (o **RTAs**).

Durante mucho tiempo, las aplicaciones web se fueron pensando como Round-Trip: El Browser hace el request inicial del documento HTML al servidor, las interacciones del Usuario hacían que el browser solicitara y recibiera un documento HTML completamente nuevo cada vez. En este tipo de aplicación, el browser es solo una especie de renderer de HTML, y toda la lógica de la aplicación va del lado del servidor. El browser realiza una serie de Requests HTTP sin estado que el server maneja generando documentos html dinámicamente.


Este modelo, si bien se sigue usando hoy en día, tiene algunas **desventajas**. Por ejemplo:

1) El usuario debe esperar mientras el siguiente documento HTML se genera, requieren mayor infraestructura del lado del servidor para procesar todos los requests y manejar el estado de la aplicación, y requieren más ancho de banda, ya que cada documento HTML debe estar autocontenido.


2) A su vez, la experiencia de usuario se degrada por factores como el efecto de refreshing (pestañeo) y el tiempo en ir a pedir los recursos al servidor.

### ¿Cómo funcionan las SPAs? 

Las *SPAs* toman un enfoque diferente. Un HTML inicial se envía al browser, pero las interacciones del usuario generan requests a través de ajax para pequeños fragmentos de HTML o datos que se inserta en el conjunto de elementos que se muestra al usuario. 

El documento HTML inicial nunca se recarga, y el usuario puede seguir intercalando con el html existente mientras las requests ajax terminan de ejecutarse asincrónicamente.

AngularJS logra sus mejores resultados cuando la aplicación a desarrollar se acerca al modelo de Sigle-page. No quiere decir que no se pueda usar para round-trip, pero hay otras herramientas, como Jquery, que lo hacen mejor.
 

## ¿Qué es Angular?

La meta de angular es traer las herramientas y capacidades que han estado disponibles para el desarrollo de back-end al cliente web, facilitando el desarrollo, test y mantenimiento de aplicaciones web complejas y ricas en contenido.

Angular funciona permitiéndonos extender HTML, expresando funcionalidad a través de elementos, atributos, clases y comentarios. 

El estilo de desarrollo de Angular se deriva del uso del patrón MVC, aunque suelen referirse a él como MV*, dada la cantidad de variaciones al patrón a las que se adhieren cuanod se desarrolla. 

## ¿Para qué sirve?

No es la solución para cada problema, y hay que saber cuando utilizarlo o buscar una alternativa.
Dado lo que angular provee, significa que tiene mucho trabajo para hacer cada vez que un documento HTML al que se le aplicó Angular se carga (compilar elementos hl, evaluar bindings, ejecutar directivas, etc). Este tipo de trabajo lleva tiempo para perforar, y ese tiempo depende de la complejidad del documento HTML, el código JS asociado y -más critico aún - la calidad del navegador y la capacidad de procesamiento del dispositivo.
En una máquina nueva con las últimas actualizaciones de Browsers no debería notarse ningún lag, pero en viejos smartphones, el setup puede llevar mucho tiempo. El objetivo, entonces, es realizar el setup tan infrecuentemente como sea posible, y entregar la mayor cantidad de  la app al usuario cuando se hace. 

## Round-Trip vs SPA

Durante mucho tiempo, las aplicaciones web se pensaban como Round- trip: El browser hace el request inicial del documento HTML al servidor, las interacciones del Usuario hacían que el browser solicitara y recibiera un documento HTML completamente nuevo cada vez. En este tipo de aplicación, el browser es solo una especie de renderer de HTML, y toda la lógica de la aplicación va del lado del servidor. El browser realiza una serie de Requests HTTP sin estado que el server maneja generando documentos html dinámicamente.
Este modelo, si bien se sigue usando hoy en día, tiene algunas desventajas: El usuario debe esperar mientras el siguiente documento HTML se genera, requieren mayor infraestructura del lado del servidor para procesar todos los requests y manejar el estado de la aplicación, y requieren más ancho de banda, ya que cada documento HTML debe estar autocontenido.

SPAs toman un enfoque diferente. Un HTML inicial se envía al browser, pero las interacciones del usuario generan requests a través de ajax para pequeños fragmentos de HTML o datos que se inserta en el conjunto de elementos que se muestra al usuario. El documento HTML inicial nunca se recarga, y el usuario puede seguir intercalando con el html existente mientras las requests ajax terminan de ejecutarse asincrónicamente.

AngularJS logra sus mejores resultados cuando la aplicación a desarrollar se acerca al modelo de Sigle-page. No quiere decir que no se pueda usar para round-trip, pero hay otras herramientas, como Jquery, que lo hacen mejor.
 
## El problema que Angular quiere resolver

Complejidad de manejar el DOM  y la lógica de una aplicación manualmente.
