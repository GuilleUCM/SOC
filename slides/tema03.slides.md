% Análisis de Redes Sociales
% Guillermo Jiménez Díaz (gjimenez@ucm.es); Alberto Díaz (albertodiaz@fdi.ucm.es)
% 17 de octubre de 2014

# Tema 3: Redes libres de escala

## WWW

### Mapa de la WWW

* Primer mapa de una porción de la WWW (1999)
* **Objetivo**: Verificar las propiedades de los modelos de red aleatoria en este sistema complejo de páginas y enlaces
* Suponían que esta red seguía el modelo de red aleatoria
* Mapa del dominio `nd.edu`

    - 300000 documentos
    - 1,5 millones de enlaces.

### Mapa de la WWW

![Mapa de la WWW: se puede ver la existencia de hubs.](../images/tema03/www.png)

### Mapa de la WWW

* A primera vista cumple la aleatoriedad predicha por el modelo
* Si nos detenemos a observar hay un gran número de nodos de grado pequeño...
* ... y existen nodos con un número excepcional de enlaces: los hubs o concentradores.
* Estos nodos son extremadamente improbables en las redes aleatorias
 
> **Conclusión:** ¿sirve una red aleatoria para modelar la WWW?

### Análisis de datos de la WWW

* Distribución de grados

![Distribución de grados de entrada y de salida de la WWW frente a la Poisson (en escala logarítmica)](../images/tema03/distkinkot.png)

### Análisis de datos de la WWW

* La distribución de grados no se asemeja a la Poisson
* La distribución de grados se asemeja a una **ley potencial** o _power law_. 

    * Se caracteriza por tener una cola mucho más ancha que una exponencial. 
    * La diferencia mucho más clara si las representamos en una escala logarítmica.

### Ley potencial

![Comparativa de una función exponencial (negro) frente a funciones de ley potencial (azul y rojo). A la izquierda se presenta en escala lineal mientras que a la derecha se ve en escala logarítmica](../images/tema03/powerlawExp2.png)

### Ley potencial

Distribución de grados en la WWW

$$p_k \sim k^{-\gamma}$$

$$log\: p_k \sim -\gamma \cdot log\: k$$


Como la WWW es una red dirigida:

$$p_{k_{in}} \sim k^{-\gamma_{in}}$$

$$p_{k_{out}} \sim k^{-\gamma_{out}}$$

### Conclusiones del estudio de la WWW

* Se pudo estimar que $\gamma_{in} \approx 2,1$ mientras que $\gamma_{in} \approx 2,45$.
* Lo realmente interesante fue la gran diferencia entre la distribución esperada (una Poisson) y la distribución final obtenida (una ley potencial). 

> La WWW no se comportaba de acuerdo al modelo de red aleatoria sino que era "otro tipo de red"

## Redes libres de escala

### Redes libres de escala

> Una **red libre de escala** es una red cuya distribución de grados sigue una ley potencial.

> Esta distribución se caracteriza por tener una larga cola.

* El primer informe relacionado con una función de ley potencial fue realizado por Pareto (s. XIX)
    
    * El 80% del dinero en Italia estaba en manos de solo un 20% de la población.

### Formalismo discreto

* El grado de un nodo es siempre un entero positivo ($K=0,1,2\dots$).

$$p_k = C \cdot k^{-\gamma}$$

* La constante C se calcula teniendo en cuenta que $\sum_{k=1}^{\infty}{p_k} = 1$

$$C = \frac{1}{\sum_{k=1}^{\infty}{k^{-\gamma}}} = \frac{1}{\varsigma(\gamma)}$$

donde $\varsigma(\gamma)$ es la función Zeta de Riemann.

### Formalismo discreto

* Para valores de $k>0$, la función de distribución es:

$$p_k = \frac{k^{-\gamma}}{\varsigma(\gamma)}$$

* Los nodos aislado ($k=0$) tienen que tratarse de manera independiente.

### Formalismo continuo

* Consideramos que $k$ puede tomar cualquier valor real positivo.

$$p(k) = C \cdot k^{-\gamma}$$

* La constante C se calcula teniendo en cuenta que $\int_{k_{min}}^{\infty}{p(k)dk} = 1$:

$$C = \frac{1}{\int_{k_{min}}^{\infty}{k^{-\gamma}dk}} = (\gamma -1)\cdot k_{min}^{\gamma -1}$$

