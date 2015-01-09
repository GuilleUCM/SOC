% Análisis de Redes Sociales
% Guillermo Jiménez Díaz (gjimenez@ucm.es); Alberto Díaz (albertodiaz@fdi.ucm.es)
% 9 de enero de 2015

# Tema 9: Robustez de las redes {-}

### Robustez

- El fallo de un componente sencillo en un sistema complejo puede provocar un error o un fallo general de todo el sistema
- Muchos sistemas naturales y sociales tienen la capacidad de permanecer inmutables aunque varios de sus componentes fallen
- En la mayoría de estos sistemas, la robustez se consigue gracias a densas interconexiones entre los componentes.

### Robustez

> En este tema veremos el rol de las redes con el fin de asegurar la robustez de un sistema complejo

- Conocer la robustez del sistema
- Conocer sus debilidades en caso de ataques premeditados
- Conocer los comportamientos de fallo en cascada
- Mejoras de la robustez

## Robustez, Errores y Ataques

### Robustez

> La __robustez__ implica entender cómo se va a comportar una red en caso de que eliminemos nodos de la misma

- **Fragmentación de la red**, es decir, cómo se rompe la red en comunidades aisladas a medida que eliminamos nodos.
- **Tolerancia a errores**, es decir, cómo de largas pasan a ser las distancias en la red a medida que eliminamos nodos. 

### Errores y Ataques

> Los __errores__ consisten en la eliminación de nodos de manera aleatoria

> Los __ataques__ consisten en la eliminación de nodos seleccionándolos de una manera deliberada.

Simularemos los ataques eliminando los nodos en orden decreciente de grado

## Teoría de la percolación

### Teoría de la percolación

> La teoría de la percolación describe el comportamiento universal de los clusters y componentes de una red aleatoria

- Suponemos que tenemos una cuadrícula
- En cada intersección podemos poner un nodo
- Dos nodos estarán conectados si están en intersecciones adyacentes
- Construimos una red aleatoria decidiendo si ponemos o no un nodo en cada intersección con probabilidad $p$.

### Teoría de la percolación

![Redes creadas siguiendo la teoría de la percolación. En rojo están los nodos que pertenecen al cluster más grande](../images/tema09/percolacion.png) 

### Teoría de la percolación

> Predice el tamaño medio de los clusters y el tamaño del cluster mayor suponiendo que vamos añadiendo nodos de manera aleatoria

> Existe un valor crítico $p_c$ a partir del cual emerge un componente gigante al que pertenecerán la mayoría de los nodos.

> Importante para entender cuál es la robustez de una red aleatoria

### Teoría de la percolación

![Probabilidad de que un nodo pertenezca a un componente gigante a partir de la teoría de la percolación](../images/tema09/pc-er.png)

## Robustez en redes aleatorias

### Fragmentación

> Podemos estudiar la robustez de una red aleatoria usando, a la inversa, la teoría de la percolación

- Partimos de una cuadrícula en la que en todas las intersecciones hay nodos
- Eliminamos los nodos con una determinada probabilidad $f$

### Fragmentación

![Probabilidad de que un nodo pertenezca al componente gigante a medida que aumentamos la probabilidad $f$ con la que eliminamos nodos de la red](../images/tema09/fc-er.png)

### Fragmentación

Al igual que durante la creación, existe un umbral $f_c$:

- Si $0<f<f_c$ entonces continuamos teniendo un componente gigante en la red.
- Si $f=f_c$ entonces el componente gigante comienza a desvanecerse y la red se empieza a fragmentar.
- Si $f>f_c$ entonces la red queda completamente rota en muchos clusters pequeños.

### Fragmentación

Cálculo aproximado de este umbral crítico $f_c$:

$$f_c = 1- \frac{1}{\frac{\langle k^2 \rangle}{\langle k \rangle}-1}$$

Para una red aleatoria, en la que el segundo momento es conocido:

$$f_c^{ER} = 1- \frac{1}{\langle k \rangle}$$

> **Conclusión**: cuanto más densa sea la red, mayor es el umbral $f_c$.

### Fragmentación

> **Conclusión**: la fragmentación de la red debido a fallos **no es un proceso gradual**

- Inicialmente, la eliminación de una pequeña fracción de nodos no afecta a la integridad de la red
- Existe un punto crítico a partir del cual la red se rompe abruptamente en pequeños grupos de nodos desconectados.

### Tolerancia a errores

> Cómo evoluciona el diámetro de la red a medida que eliminamos nodos de manera aleatoria a medida que aumentamos $f$.

### Tolerancia a errores

![Diámetro de la red a medida que aumentamos el número de nodos que eliminamos de la red. Aquí se muestra solo para una pequeña fracción de nodos eliminados (E=Red aleatoria; SF=Red libre de escala)](../images/tema09/diametro.png)

### Tolerancia a errores

> **Conclusión:** El diámetro de la red crece de manera monótona para valores muy pequeños de $f$
 
- La mayoría de los nodos tienen aproximadamente el mismo grado
- Todos contribuyen aproximadamente de la misma forma al diámetro de la red
- La desaparición de cualquiera de ellos hace que las distancias vayan creciendo. 
- Cuando alcancemos $f_c$ el diámetro divergirá ya que romperemos el componente gigante.

### Comportamiento frente a ataques

- Se decide deliberadamente qué nodos de la red queremos eliminar en cada momento
- Simular un ataque eliminando los nodos en orden decreciente de su grado $k$

### Comportamiento frente a ataques

Desde el punto de vista de la fragmentación 

![](../images/tema09/fragAtaque-er.png)

### Comportamiento frente a ataques

> **Conclusión**: la fragmentación de la red evoluciona de la misma forma ya sea por errores o por ataques

- Esto se debe a que todos los nodos tienen un grado similar
- Un ataque deliberado no es más efectivo que los errores aleatorios en una red aleatoria. 

### Comportamiento frente a ataques

![Diámetro de la red a medida que aumentamos el número de nodos que eliminamos de la red. Aquí se muestra solo para una pequeña fracción de nodos eliminados (E=Red aleatoria; SF=Red libre de escala)](../images/tema09/diametro.png)

### Comportamiento frente a ataques

> **Conclusión**: las distancias en la red evolucionan de la misma forma ya sea por errores o por ataque

- El ataque a los nodos de mayor grado sigue haciendo que la distancia crezca de manera monótona
- No se ve diferencia apreciable con respecto a la tolerancia a errores.

### Comportamiento frente a ataques


> **Conclusión**: las redes aleatorias son resistentes a ataques

> **Conclusión**: Su resistencia es similar para errores aleatorios que para ataques

## Robustez en redes libres de escala 

