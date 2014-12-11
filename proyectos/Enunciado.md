% Análisis de Redes Sociales
% Guillermo Jiménez Díaz (gjimenez@ucm.es); Alberto Díaz (albertodiaz@fdi.ucm.es)

# Proyecto final {-}
\setcounter{section}{1}

A continuación se detallan la temática y los plazos para realizar el proyecto final de la asignatura. Tal y como aparece en la ficha docente de la asignatura, el proyecto forma parte de la evaluación final y supone un 30% de la nota final de la asignatura.

El objetivo de este proyecto es formalizar los conocimientos adquiridos en el curso, bien pudiéndolos aplicar a un caso real de análisis de redes complejas, o bien desarrollando simulaciones o algoritmos similares a los descritos durante el curso y haciendo un análisis de los mismos.

La realización del proyecto consistirá en el desarrollo de una memoria explicativa del trabajo realizado y las conclusiones obtenidas, así como una presentación pública del mismo. Los proyectos deberán ser acordados con los profesores de la asignatura y deberán encajar en uno de los tipos descritos en la [Sección Tipos de proyectos](#tipos). Además, se deberán cumplir los plazos descritos en la [Sección Planificación](#plan).

## Tipos de proyectos {#tipos}

### Opción 1: Análisis empírico de una red

El objetivo general de este tipo de proyecto consiste en encontrar una fuente de datos que sea susceptible de ser interpretada como una red social, analizarlos, visualizarlos e interpretarlos. Para la realización de este tipo de proyecto es necesario realizar (y describir en la memoria) las siguientes fases:

1. Obtención de datos (30%)
    * Descripción detallada de cómo se han obtenido los datos: cuál ha sido la fuente o fuentes desde la que se han obtenido; si se ha usado datos ya existentes; código fuente de las herramientas de extracción de datos utilizadas, si procede.
    * Explicación del significado de los nodos y aristas de la red.
    * Se valorará la originalidad de los datos obtenidos.
2. Análisis de datos (40%)
    * Detallar los objetivos del análisis.
    * Descripción de las métricas o algoritmos que se van a aplicar para analizar la red.
    * Visualizaciones que faciliten la comprensión de los datos.
    * Descripción de las tareas realizadas durante el análisis de datos. Se recomienda detallar unas instrucciones en las que se explique paso a paso cómo se ha realizado el análisis.
    * Se valorará la adecuación de las métricas pedidas a los objetivos del análisis así como que el análisis se describa de tal forma que sea fácilmente reproducible (instrucciones paso a paso).
    * Adicionalmente, se valorará muy positivamente si se utilizan técnicas o métricas adicionales que no hayan sido cubiertas dentro del material de la asignatura.
3. Interpretación de los datos (30%)
    * Realizar una interpretación de los resultados obtenidos durante el análisis de los datos.
    * Detallar las limitaciones encontradas durante el análisis de los datos.
    * Describir las conclusiones más relevantes encontradas durante el análisis.
    * Adicionalmente se puede realizar una comparativa con los modelos de redes vistos durante el curso para deducir cuál es el modelo al que mejor se aproxima.
    * Se valorará principalmente la correcta interpretación de las métricas con respecto al dominio de datos elegido.

### Opción 2: Simulación de un modelo o algoritmo

El objetivo de este tipo de proyecto es la implementación y simulación de un modelo o algoritmo visto en clase y compararlo (o aplicarlo) sobre las redes utilizadas durante las prácticas. Para la realización de este tipo de proyecto es necesario realizar (y describir en la memoria) las siguientes fases:

1. Construcción del modelo o algoritmo (30%)
    * Descripción detallada del modelo o algoritmo que se va a desarrollar. 
    * Código fuente del modelo o algoritmo.
    * Aplicación asociada, documentación e instrucciones de uso.
    * Se valorará la facilidad de uso y la capacidad de automatizar su ejecución.
    * Así mismo, se valorará la originalidad del modelo o algoritmo propuesto (si es una modificación propia de un modelo propuesto en clase, si se desarrollan algoritmos o modelos que no se han visto en clase...)
2. Ejecución y pruebas del modelo o algoritmo. (40%)
    * Detallar cuáles son las pruebas a realizar y con qué algoritmos o modelos existentes van a ser comparados.
    * Describir las métricas que se utilizarán para comparar los modelos.
    * Visualización de los resultados obtenidos durante las pruebas.
    * Descripción de las tareas realizadas durante las ejecuciones y pruebas. Se recomienda detallar unas instrucciones en las que se explique paso a paso cómo se ha realizado esta fase.
    * Se valorará la adecuación de los modelos o algoritmos utilizados para realizar la comparación, así como que se describa de tal forma que sea fácilmente reproducible (instrucciones paso a paso).
    * Adicionalmente se valorará muy positivamente las pruebas adicionales que se realicen sobre el rendimiento del modelo o algoritmo implementado (en cuanto a tiempo, memoria, tamaño de la redes que procesa...)
3. Comparativa e interpretación (30%)
    * Realizar una interpretación de los resultados obtenidos durante la fase anterior
    * Detallar las limitaciones encontradas durante la ejecución de las pruebas.
    * Describir las conclusiones más relevantes encontradas durante la ejecución y la comparación con otros modelos.
    * Se valorará principalmente la correcta interpretación de los resultados con respecto a los modelos o algoritmos usados durante la comparación.

## Planificación {#plan}

El proyecto tendrá que realizarse teniendo en cuenta la siguiente planificación:

- Para la próxima semana (17 de diciembre) cada grupo tendrá que esbozar el proyecto para discutirlo con los profesores. Si es posible, se recomienda mandar por correo un pequeño resumen del mismo el día 16.
- En todo caso, el 14 de enero se deberá haber cerrado la temática del proyecto con los profesores. En el caso de que para esa fecha el proyecto no se haya cerrado, el proyecto estará suspenso.
- El día 23 de enero se realizará una presentación preliminar del estado del proyecto. Consistirá en una presentación pública de 3 minutos explicando el tema elegido, los pasos que se han dado, conclusiones preliminares y trabajo por hacer.
- El día 1 de febrero a las 23.55h se deberá realizar la entrega de toda la documentación del proyecto a través del Campus Virtual.
- El día 2 de febrero a las 17h (día del examen de SOC) se realizará la presentación final pública del proyecto. En este caso se dispondrá de 7 minutos para explicar nuevamente el tema elegido, las tareas realizadas y las conclusiones finales e interpretación de los resultados obtenidos.


## Entrega del proyecto

La práctica se entregará en el Campus Virtual, antes de las 23:55 del día 1 de
febrero de 2015. La entrega de la práctica será un archivo .zip (etiquetado con el número de grupo GrupoXX) con los siguientes contenidos:

* Documentación.pdf : Un archivo pdf que deberá incluir, al menos, el
siguiente contenido:

    - Portada con el número y título de la práctica.
    - Número de grupo.
    - Nombre y apellidos de los integrantes del grupo.
    - Memoria del trabajo
    - Referencias bibliográficas u otro tipo de material distinto del proporcionado en la asignatura que se haya consultado para realizar la
    práctica.
* Código fuente de todas las herramientas desarrolladas durante la realización del trabajo, así como sus versiones ejecutables e instrucciones de uso.
* Todos los archivos adicionales que el grupo considere relevantes (por ejemplo, archivos de Gephi, hojas excel con los datos utilizados durante el análisis y comparación, etc.).

El archivo puede ser subido por cualquiera de los integrantes del grupo (sólo una entrega).