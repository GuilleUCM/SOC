% Prácticas de Desarrollo de Sistemas Interactivos
% Pablo Moreno Ger (pablom@fdi.ucm.es); Guillermo Jiménez Díaz (gjimenez@ucm.es)
% Curso 2013-2014

# Acerca de las prácticas de la asignatura {-}

La asignatura de Desarrollo de Sistemas Interactivos incluye un conjunto de prácticas para realizar en grupo, que representan un 30% de la calificación final.

Los grupos de prácticas se formarán al principio del curso, con un mínimo de 4 alumnos y un máximo de 6, y deberán mantenerse para todas las entregas del curso.

El resultado de todas las prácticas deberá entregarse en el campus virtual, en las fechas y formatos indicados en el enunciado de cada una de las prácticas.

# Práctica 1: Prototipos en papel

Como primera práctica, vamos a construir prototipos en papel que representen los pasos necesarios para realizar un conjunto de tareas en distintas herramientas interactivas.

El prototipado en papel es una forma de prototipado rápido de menor coste que el desarrollo de prototipos software, permite explorar y descartar ideas de forma rápida, y facilita el proceso de presentar ideas de interacción al equipo de trabajo o al cliente.

Para el desarrollo de esta práctica, se puede consultar el documento _Introducción al prototipado en papel_ disponible en el campus virtual de la asignatura.

## Desarrollo de la práctica

El objetivo formal de esta práctica es diseñar en papel una interfaz para una aplicación (a escoger entre un conjunto de posibles temáticas) y simular sobre ella los pasos necesarios para realizar un conjunto predefinido de acciones.

La simulación de las interfaces deberá ser grabada en un vídeo, que será presentado en clase junto con una exposición sobre las decisiones de diseño tomadas.

### Elección del trabajo y preparación de los prototipos