*La función de distribución según el formalismo continuo es:

$$p(k)= (\gamma -1)\cdot k_{min}^{\gamma -1}\cdot k^{\gamma -1}$$

Donde $k_{min}$ es el menor grado de la red (o función de distribución)

### Formalismo contínuo

La función de distribución se ha de interpretar como la probabilidad de que un nodo tenga un grado entre dos valores $k_1$ y $k_2$:

$$\int_{k_1}^{k_2}{p(k)dk}$$


## Hubs en las redes libres de escala

### Distribuciones de grados en redes aleatorias frente a libres de escala

![Distribuciones para redes aleatorias y redes libres de escala ((a) en escala lineal; (b) en escala logarítmica y representación gráfica de una (c)red aleatoria frente a una (d)red libre de escala ($\langle k \rangle=3 \text{; }N=50$)](../images/tema03/aleatoriavslibre.png)

### Distribuciones de grados en redes aleatorias frente a libres de escala

* La red libre de escala presenta una probabilidad de nodos con $k$ pequeño mayor que en una red aleatoria
* La red aleatoria tiene una mayor probabilidad de tener nodos con un grado $k \sim \langle k \rangle$ que la red libre de escala
* La red libre de escala presenta una mayor probabilidad de que existan nodos con $k$ muy alto.
* La probabilidad de que existan hubs en una red libre de escala es varios órdenes  de magnitud mayor que en una red aleatoria 

### Distribuciones de grados en redes aleatorias frente a libres de escala

> Ejemplo: Datos de la WWW ($\langle k \rangle = 4,6$)

* **Red aleatoria**: $p_{aleatoria}(100)=10^{-30}$.
* **Red libre de escala**: $p_{libre-escala}(100)=10^{-4}$.

### Grado del mayor hub

* $k_{max}$: grado del mayor hub existente en la red

* Red aleatoria con una distribución de grados $p_k$ exponencial:

$$p_k = C \cdot e^{-\lambda k}: \;\; k_{max}= k_{min} + \frac{lnN}{\lambda}$$

> $k_{max}$ depende de $lnN$
> 
> Muy poca diferencia entre $k_{min}$ y $k_{max}$
> 
> No hay hubs.

### Grado del mayor hub

* Red aleatoria con una distribución de grados $p_k$ Poisson

> $k_{max}$ depende más suavemente de $lnN$
> 
> Aún menor diferencia entre $k_{min}$ y $k_{max}$
> 
> No hay hubs.

### Grado del mayor hub

* Red libre de escala con una distribución de grados $p_k$ de ley potencial

$$p(k) = C \cdot k^{-\gamma}:\;\; k_{max}\sim k_{min} \cdot N^{\frac{1}{\gamma -1}}$$

> $k_{max}$ depende de $N$
> 
> Puede haber (y se espera que haya) hubs.
> 
> **Conclusión**: Cuanto mayor es la red, mayor es el grado del hub más grande.

### Grado del mayor hub

![Relación entre el grado del mayor hub ($k_{max}$) y el tamaño de la red ($N$)](../images/tema03/kmax-n.png)

### Grado del mayor hub

> Ejemplo: Datos de la WWW ($N=3\cdot10^5$)

* **Red aleatoria**: $$k_{max}\approx 13$$

* **Red libre de escala**: $$k_{max}\approx 85000$$

### Resumen gráfico

![Red de carreteras de EEUU (una red aleatoria) frente a la red de tráfico aéreo del mismo país (red libre de escala)](../images/tema03/transporte.png)

## ¿Qué significa "libre de escala"?

### Momentos de la distribución de grados

$$\langle k^n \rangle = \sum_{k_{min}}^{\infty}{k^np_k}=\int_{k_{min}}^{\infty}{k^np(k)dk}$$

* n=1: Grado medio ($\langle k \rangle$).

* n=2: Varianza ($\sigma^2 = \langle k^2 \rangle - \langle k \rangle^2$)

    Mide la dispersión de los grados. Su raíz cuadrada es la desviación típica ($\sigma$)

* n=3: Asimetría ($\langle k^3 \rangle$)

    Cómo de simétrica es p_k alrededor de la  media (si la función es simétrica entonces $\langle k^3 \rangle=0$)

### Momento de la distribución de grados

* Momento n-ésimo en una red libre de escala

$$\langle k^n \rangle = \int_{k_{min}}^{k_{max}}{k^np(k)dk} = C \frac{k_{max}^{n-\gamma+1} - k_{min}^{n-\gamma+1}}{n-\gamma + 1}$$

* Como $k_{max}$ crece con el tamaño de la red  analizamos $k_{max} \to \infty$:

$$\langle k^n \rangle = \frac{(\gamma -1)}{(n-\gamma- 1)} k_{min}^{\gamma-1} \Big[ k^{n-\gamma+1}\Big]_{k_{min}}^\infty$$

### Momento de la distribución de grados

* $n-\gamma+1 \leq 0$

    * El momento está acotado
    * Todos los momentos en los que $n \leq \gamma+1$ son finitos

* $n-\gamma+1 > 0$

    * El momento tiende a infinito según la red crece
    * Todos los momentos en los que $n > \gamma+1$ divergen

### Libre de escala

![Datos de redes reales. Podemos ver que la mayoría de los exponentes $\gamma$ tienen un valor entre 2 y 3](../images/tema03/datosRedesReales.png)

### Libre de escala

* El exponente del grado $\gamma$ tiene un valor entre 2 y 3
* El primer momento ($\langle k \rangle$) es finito
* La varianza (segundo momento o $\langle k^2 \rangle$) y el resto de momentos tienden a infinito

> Si esto es así entonces resulta que los valores medios no tienen realmente sentido ya que hay fluctuaciones demasiado grandes.<br/>**La escala interna (la media) no tiene sentido por lo que es una red "libre de escala"**

## Universalidad

### Universalidad

> ¿Son, en general, las redes reales libres de escala?

* Estudios de redes libres de escala
    
    * Price (1965): Redes científicas (el término aún no se conoce)
    * Barabasi (1999): WWW (acuña el término)
    * 1999: Internet (la red física de routers) y red de actores de Hollywood
    * ...: estudio en múltiples redes biológicas, tecnológicas y sociales: redes de interacción entre proteínas, comunidades virtuales, redes metabólicas, circuitos eléctricos, etc.
    * 2010: Twitter
    * 2011: Facebook

### Universalidad

![](../images/tema03/historia.png)

### Universalidad

* En todas hay diferencias de varios órdenes de magnitud entre los nodos con menor y mayor grado. 
* Los exponentes $\gamma$ de las funciones de distribución de grados son similares independientemente del dominio de la red.
* La mayoría de los exponentes varían entre 2 y 3.
* Las redes estudiadas muestran características comunes

### No todas las redes reales son libres de escala

* **No todas las redes son libres de escala**
* Contraejemplo: la red eléctrica (_Power grid_) no cumplen la propiedad de ser libre de escala.
* Contraejemplo: las redes existentes en materiales (enlaces atómicos que conforman estructuras cristalinas y amorfas)
* Contraejemplo: red neuronal del gusano _C.elegans_.
* Generalmente no aparece en redes en las que existe una limitación en el número de enlaces que un nodo puede tener (como la red eléctrica o la estructura atómica).

## Identificación de las redes libres de escala

### Representar gráficamente la distribución de grados

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Reiciendis doloribus ullam enim tempore suscipit odio explicabo consectetur at itaque ea, sed debitis, laboriosam atque dolorum? Dicta recusandae, quasi. Impedit, neque?

### Comprobar que la distribución sigue realmente una ley potencial

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Reiciendis doloribus ullam enim tempore suscipit odio explicabo consectetur at itaque ea, sed debitis, laboriosam atque dolorum? Dicta recusandae, quasi. Impedit, neque?

### Calcular el valor del exponente de la función

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Reiciendis doloribus ullam enim tempore suscipit odio explicabo consectetur at itaque ea, sed debitis, laboriosam atque dolorum? Dicta recusandae, quasi. Impedit, neque?

## Propiedad de los mundos ultra-pequeños

## Resumen

### Resumen



![Cuadro resumen](../images/tema03/resumen.png)

### Resumen

Las redes reales cumplen otra nueva ley que es la **propiedad libre de escala**:

> Muchas redes reales presentan distribuciones de cola ancha. Esto implica que nodos de grado bajo conviven con nodos con un grado excepcionalmente grande: los hubs.