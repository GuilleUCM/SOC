% Análisis de Redes Sociales
% Guillermo Jiménez Díaz (gjimenez@ucm.es); Alberto Díaz (albertodiaz@fdi.ucm.es)
% Curso 2014 - 2015

# Prefacio {-}

Estos son las prácticas de la asignatura Análisis de Redes Sociales, impartida en la Facultad de Informática de la Universidad Complutense de Madrid por los profesores Guillermo Jiménez Díaz y Alberto Díaz, del Departamento de Ingeniería del Software e Inteligencia Artificial.

Este material ha sido desarrollado a partir de distintas fuertes, destacando como referencia principal el libro _Network Science_ de Laszlo Barabasi, el material de la asignatura _Social Network Analysis_, impartido por Lada Adamic a través de Coursera, y las transparencias de la asignatura Redes y Sistemas Complejos, creadas por Óscar Cordón García de la Universidad de Granada.

Este obra está bajo una [licencia de Creative Commons Reconocimiento-NoComercial-CompartirIgual 4.0 Internacional](http://creativecommons.org/licenses/by-nc-sa/4.0/).

# Práctica 1: Análisis básico de una red con Gephi y Netvizz

Esta práctica tiene una parte de trabajo individual y otra de trabajo en grupo.En primer lugar cada alumno deberá analizar su propia red social de amigos en Facebook y posteriormente se deberán discutir las diferencias y similitudes entre las redes de cada uno de los alumnos del mismo grupo.

En primer lugar hay que usar la aplicación Netvizz de Facebook <https://apps.facebook.com/netvizz> para generar la propia red social de amigos del alumno en Facebook (personal friend network). Al crear la red no es necesario incluir ningún dato adicional como la contabilización de los "me gusta" de los amigos (no es necesario marcar el checkbox), aunque el alumno puede "jugar" con su red fuera del desarrollo de la práctica. 

Una vez generada la red, se cargará en Gephi y se realizarán tareas básicas de
análisis y visualización. Si la red presenta más de una componente conexa, se
recomienda usar Force Atlas 2 como algoritmo de layout (Distribución). Para evitar que las componentes conexas queden fuera de la vista principal que muestra la componente gigante, fijar el valor del parámetro Gravedad en Puesta a punto en torno a 20. Si todo queda demasiado amontonado, se puede probar a marcar la opción Disuadir Hubs y/o Evitar el solapamiento. Los aspectos estéticos de la visualización se dejan al parecer del propio alumno, que puede probar las distintas variantes de algoritmos de layout implementados en Gephi y de parámetros para determinar cuál le proporciona la distribución que más le guste

Para los primeros pasos del análisis, comenzaremos por anotar los valores de las medidas globales básicas: número de nodos N y número de enlaces L, que aparecen directamente en la ventana Contexto, además de calcular manualmente el número máximo de enlaces Lmax. Posteriormente, calcularemos las restantes medidas globales (grado medio <k>, diámetro dmax y distancia media d) ejecutando las opciones correspondientes en la ventana Estadísticas.

Al realizar el cálculo del grado medio, obtendremos también la distribución de
grados de la red completa, que debemos grabar (Gephi lo guarda en una carpeta con una imagen png y un fichero html). El cálculo del diámetro nos proporciona también el valor de la distancia media, que anotaremos, y la distribución de distancias, que guardaremos, así como otras muchas medidas, varias de las cuales estudiaremos en temas de teoría posteriores como por ejemplo la Centralidad.

La opción Densidad de grafo nos mide la relación entre número de enlaces L y
el número máximo de enlaces Lmax. La ejecutaremos y anotaremos el valor.
Finalmente, ejecutaremos la opción Coeficiente medio de clustering para obtener
la medida del mismo nombre, <C>. Dicha opción nos proporcionará también la
distribución del coeficiente de clustering en la red, que guardaremos.

Ahora pasaremos a analizar la conectividad de la red. En primer lugar,
obtendremos el número de componentes conexas ejecutando la opción Componentes
conexos y lo anotaremos. Luego nos centraremos en la componente gigante y
calcularemos su número de nodos. Para ello, iremos a Filtros, seleccionaremos
Topología->Componente gigante y arrastramos el filtro a la ventana de abajo llamada Consultas donde pone Arrastrar filtro aquí. Entonces pulsaremos en el botón Filtrar con la flecha verde en la esquina inferior izquierda de la pantalla. La visualización cambiará y sólo mostrará la componente gigante. La ventana Contexto en la esquina superior izquierda nos mostrará el número de nodos y enlaces de dicha componente y sus porcentajes con respecto a la red total, los cuales anotaremos.

Una vez realizadas todo esto, cada alumno guardará el proyecto desde Gephi
nombrándolo con sus apellidos y su nombre propio. Por otro lado, cada alumno del grupo almacenará todos los valores obtenidos en una tabla incluida en un fichero Excel llamado con el nombre del alumno.

La última tarea a realizar será escribir un pequeño análisis de las redes estudiadas a partir de los valores de medidas y de las gráficas de distribución de grados, distancias, etc. obtenidas. En particular hay que explicar como se ajustan los valores obtenidos a los modelos de redes aleatorias. Hay que realizar un análsis individual de cada red, así como discutir la similitud o diferencia entre las redes analizadas por cada uno. No se trata de escribir mucho sino de hacer un análisis razonable considerando los conocimientos limitados que todavía tenemos sobre el análisis de redes.



# Entrega

La práctica se entregará en el campus virtual, antes de las 23:59 del día 2 de noviembre de 2013.

La entrega de la práctica será un archivo .zip (etiquetado con el número de grupo _GrupoXX_) con los siguientes contenidos:

* _Documentación.pdf_: Un archivo pdf que deberá incluir, al menos, el siguiente contenido:
    -   Portada con el número y título de la práctica.
    -   Número de grupo.
    -   Nombre y apellidos de los integrantes del grupo.
    -   Para cada una de las redes de cada alumno
        +   Una imagen de la red completa y otra de la componente gigante con una visualización lo más estética posible.
        +   La tabla excel con los valores de las medidas estudiadas.
        +   Los gráficos de las distruciones de grado, distancia, etc.
        +   Un análisis de la red en función de los datos anteriores.
    -   Una comparativa de las distintas redes analizadas.
    -   Referencias bibliográficas u otro tipo de material distinto del proporcionado en la asignatura que se haya consultado para realizar la práctica. 
* Ficheros obtenidos con netvizz para cada red.
* Un fichero excel con los datos de todas las redes analizadas.

El archivo puede ser subido por cualquiera de los integrantes del grupo (sólo una entrega).
