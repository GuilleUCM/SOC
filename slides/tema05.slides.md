% Análisis de Redes Sociales
% Guillermo Jiménez Díaz (gjimenez@ucm.es); Alberto Díaz (albertodiaz@fdi.ucm.es)
% Curso 2016-17

# Tema 2: Modelos de redes: <br/>El modelo de red aleatoria

## Modelos

### Modelos

> Los datos relativos a una red nos permiten calcular todas las propiedades vistas hasta ahora.
> 
> Sin embargo, muchas de **las redes reales son demasiado complejas** como para tener todos los datos. En este caso es necesario aproximarlas mediante un modelo que las simplifique.

### Modelos

* Un **modelo** es una _representación simple_ de un sistema complejo del que podemos _extraer y derivar propiedades_ matemáticamente.
* Los modelos nos ayudan a entender cómo y por qué se han formado las redes tal y como son ahora.
* Mediante un modelo que se aproxime a una red real podremos _predecir propiedades y resultados_ de la misma. 

> En este y en sucesivos capítulos estudiaremos algunos de los modelos más conocidos de redes sociales.
> 
> El primero de ellos es el **modelo de red aleatoria**.

## Modelo de red aleatoria

### Ejemplo motivante

![Primer día de clase en la Universidad. Charlas en grupos con encuentros aleatorios](../images/tema02/ejemplo.png)

### Encuentros aleatorios

> **Premisa:** Los enlaces entre los nodos de una red se generan de manera aleatoria

### Modelo de red aleatoria

* Una __red aleatoria__ es una red en la que cada uno de los enlaces entre dos nodos se ha creado siguiendo un proceso completamente aleatorio.
* Matemáticamente es una red que tiene __$N$ nodos__ donde cada nodo puede estar conectado con otro con una __probabilidad $p$__. Se representa como __$G(N,p)$__

### Modelo de red aleatoria

* Modelo de Erdös-Renyi (1960)

![Pal Erdös y Alfred Renyi, matemáticos hungaros principales investigadores del modelo de red aleatoria.](../images/tema02/erdosRenyi.png)


### Construcción

> 1. Crear N nodos aislados
> 2. Seleccionar un par de nodos y generar un número aleatorio entre 0 y 1. Si es menor o igual que $p$ entonces añadimos un enlace entre ellos. En otro caso, los dejamos desconectados.
> 3. Repetir el paso 2 para los $\frac{N(N-1)}{2}$ pares de nodos de la red.

### Alternativa

* El modelo de red aleatoria también puede caracterizarse como __$G(N, L)$__, donde $L$ es el número de enlaces de la red.
* La red se forma seleccionando aleatoriamente 2 nodos y, si no existe un enlace entre ellos, se añade.
* Este proceso se repite hasta conseguir un total de $L$ enlaces.
* Forma menos usada.

## Número de enlaces

### Igual parámetros, distintas redes

![](../images/tema02/distintasRedes.png)

* Si la red se representa como $G(L,p)$ entonces ya sabemos el número exacto de enlaces.

### Número variable de enlaces

* Las redes aleatorias $G(N, p)$ tienen un número variable de enlaces ($L$). 
* Podemos calcular la probabilidad de que la red tenga exactamente $L$ enlaces.

* __Distribución binomial__: el número de éxitos ($x$) que se pueden conseguir en la realización de $n$ experimentos independientes donde la probabilidad de acierto es $p$ y la de fracaso, $1-p$.

$$ B(n, x, p) \to p_x = \binom{n}{x}p^x(1-p)^{n-x}$$ 

### Distribución binomial

![](../images/tema05/Binomial.png)

### Propiedades de la distribución binomial

$$ B(n, x, p) \to p_x = \binom{n}{x}p^x(1-p)^{n-x}$$ 

* Media de la distribución: $\langle x \rangle = \sum_{x=1}^{N}x \cdot p_x = n \cdot p$
* Varianza de la distribución: $\sigma _x ^2= p \cdot (1-p) \cdot n$
* Desviación estándar de la distribución: $\sigma _x = [p \cdot (1-p) \cdot n]^{\frac{1}{2}}$

### Probabilidad de L

* La probabilidad de una red $G(N, p)$ de tener exactamente $L$ enlaces es:

$$ p_L = B(L_{max}, L, p) \to p_L = \binom{L_{max}}{L} p^L(1-p)^{L_{max}-L} $$


* Número medio de enlaces esperados en $G(N,p)$ como:

