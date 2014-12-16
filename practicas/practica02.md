% Análisis de Redes Sociales
% Guillermo Jiménez Díaz (gjimenez@ucm.es); Alberto Díaz (albertodiaz@fdi.ucm.es)
% Curso 2014 - 2015

# Prefacio {-}

Estos son las prácticas de la asignatura Análisis de Redes Sociales, impartida en la Facultad de Informática de la Universidad Complutense de Madrid por los profesores Guillermo Jiménez Díaz y Alberto Díaz, del Departamento de Ingeniería del Software e Inteligencia Artificial.

Este material ha sido desarrollado a partir de distintas fuertes, destacando como referencia principal el libro _Network Science_ de Laszlo Barabasi, el material de la asignatura _Social Network Analysis_, impartido por Lada Adamic a través de Coursera, y las transparencias de la asignatura Redes y Sistemas Complejos, creadas por Óscar Cordón García de la Universidad de Granada.

Este obra está bajo una [licencia de Creative Commons Reconocimiento-NoComercial-CompartirIgual 4.0 Internacional](http://creativecommons.org/licenses/by-nc-sa/4.0/).

# Práctica 2: Implementación de modelos de redes

En esta práctica vamos a implementar dos de los modelos que hemos estudiado hasta ahora en la asignatura: el modelo de Erdos-Renyi, para la generación de redes aleatoria, y el modelo de Barabasi-Albert, para la generación de redes libres de escala. La práctica consistirá en implementar estos dos modelos en la tecnología elegida por el grupo de prácticas y hacer una pequeño análisis de las principales propiedades de las redes generadas con estos modelos en Gephi.

## Parte A: Desarrollo de un modelo de red aleatoria

Desarrollar una pequeña aplicación que genere una red aleatoria dados los valores $N$(>0) --el número de nodos inicial-- y $p$ ($0 \leq p \leq 1$) --la probabilidad de enlaces dentro de la red. No es necesaria ninguna simulación como las que se han visto en clase sino que lo que queremos es que la aplicación genere un un fichero en [uno de los formatos que es capaz de importar Gephi](http://gephi.github.io/users/supported-graph-formats/) (por ejemplo, CSV para nodos y aristas por separado). 

## Parte B: Desarrollo de un modelo de Barabasi-Albert

Desarrollar una pequeña aplicación que genere una red libre de escala siguiendo el modelo de Barabasi-Albert dados los valores $m$(>0) --el número de enlaces con los que entra un nodo nuevo a la red-- y $t$ (>0)) --el número de pasos del modelo. Puedes suponer que $m_0 = m+1$ y que en la configuración inicial todos los nodos están unidos con todos. Recuerda que en estas redes el número de nodos es dependiente del número de pasos dados en el modelo: $N(t) = m_0 + m \cdot t$.

Al igual que antes, no es necesaria ninguna simulación como las que se han visto en clase sino que lo que queremos es que la aplicación genere un un fichero en [uno de los formatos que es capaz de importar Gephi](http://gephi.github.io/users/supported-graph-formats/) (por ejemplo, CSV para nodos y aristas por separado). 

## Parte C: Verificación de las propiedades de las redes generadas

Crear varias redes de igual número de nodos con ambos modelos. Se recomienda que el análisis se haga con tamaños grandes, por ejemplo $N$ = 500, 1000, 5000, 10000, 50000 y 100000 (cuidado con los valores máximos de los enteros al programar los modelos).

Estudia las propiedades de las redes generadas y haz un análisis comparativo en cuanto a la densidad de las redes generadas, la distribución de grados, la distancia media y el coeficiente de agrupamiento. Este análisis se realizará tanto entre las redes de distintos tamaños para un mismo modelo, como entre las redes de igual tamaño creadas con distintos modelos.

Muestra gráficamente con Gephi la mayor red que hayas generado para cada uno de los modelos de modo que el tamaño de los nodos sea dependiente de su grado. 

Por último, compara los resultados reales obtenidos con los predichos por los modelos (recuerda que al final de cada tema tienes un cuadro resumen con las principales propiedades de cada tipo de red y la forma en la que se calculan).

## Consejos para el desarrollo de los modelos

Los modelos pueden estar desarrollados en cualquier tecnología (Java, C++, Python, Javascript...). Se recomienda utilizar las estructuras de datos adecuadas para ir guardando toda la información adicional necesaria e ir actualizándola en cada paso de simulación (sobre todo en el modelo de Barabasi-Albert). Se puede utilizar cualquier tipo de librería auxiliar que ayude en la gestión de las estructuras de datos usadas para la creación del modelo.

Las aplicaciones creadas pueden lanzarse desde la línea de comandos o pueden tener una pequeña interfaz gráfica (de escritorio o web). El resultado final de la ejecución será el fichero (o los ficheros) en un formato que se pueda cargar en Gephi. En caso de error no se deberá crear ningún fichero y se avisará al usuario.

## Entrega

La práctica se entregará en el campus virtual, antes de las 23:55 del día 23 de noviembre de 2014. 

La entrega de la práctica será un archivo `GrupoXX.zip` con los siguientes contenidos:

* Un archivo `fuentes.zip` con el código fuente de las aplicaciones creadas.
* Un archivo `ejecutables.zip` con una versión ejecutable de las aplicaciones creadas (no se aceptará solo el código fuente).
* Un pequeño manual de uso de las aplicaciones creadas (`manual.pdf`).
* Una hoja Excel con los datos analizados para las redes creadas.
* Un archivo `memoria.pdf` donde se incluirá:
    - Portada con el número y título de la práctica.
    - Número de grupo.
    - Nombre y apellidos de los integrantes del grupo.
    - Una breve descripción de los resultados obtenidos en el análisis realizado sobre las redes creadas a partir de los modelos, la comparación con los valores predichos con los modelos y las representaciones gráficas de las redes de mayor tamaño creadas con Gephi.

El archivo puede ser subido por cualquiera de los integrantes del grupo (sólo una entrega).