En la [siguiente seccion](#dominios) se describen los posibles tipos de aplicación (o dominios) sobre los que se puede trabajar. Son todos dominios muy comunes, para los que existen distintas aplicaciones específicas con distintas interfaces.

Para cada dominio, se describe un conjunto de tareas específico que deben poder realizarse mediante la interfaz.

Cada grupo debe elegir un tipo de aplicación para trabajar, y deberá crear prototipos en papel de la interfaz dando soporte a todas las tareas indicadas. Para ello, se pueden copiar los elementos de las interfaces de aplicaciones ya existentes, o se pueden proponer nuevos mecanismos de interacción.

Una vez construida la interfaz en papel, se deben añadir los elementos interactivos simulados necesarios para completar las tareas. En el documento _Introducción al prototipado en papel_ disponible en el campus virtual se dan consejos sobre cómo preparar los prototipos, así como ejemplos de vídeos de prototipos en papel "interactivos".

### Dominios de los prototipos{#aplicaciones}

Cada grupo debe elegir uno de los siguientes tipos de aplicación para trabajar. Para cada tipo, se indican las tareas que deben contemplarse. Es aceptable que más de un grupo trabaje sobre un mismo tipo de aplicación.

Una vez escogido el tipo, se puede tomar una aplicación de referencia y reproducir su interfaz, o se puede proponer una completamente nueva. Si se reproduce una existente, es posible que alguna de las tareas a realizar no esté contemplada, por lo que el grupo tendrá que decidir cómo implementa la tarea. En cualquier caso, es recomendable intentar proponer mejoras a la interacción por defecto.


#### Herramienta de correo{-} 

La aplicación es un gestor de correo electrónico, que permite gestionar una cuenta de correo, listas de contactos, trabajo con archivos adjuntos, etc.

Ejemplos existentes:

- Outlook
- Gmail
- Thunderbird
- Sparrow
- Mailbird

Tareas que se deben implementar:

- **Leer y responder correo:** Desde la vista inicial (habitualmente una lista de los correos recibidos, con o sin previsualización) seleccionar un correo específico y ver su contenido. A continuación, enviar una respuesta a todos los destinatarios (Reply-All).
- **Redactar un nuevo mensaje:** Partiendo de la pantalla inicial, empezar a crear un mensaje desde cero. Añadir varios destinatarios (To, CC y BCC) y redactar el cuerpo del mensaje. Adjuntar una foto y finalmente enviar.
- **Agregar un contacto desde un mensaje:** Partiendo de un mensaje, queremos añadir al emisor a nuestra lista de contactos. El resultado final es añadir a la lista de contactos un nuevo contacto con nombre, apellidos, teléfono y, por supuesto, la dirección de correo desde la que había enviado el mensaje.

#### Red social{-} 

Una aplicación web de gestión de una red social. Permite gestionar una lista de contactos (que se pueden agrupar en subconjuntos / grupos / círculos / listas), publicar contenido nuevo, compartir con nuestros contactos contenido generado por otros usuarios, etc.

Ejemplos existentes:

- Facebook
- Google+
- Twitter
- YouTube
- Tuenti

Tareas que se deben implementar:

- **Publicar un nuevo mensaje:** Desde la vista inicial (habitualmente el timeline, la lista de posts o la lista de contactos) publicar un nuevo aporte de contenido. Se debe distinguir entre compartir con todos los contactos o sólo con un subgrupo.
- **Compartir un contenido:** Partiendo de un elemento de contenido producido por uno de nuestros contactos (un post, una actualización, un tweet, un vídeo, etc.), compartir el contenido con nuestros contactos. Se puede añadir un comentario adicional al compartir el contenido. De nuevo, se debe distinguir entre compartir con todos los contactos o sólo con un grupo.
- **Organizar a los contactos en grupos:** Partiendo de una representación de la lista de contactos y de las agrupaciones (listas, grupos, círculos), reorganizar los contactos en varios grupos. La tarea incluye pasar un contacto de un grupo a otro.


#### Entorno Integrado de desarrollo{-}

Un entorno como pueden ser Eclipse o Visual Studio, que integra el editor, el compilador y la funcionalidad para depurar programas ejecutando paso a paso.

Ejemplos existentes:

- Eclipse
- Visual Studio
- XCode
- NetBeans

Tareas que se deben implementar:

- **Creación de un proyecto multi-archivo:** Desde la vista inicial, construir un nuevo proyecto que vaya a incluir múltiples archivos de código fuente, prestando especial atención a cómo se van gestionando los archivos del proyecto (agregar archivos, reorganizar, etc.).

- **Depuración paso a paso:** Proceso para depurar un programa paso a paso (entrando en subprogramas o no), incluyendo mecanismos para la inspección de variables.

- **Detección y arreglo de errores:** Tanto Eclipse como Visual Studio van marcando los errores de compilación a medida que escribimos el código, empleando metáforas distintas. Además, Eclipse ofrece la posibilidad de arreglos automáticos de código para muchas situaciones. 


#### Tienda online (_e-commerce_){-}

Una tienda online que permite explorar un catálogo de productos, incluye funciones de recomendación, gestiona procesos de compra y maneja listas de deseos para los usuarios registrados.

Ejemplos existentes:

- Amazon
- Fnac
- Alternate
- ThinkGeek

Tareas que se deben implementar:

- **Explorar productos:** Esta tarea incluye la posibilidad de explorar categorías, de realizar búsquedas y de filtrar resultados según distintos criterios. También de recomendar productos a partir del historial de búsquedas y compras.  

- **Proceso de compra:** Todos los pasos desde la página del producto hasta la confirmación del envío: añadir al carro, registro/login, datos de pago, confirmación del envío, etc. Es el proceso más tedioso, y se corre el riesgo de perder clientes, por lo que se valorarán soluciones sencillas y directas para el usuario.

- **Gestión de la lista de deseos:** Los productos se añaden a la lista de deseos a partir de la descripción del producto. En las listas de deseos debe existir algún modo de aportar información sobre cuáles se "desean más" (puntuación, estrellas, ordenación, etc.), así como de eliminar objetos no deseados. Amazon permite gestionar múltiples listas de deseos.


### Preparación de vídeos

Una vez construidos el prototipo y las interacciones, el grupo deberá grabar un vídeo que represente la interacción. El vídeo se puede grabar usando los medios que escoja cada grupo (cámara, webcam, teléfono móvil). El estilo de interacción y de edición del vídeo se dejan a la elección de cada grupo. 

Únicamente se plantean los siguientes requisitos:

* Los vídeos deben durar menos de 3 minutos.
* Deben cubrirse todos los pasos necesarios para realizar todas las tareas indicadas (el vídeo puede estar dividido en bloques para cada tarea).
* Debe verse correctamente la interfaz y las acciones del usuario (click, pulsar, arrastrar, etc.).

Una vez producido el vídeo, uno de los miembros del grupo deberá subirlo a YouTube (en modo _oculto_ o _público_).


### Presentación

Las prácticas se presentarán en clase, en presentaciones de menos de 7 minutos incluyendo mostrar el vídeo. En la presentación, de formato y estructura libre, el grupo debe explicar:

* El dominio elegido.
* Si se ha copiado alguna aplicación existente.
* Qué cambios se han hecho, si la aplicación era existente, o qué cosas nuevas aportan, si la aplicación es nueva.
* Qué elementos de la interfaz son más novedosos.

## Entrega

La práctica se entregará en el campus virtual, antes de las 23:59 del día 3 de noviembre de 2013. Las presentaciones se realizarán el día 4 de noviembre durante la sesión de laboratorio.

La entrega de la práctica será un archivo .zip con los siguientes contenidos:

* _Alumnos.txt_: Un archivo con los nombres de todos los integrantes del grupo.
* _Presentación.pptx_ (opcional): La presentación que se va a emplear para la presentación pública (si es que se va a usar una) o cualquier otro recurso digital que se vaya a usar como apoyo.
* _Video.txt_: Un archivo con la URL desde la que se puede ver el vídeo.
* _Materiales_: Una carpeta con copias digitales (escaneadas, fotografiadas) de los materiales en papel usados en el prototipo (JPGs, PDFs, etc.).

El archivo puede ser subido por cualquiera de los integrantes del grupo (sólo una entrega).
