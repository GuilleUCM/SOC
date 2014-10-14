% Análisis de Redes Sociales
% Guillermo Jiménez Díaz (gjimenez@ucm.es); Alberto Díaz (albertodiaz@fdi.ucm.es)
% Curso 2014 - 2015

# Acerca de las prácticas de la asignatura {-}



# Práctica 0: Tutorial sobre Gephi

En esta práctica vamos a ver la herramienta Gephi, que será utilizada a lo largo de la asignatura.

## Herramientas

Debido al interés en la minería y visualización de redes se han desarrollado una gran colección de herramientas software.

Algunas son más técnicas y están dirigidas a programadores mientras que otras son más intuitivas.

La mayoría permiten el cálculo de medidas locales y globales de la red y su visualización gráfica.

Las más populares pueden ser Gephi, Pajek, UCINet, NodeXL y varias bibliotecas desarrolladas para el lenguaje R.

En particular a lo largo de la asignatura vamos a usar:

* Gephi (visualización y métricas básicas): http://gephi.org/
* NetLogo (modelado de procesos dinámicos en redes): http://ccl.northwestern.edu/netlogo/


## Primera parte: tutorial Gephi

<!-- * Material Lada: 1-2-1B: Gephi básico, 1-3-1C: cracterísticas de las buenas vizualizaciones, 1-4-1D: grado y componentes conexas. -->

* Cargar Gephi
* Abrir dining.gephi
* 26 chicas. Representa la primera y segunda elección de con quien prefieren sentarse en la cena cada una de las 26 chicas.
* Context: Número de nodos y número de enlaces. Grafo dirigido.
* Con Random layout es dificil de ver.
* Seleccionar nodo con más conexiones: aparece en ventana Edit?.
* Seleccionar Layout: Force Atlas 2
* 
* Barra de herramientas para modificar el grafo
* Tamaño nodos, color nodos
* Mostrar etiquetas de los nodos (ajustar con layout)

* Vista Laboratorio de datos
* Vista previsualización

## Segunda parte

* Medidas sobre la red
* Grado.
* Grado de salida es el mismo para todos.
* Grado de entrada da una medida de la popularidad.
* Ranking. Nodes. InDegree.
* Pintar con distintos Colores. Mejor distintos tamaños.
* Spline. Linear.
* Hay chicas más populares que otras.

* Statistics. Compute Average degree. Run.
* Ver InDegree Distribution.
* Mirar en Data LAboratory. ahora aparecen los valores de grado.
* Pulsar en la cabecera y lo ordena.
* Podemos ver quien es la chica más popular
* 
* Statistics. Connected Components. Run. Directed.
* 11 strongly connected components
* Partition. Nodes. Refresh. Strongly-connected id.
* Randomize color. Apply
* Alice is one connected component.
* 

## Tercera parte

Crearos un grafo y estudiar sus propiedades.


## Entrega

Sin entrega.

La práctica se entregará en el campus virtual, antes de las 23:59 del día 3 de noviembre de 2013. Las presentaciones se realizarán el día 4 de noviembre durante la sesión de laboratorio.

La entrega de la práctica será un archivo .zip con los siguientes contenidos:

* _Alumnos.txt_: Un archivo con los nombres de todos los integrantes del grupo.
* _Presentación.pptx_ (opcional): La presentación que se va a emplear para la presentación pública (si es que se va a usar una) o cualquier otro recurso digital que se vaya a usar como apoyo.
* _Video.txt_: Un archivo con la URL desde la que se puede ver el vídeo.
* _Materiales_: Una carpeta con copias digitales (escaneadas, fotografiadas) de los materiales en papel usados en el prototipo (JPGs, PDFs, etc.).

El archivo puede ser subido por cualquiera de los integrantes del grupo (sólo una entrega).
