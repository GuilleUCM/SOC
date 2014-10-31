% Análisis de Redes Sociales
% Guillermo Jiménez Díaz (gjimenez@ucm.es); Alberto Díaz (albertodiaz@fdi.ucm.es)
% 31 de octubre de 2014



# Tema 5: Centralidad {-}

### Concepto de centralidad

Los nodos con una "posición más central" (una mayor centralidad) tienen un acceso más fácil y rápido a los demás nodos de la red y una mayor capacidad para ejercer un control del flujo entre ellos.

### Ejemplos de grafos de actores en películas

En los siguientes grafos se representan relaciones entre los actores que aparecen en distintas películas analizando los guiones. Se incluye una arista entre dos actores si un actor interacciona con otro actor en un punto concreto de la película.

### Ejemplos de grafos de actores en películas

<!-- PONER FIGURAS -->
[Wikipedia: El Fugitivo (1993). Actores principales: Dr. Kimble, Gerard](http://es.wikipedia.org/wiki/El_fugitivo_(pel%C3%ADcula_de_1993))

![The Fugitive (1993)](../images/tema05/elFugitivo.png)

### Ejemplos de grafos de actores en películas

[Wikipedia: Memento (2000). Actor principal: Leonard](http://es.wikipedia.org/wiki/Memento)

![Memento (2000)](../images/tema05/Memento.png)

### Ejemplos de grafos de actores en películas

Han sido extraídas de la web [moviegalaxies.com](http://moviegalaxies.com)

## Medidas

### Medidas

Para analizar la estructura de las redes sociales existen 2 tipos de medidas: Medidas locales (a nivel de nodos) y medidas globales (a nivel de red).

### Medidas locales (a nivel de nodos).

* Todas estas medidas están basadas en el concepto general de centralidad (redes no dirigidas) o prestigio (redes dirigidas).
* La centralidad es una medida general de la posición de un nodo en la estructura global de la red social.
* Estas medidas se usan para identificar los nodos claves de una red.
* Muestran como las relaciones se concentran en unos pocos nodos (individuos), dando una idea de su poder social.

<!-- DUDA: Ejemplos Nada? -->

### Medidas globales (a nivel de red)

* Proporcionan información más compacta que permite evaluar la estructura global de la red.
* Proporcionan información sobre propiedades importantes de los fenónemos sociales subyacentes.
* Algunas de estas medidas las hemos utilizado en temas anteriores: diámetro, distancia media, grado medio, densidad.

## Medidas locales de centralidad

### Medidas locales de centralidad

Existen varias medidas distintas de centralidad:

* Grado
* Intermediación (betweenness)
* Cercanía (closeness)
* Excentricidad
* Centralidad de vector propio
* Coeficiente local de clustering

## Centralidad de grado

### Centralidad de grado

Mide el número de enlaces con otros nodos.
Hay que distinguir entre grafos dirigidos y no dirigidos.

### Grafos no dirigidos.

Centralidad de grado de un nodo: número de enlaces que lo conectan con otros.

$$C_D(N) = k_N$$

$C_D(N)$ se define en el intervalo {0, g-1}, siendo g el número de nodos de la componenente conexa donde está el nodo N.

<!-- PINTAR GRAFO CON EJEMPLO -->

### Grafos no dirigidos.

Interpretación:

* Los nodos con más enlaces son más centrales.
* En una red social de personas con relaciones de amistad, los individuos con más amigos son más centrales.
* Sin embargo, sólo mide la importancia con respecto a los vecinos más cercanos.
* Se asume que las conexiones de los vecinos no importan, sólo importa lo que se pueda hacer directamente con los vecinos. 

### Grafos dirigidos.

En grafos dirigidos, se define el prestigio de entrada (in-degree), denominado Soporte, y el prestigio de salida (out-degree), denominado Influencia:

$$Soporte = P_D^{in} = k_N^{in}$$

$$Influencia = P_D^{out} = k_N^{out}$$

Ambos se definen en el intervalo {0, g-1} 

<!-- PINTAR GRAFO CON EJEMPLO -->

### Grafos dirigidos.

Interpretación Soporte:

* Los nodos con muchos enlaces de entrada son prominentes.
* La idea básica es que muchos nodos procuran tener enlaces directos a ellos, por lo que se puede considerar como una medida de su importancia.

Interpretación Influencia:

* Los nodos que tienen muchas conexiones directas de salida con otros son influyentes.
* Pueden transferir información rápidamente a muchos otros nodos.

### Grafos dirigidos.

![Ejemplo de Soporte e Influencia. Comercio de petróleo y derivados, 1998. Fuente: NBER-United Nations Trade Data. Cada nodo es un país y hay un enlace entre el exportador y el importador. El grosor de la arista indica el volumen exportado.](../images/tema05/ImagenSoporte.png)

Preguntas sobre Figura 3:

Pregunta sobre Soporte: ¿Qué países importan de muchos otros?: ¿Arabía Saudí, Japón, Iraq, USA, Venezuela?
<!-- Respuesta: Japan y USA -->

Pregunta sobre Influencia: ¿Qué país exporta a pocos países pero lo hace en gran cantidad?: ¿Arabía Saudí, Japón, Iraq, USA, Venezuela?
<!-- Respuesta: Venezuela -->


### Normalización del grado

Es habitual normalizar los valores de las centralidades de grado ($C_D(N)$, $P_D^{in}$, $P_D^{out}$) diviéndolas por su valor máximo g-1 (siendo g el número de nodos de la componente conexa donde está el nodo).

<!-- PINTAR EJEMPLOS UGR O LADA -->

<!-- ¿FREEMAN FORMULA FOR CENTRALIZATION DE LADA? NO -->

### Problemas del grado como medida de centralidad

El grado es una medida adecuada para evaluar la centralidad de un nodo en una red social pero desde una perspectiva muy local:

* mide la importancia y la influencia del nodo con respecto a sus vecinos más cercanos,
* pero tiene una limitación importante: no tiene en cuenta la estructura global de la red.

<!-- EXPLICAR SOBRE EJEMPLOS ANTERIORES -->

<!-- ¿DISCUSIÓN SOBRE INTERMEDIACIÓN DE LADA? NO -->


## Intermediación

### Intermediación

La intermediación es una medida pensada para capturar como de central es un nodo desde el punto de vista de cuantos caminos mínimos que conectan nodos lo atraviesan

$$C_B(i) = \sum_{j<k}\frac{g_{jk}(i)}{g_{jk}}$$

donde $g_{jk}$ es el número de caminos mínimos que conectan los nodos j y k (normalmente 1), y $g_{jk}(i)$ es el número de esos caminos que incluyen al nodo i en medio del camino.

$C_B(i)$ se define en el intervalo {0, (g-1)(g-2)} en redes dirigidas y en {0, (g-1)(g-2)/2} en no dirigidas.

### Intermediación

Interpretación:

* Un nodo tiene una posición más favorable (mayor intermediación) en la medida en que dicho nodo esté situado en los caminos geodésicos (caminos más cortos) de todos los demás.
* En otras palabras, cuanto más caminos geodésicos pasen por un nodo más central será.
* En la perspectiva de las redes sociales, las interacciones entre dos actores no adyacentes puede depender de otros actores del conjunto, especialmente de aquellos situados en los caminos entre ambos.
* Los nodos con una intermediación alta ocupan roles críticos en la estructura de una red, puesto que suelen ocupar una posición que les permite trabajar como interfaces entre subgrupos de nodos fuertemente unidos.
* Son elementos vitales en la conexión entre distintas regiones de una red.

### Intermediación

Es habitual considerar la medida normalizada:

$$C_B^{'}(i) = \frac{C_B(i)}{(g-1)(g-2)/2}$$

donde el denominador representa el número de pares de nodos excluyendo el propio nodo i.


<!-- PINTAR EJEMPLOS NADA. -->


<!-- ![Grado vs. Intermediación](../images/tema05/imagenGradovsIntermediacion.jpg)

Grado. $C_D$. Max = 17.
Nodo 1. $C_D = 6$.
Nodo 2. $C_D = 6$.

Intermediación. $C_B$. Max = 17*16/2 = 136.
Nodo 1. $C_B = 70.0$.
Nodo 2. $C_B = 96.5$. -->


<!-- ![Ejercicio](../images/tema05/Imagen3.jpg)

* Encontrar un nodo con un valor alto de intermediación pero con un grado bajo

* Encontrar un nodo con un valor bajo de intermediación pero con un grado alto -->


## Cercanía

### Cercanía

Esta medida da importancia a la facilidad de acceso al resto de la red, a que se pueda llegar al resto de los nodos de la red con pocos saltos, o dicho de otra forma que la distancia al resto de los nodos de la red sea pequeña.

En esta medida no se tiene en cuenta ni tener muchos vecinos directos ni estar situado entre otros nodos. Se le da importancia a estar "en medio" de la red.

La suma de las distancias geodésicas (distancias de los caminos mínimos) de un nodo de la red a todos los demás es la lejanía de un nodo al resto.
La inversa de dicha suma es la medida de cercanía.

### Cercanía

Centralidad de cercanía:

$$C_C(i) = 1 / \sum_{j=1}^{g}d(i,j)$$

Centralidad de cercanía normalizada:

$$C_C^{'}(i) = 1 / (\frac{\sum_{j=1}^{g}d(i,j)}{g-1})$$

<!-- Si hay varias componentes conexas puede haber distancias infinitas, se puede calcular la centralidad de cercanía como la suma de las inversas de las distancias. -->

<!-- PINTAR EJEMPLOS NADA -->

<!-- ![Ejercicio](../images/tema05/Imagen4.jpg)

* Encontrar un nodo con grado relativamente alto pero con un valor de cercanía bajo -->

### Cercanía en redes dirigidas

Se pueden definir dos medidas de cercanía distintas considerando sólo los enlaces de entrada o de salida:

* Cercanía de entrada (p.ej.: prestigio en redes de citación)

* Cercanía de salida (alcance de la influencia de un nodo)

## Excentricidad

### Excentricidad

Otra medida local basada en distancias es la centralidad de excentricidad $C_E(i)$. Se define como la inversa de la excentricidad (la máxima distancia geodésica) entre un nodo y el resto de nodos de la red.

Los nodos con mayor valor de excentricidad se denominan nodos periféricos, los de menor valor forman el centro de la red.

### Excentricidad

Centralidad de excentricidad:

$$C_E(i) = 1 / \max_{jinV(G)/i}d(i,j)$$

Centralidad de cercanía normalizada:

$$C_E^{'}(i) = C_E(i) / g-1$$