$$ \langle L \rangle = p \cdot L_{max} = p \cdot \binom{N}{2} = p \cdot \frac{N(N-1)}{2}$$




## Grado medio y<br/>Distribución del grado de los nodos

### Grado medio 

Si la red se representa como $G(L,p)$

$$\langle k \rangle = \frac{2L}{N}$$

En otro caso:

$$ \langle k \rangle = \frac{2 \langle L \rangle }{N}  = p \cdot (N-1)$$ 

> __Conclusión__: cuanto mayor sea $p$, mayor es el grado medio y, por tanto, más densa se vuelve la red.

### Distribución del grado de los nodos

Podemos representarla como una binomial.

$$ p_k = B(N-1, k, p) \to p_k = \binom{N-1}{k} p^k(1-p)^{N-1-k}$$

* El **grado medio**: $\langle k \rangle = (N-1) \cdot p$
* La **varianza** de $k$ será: $\sigma _k ^2 = p \cdot (1-p) \cdot (N-1)$
* La **desviación estándar** de $k$ será: $\sigma _k = [p \cdot (1-p) \cdot (N-1)]^{\frac{1}{2}}$

### Aproximación para redes reales


* La mayoría de las redes reales son __dispersas: $\langle k \rangle \ll N$__

* La distribución de grados de los nodos se aproxima mejor usando una _distribución de Poisson_:

$$ P(x, \lambda) \to p_x = e^{-\lambda} \cdot \frac{\lambda ^x}{x!}$$

### Propiedades de la distribución de Poisson

$$ P(x, \lambda) \to p_x = e^{-\lambda} \cdot \frac{\lambda ^x}{x!}$$

* Media de la distribución: $\langle x \rangle = \lambda$
* Varianza de la distribución: $\sigma _x ^2= \lambda$
* Desviación estándar: $\sigma _x = \lambda ^{\frac{1}{2}}$

### Comparativa entre la distribución binomial y la Poisson

![Representación gráfica de la distribución binomial y de la distribución de Poisson](../images/tema02/binomPoisson.png)

### Comparativa entre la distribución binomial y la Poisson

![Comparativa de distribuciones de grados (izq: Binomial; der: Poisson)](../images/tema02/binomPoisson2.png)

### Comparativa entre la distribución binomial y la Poisson

Propiedades comunes:

* Tienen un pico en $\langle x \rangle$ de modo que si modificamos $p$ entonces el pico se desplaza hacia la derecha.
* Cuanto más densa es la distribución entonces más ancha es la distribución.

Ventaja de la Poisson frente a la binomial

* Las principales propiedades tienen una forma más simple
* La Poisson no depende de $N$

### Distribución de grados cuando $N\gg k$

Aproximamos mediante una Poisson:

$$p_k = P(k, \langle k \rangle) \to p_k = e^{-\langle k \rangle}\cdot \frac{\langle k \rangle ^k}{k!}$$

* Varianza de $k$: $\sigma _k ^2= \langle k \rangle$
* Desviación estándar de $k$: $\sigma _k = \langle k \rangle ^{\frac{1}{2}}$



### Propiedades derivables de la distribución de grados

> __Conclusión: La distribución de grados<br/>no depende de $N$__ 
> 
> Dos redes con igual $\langle k \rangle$ y distinto tamaño $N$ tienen funciones de distribución de grado indistinguibles.

### Propiedades derivables de la distribución de grados

> __Conclusión: La mayoría de los nodos tienen un grado entorno a la media ($\langle k \rangle$)__ 
> 
> Los nodos de mayor grado tienen solo unos pocos más que la media

### Propiedades derivables de la distribución de grados

> __Conclusión: Las redes aleatorias no tienen **concentradores o hubs**__
> 
>  Nodos con conectividad o grado muy alto: la probabilidad de tener nodos con grado muy alto es extremadamente baja

### Ejemplo

* $\langle k \rangle = 1000$ 
* $\sigma _k = 31,62$
* Los nodos tienen entre 970 y 1030 enlaces.
* $k_{max}=1185$ y $k_{min}=816$.


## Evolución de una red aleatoria

### Evolución

* La creación de una red aleatoria parte de un conjunto de nodos aislados que se van uniendo aleatoriamente. 
* Una simulación del algoritmo de creación permite ver:

    * cómo varía el grado medio de la red
    * cómo aparece un componente gigante cuyo tamaño va variando a medida que se modifica dicho grado medio.

