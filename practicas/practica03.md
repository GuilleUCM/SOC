% Prácticas de Desarrollo de Sistemas Interactivos
% Pablo Moreno Ger (pablom@fdi.ucm.es); Guillermo Jiménez Díaz (gjimenez@ucm.es)
% Curso 2013-2014

# Acerca de las prácticas de la asignatura {-}

La asignatura de Desarrollo de Sistemas Interactivos incluye un conjunto de prácticas para realizar en grupo, que representan un 30% de la calificación final.

Los grupos de prácticas se formarán al principio del curso, con un mínimo de 4 alumnos y un máximo de 6, y deberán mantenerse para todas las entregas del curso.

El resultado de todas las prácticas deberá entregarse en el campus virtual, en las fechas y formatos indicados en el enunciado de cada una de las prácticas.

# Práctica 3: Evaluación Heurística {-}
\setcounter{section}{3}

En esta última práctica vamos a realizar una evaluación heurística de los prototipos desarrollados en las anteriores prácticas. 

## Desarrollo de la práctica

Para esta evaluación se deberá seguir uno de los dos conjuntos de heurísticas vistas en clase --los 10 principios de diseño de Nielsen o las 8 reglas de oro de Shneiderman-- a elegir por el grupo de prácticas. La evaluación deberán hacerla por separado todos los miembros del grupo (un informe individual por persona).

El prototipo a evaluar puede ser el entregado en la práctica 2 o una modificación del mismo. En todo caso será necesario entregar dicho prototipo junto con el informe de la evaluación realizada.

Cada evaluador tendrá que evaluar el prototipo individualmente (siguiendo las pautas descritas en clase y en los apuntes) y crear un [informe individual](#infInd) de evaluación. Posteriormente, el grupo de prácticas se reunirá para analizar los informes individuales y crear [la lista unificada de problemas](#infUnif). Una vez completada y ordenada de acuerdo a la severidad media de los problemas encontrados se realizará un breve informe de [cambios y prioridades](#infCambios).

## Memoria descriptiva

Cada grupo debe entregar una memoria descriptiva del trabajo que debe incluir las siguientes secciones:

- Introducción
- Informes individuales de evaluación
- Lista unificada de problemas
- Informe de cambios y prioridades

No hay una longitud fija ya que ésta dependerá del número y longitud de los informes individuales realizados.


### Introducción

En la introducción se describirá brevemente el prototipo que se va a evaluar y cuáles son las tareas que se van a poder realizar en dicho prototipo. Así mismo se deberán enumerar cuáles son las heurísticas que se van a emplear para realizar la evaluación.


### Informes individuales de evaluación {#infInd}

Cada uno de los evaluadores tendrá que realizar un informe de la evaluación heurística realizada. Este informe ha de contener la siguiente información:

* Nombre del evaluador
* Edad
* Sexo
* Fecha y hora (inicio-fin) de la evaluación
* Datos técnicos sobre el hardware/software en el que se ha probado el prototipo: sistema operativo, navegador (si procede), tamaño y resolución del monitor, tamaño y resolución de la ventana en la que se ha visualiazdo el prototipo.
* Impresiones positivas de la aplicación: enumerar algunas de las mejores imopresiones de la aplicación, indicando en qué pantalla se han visto y, si fuera necesario, incluyendo una captura de pantalla.
* Problemas detectados: Cada problema ha de contener la siguiente información:
1. Nombre
2. Breve descripción
3. Heurística violada
3. Dónde se ha encontrado
4. Si es necesario, una captura de pantalla para visualizar el problema.
5. Grado de severidad del problema: Será un valor entero entre 0 y 4 (no son válidas fracciones) donde cada valor representa lo siguiente:

    4 = Problema catastrófico

    3 = Problema serio

    2 = Problema menor

    1 = Problema estético
    
    0 = No es un problema

Se recomienda seguir un formato para las anotaciones que facilite después la integración de los informes en una lista unificada de problemas.

### Lista unificada de problemas {#infUnif}

A partir de los informes individuales de la sección anterior, hay que generar una lista unificada de problemas. Tal y como se ha discutido en clase, esto se hace agregando las evaluaciones de todos los evaluadores (problemas y severidades) y calculando el promedio de las severidades.

Es importante recordar que si un determinado elemento tiene dos problemas de usabilidad (es decir, viola dos heurísticas distintas), entonces tiene que figurar dos veces, uno por cada principio violado.

Junto con este enunciado se incluye un archivo Excel con una plantilla para el resumen unificado de la evaluación heurística.

### Informe de cambios y prioridades {#infCambios}

Es un breve informe en el que se explicarán qué problemas de los encontrados por los evaluadores se abordarían en caso de poder realizar una nueva iteración de diseño y qué cambios se propondrían. Este informe no ha de dar solución a todos los problemas sino establecer unas prioridades sobre los principales problemas encontrados y decidir cómo los resolveríamos.

 
## Entrega

La práctica se entregará en el campus virtual, antes de las 23:55 del día 31 de enero de 2014. 

La entrega de la práctica será un archivo .zip con los siguientes contenidos:

* _Alumnos.txt_: Un archivo con los nombres de todos los integrantes del grupo.
* _Memoria.pdf_: La memoria de la práctica. 
* _Prototipo.pdf_: El prototipo que ha sufrido la evaluación

El archivo puede ser subido por cualquiera de los integrantes del grupo (sólo una entrega).