<http://barabasi.com/networksciencebook/resources/chapter3.html>

### Evolución

![Evolución del tamaño del componente gigante ($\frac{N_G}{N}$) con respecto al grado medio de la red $\langle k \rangle$](../images/tema02/evolucion.png)

### Evolución

* Partimos de nodos aislados
* A partir de $\langle k \rangle = 1$ el valor de $\frac{N_G}{N}$ comienza a crecer rápidamente
* Comienza la aparición de un componente gigante.
* A partir de otro punto desaparecen los nodos aislados

### Evolución

Con respecto a la probabilidad $p$:

* Si $p=0$ entonces $\langle k \rangle = 0$, $N_G = 1$ y $\frac{N_G}{N} \sim 0$.
* Si $p=1$ entonces $\langle k \rangle = N-1$, $N_G = N$ y $\frac{N_G}{N} = 1$.
* La aparición del componente gigante aparece cuando $\langle k \rangle=1$
* Cuantos más nodos $N$ tenga la red, menor $p$ es necesario para crear un componente gigante.

### Etapas

* Etapa o regimen subcrítico
* Regimen o punto crítico
* Etapa o regimen supercrítico
* Etapa o regimen conectado

### Etapa subcrítica

* $0 < \langle k \rangle < 1 \to p < \frac{1}{N}$
* Durante esta etapa se crean pares de enlaces
* Según incrementa el grado medio se crean pequeños grupos (no componentes gigantes ya que $\frac{N_G}{N} \sim 0$)
* El tamaño del grupo más grande es $N_G \sim ln N$.

### Punto crítico

* $\langle k \rangle = 1 \to p= \frac{1}{N}$.
* Hay un gran número de componentes de pequeño tamaño
* Aparece un componente gigante
* El tamaño del componente más grande es $N_G \sim N^{\frac{2}{3}}$.

### Etapa supercrítica

* $\langle k \rangle > 1 \to p > \frac{1}{N}$.
* El componente gigante crece según nos alejamos del punto crítico.
* $\frac{N_G}{N} \sim \langle k \rangle -1 \to N_G \sim (p-p_c)\cdot N$, donde $p_c = \frac{1}{N}$.
* Siguen existiendo componentes aislados que conviven con el componente gigante.

### Etapa conectada

* $\langle k \rangle \ge ln N \to p \ge \frac{ln N}{N}$.
* Cuando $p$ es lo suficientemente grande el componente gigante absorbe todos los nodos y componentes de la red
* $N_G \sim N$. En este momento toda la red es conexa.
* La red sigue siendo relativamente dispersa

### Resultados

> __Conclusión:__ Si $\langle k \rangle > 1$ entonces la red puede comenzar a considerarse como tal (existe un componente gigante)

> __Conclusión:__ Si $\langle k \rangle \sim ln N$ entonces todos los componentes son absorbidos, creando una red global conectada.

## Distancia en redes aleatorias

### Distancia media en una red aleatoria

En una red aleatoria de grado $\langle k \rangle$ se cumple que cualquier nodo de la red tiene, _en media_:

* $\langle k \rangle$ nodos a distancia 1 ($d=1$)
* $\langle k \rangle^2$ nodos a distancia 2 ($d=2$)
* ...
* $\langle k \rangle^d$ nodos a distancia d 


$$N(d) =1+\langle k \rangle+\langle k \rangle^2+\dots=\frac{\langle k \rangle^{d+1}-1}{\langle k \rangle-1}$$

### Distancia media en una red aleatoria

Si suponemos que $\langle k \rangle \gg 1$:

$$d_{max} \propto \frac{log N}{log \langle k \rangle}$$

Se puede considerar que la misma fórmula aproxima $\langle d \rangle$

$$\langle d \rangle \propto \frac{log N}{log \langle k \rangle}$$

### Distancia media en una red aleatoria

> __Conclusión__: La longitud media de los caminos de la red va a ser varios órdenes de magnitud más pequeño que $N$.

> __Conclusión__: Cuanto más densa sea la red, menor es la distancia entre los nodos.

### Pequeños mundos

> __Small worlds__: la distancia entre dos nodos cualquiera de la red es sorprendentemente corta.

## Coeficiente de agrupamiento

### Coeficiente de agrupamiento

* Para calcular $C_i$ necesitamos estimar cuál es el número de enlaces entre los vecinos de un nodo.
* La probabilidad de que haya un enlace entre dos nodos en una red aleatoria es $p$ 
* Un nodo $i$ puede tener $\frac{k_i(k_i-1)}{2}$ posibles enlaces entre sus $k_i$ vecinos.

$$ \langle L_i \rangle = p \cdot \frac{k_i(k_i-1)}{2}$$

$$
C_i = \langle C \rangle = \frac{2 \cdot \langle L_i \rangle }{k_i(k_i-1)} = p = \frac{\langle k \rangle}{N}
$$

### Coeficiente agrupamiento

> __Conclusión__: Para un $\langle k \rangle$ fijo, el coeficiente de agrupamiento decrece cuanto mayor es el tamaño de la red ($N$).
> 
> Este coeficiente decrecerá a razón de $\frac{1}{N}$. 

> __Conclusión__: El coeficiente de agrupamiento de un nodo es independiente de su grado.


## Redes reales frente a redes aleatorias

### Redes reales frente a redes aleatorias

Si suponemos que las redes reales siguen el modelo de red aleatoria entonces se cumplirán las propiedades vistas anteriormente. 

![Datos sobre algunas redes reales](../images/tema02/datosRedes.png)

### Etapas de evolución

* Todas estas redes cumplen que $\langle k \rangle > 1$ por lo que tienen un componente gigante.
* No se cumple que $\langle k \rangle \sim ln N$

    * Deberíamos suponer que se encuentran en la fase supercrítica
    * Existen nodos y componentes aislados.

> Si las redes reales se modelan de acuerdo al modelo de Erdös-Renyi entonces deberían existir nodos desconectados del componente gigante.

### Etapas de evolución

> **Internet**
> 
> Existen subredes que no están conectados a la red global.
> 
> Si esto fuese así, ¿cómo los alcanzaríamos?. 

> Estamos ante la evidencia de que tal vez este modelo no es del todo válido para algunas redes reales.



### Mundos pequeños en redes reales

* Ejemplo: Facebook
    
    Datos de mayo de 2011: $721\cdot 10^6$ usuarios y $68\cdot 10^9$ relaciones (simétricas) de amistad

$$
\langle d \rangle = \frac{log N}{log \langle k \rangle} \simeq 3.90
$$

### Mundos pequeños en redes reales

![Distancia media y diámetro de algunas redes reales](../images/tema02/dmRedesReales.png) 

### Mundos pequeños en redes reales

> En general, se cumplen la ley de los mundos pequeños



### Coeficiente agrupamiento en redes reales

![Cálculos del coeficiente de agrupamiento para redes reales](../images/tema02/ci_reales.png)

### Coeficiente agrupamiento en redes reales

* $C_i$ no decrece a razón de $\frac{1}{N}$ (línea punteada)
* $C_i$ _sí_ depende del grado de los nodos.

> De nuevo nos encontramos que las redes reales incumplen propiedades de las redes aleatorias

## Resumen

### Resumen
* Una __red aleatoria__ es una red en la que cada uno de los enlaces entre dos nodos se ha creado siguiendo un proceso completamente aleatorio.

![Cuadro resumen (extraído de _Network Science_, pp. 70)](../images/tema02/resumen.png)

### Resumen

* Las redes reales **incumplen** algunas de las propiedades de las redes aleatorias.

* **Distribución de grados** <span style="color: #e74c3c;">(Incumplida)</span>

> La distribución de grados se puede aproximar a una función de Poisson pero esta distribución no explica la existencia del gran número de nodos altamente conectados que aparecen en las redes reales.

### Resumen

* **Conectividad** <span style="color: #e74c3c;">(Incumplida)</span>
    
> El modelo de redes aleatorias predice que si $1 < \langle k \rangle < ln N$ entonces la red presenta grupos aislados.

> Redes como Internet no cumplen que $\langle k \rangle > ln N$ y, sin embargo, no están fragmentadas.
 
### Resumen

* **Coeficiente de agrupamiento** <span style="color: #e74c3c;">(Incumplida)</span>

> Según el modelo de red aleatoria, el coeficiente de agrupamiento es independiente del grado del nodo sobre el que se calcula

> Según el modelo de red aleatoria, el coeficiente de agrupamiento depende del tamaño de la red en relación $\frac{1}{N}$.

> Las redes reales no cumplen ninguna de estas dos propiedades.

### Resumen

* **Propiedad de los pequeños mundo** <span style="color: #2ecc71;">(Cumplida)</span>

> En un sistema complejo hay un camino de longitud _corta_  entre cualquier par de nodos de la red que lo modela.
