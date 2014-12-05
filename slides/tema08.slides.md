% Análisis de Redes Sociales
% Guillermo Jiménez Díaz (gjimenez@ucm.es); Alberto Díaz (albertodiaz@fdi.ucm.es)
% 5 de diciembre de 2014

# Tema 8: Propagación y Difusión en Redes {-}

### Propagación y Difusión

Modelar la propagación de elementos:

* Enfermedades
* Vídeos virales
* Rumores
* Virus informáticos
* Compra de productos
* Anuncios
* Información e innovación...

### Propagación y Difusión

> Modelos similares independientemente de lo que queramos propagar

* Basados en modelos de propagación clásicos de epidemias (1927)
* Aplicados a redes (2001)
* Estructura de la red influye en la propagación

### Propagación y Difusión

* Modelos de contagio simple
* Modelos de contagio aplicados a redes
* Modelos de contagio complejos
* Difusión de opiniones e innovación
* Aplicaciones

## Modelos de contagio simple

### Modelos de contagio simple

> La __epidemiología__ es la ciencia que estudia la salud y control de enfermedades en una población, así como la predicción de expansión de dichas enfermedades.

El modelo general se basa en dos hipótesis: 

- **Modelo compartimental**
- **Mezcla homogénea**

### Modelo compartimental

> Cada individuo puede estar en un determinado estado dependiendo de en qué fase se la enfermedad se encuentra.
 
- **Susceptible (S)**: El individuo está sano y puede ser infectado.
- **Infectado (I)**: El individuo está infectado y puede contagiar a otros individuos.
- **Recuperado (R)**: El individuo estuvo contagiado pero se ha recuperado y no puede volver a ser contagiado. También se utiliza para modelar los individuos que no han superado la enfermedad y que han muerto a causa de ella.

### Mezcla homogénea

> Cualquier individuo tiene la misma probabilidad de estar en contacto con un individuo infectado.

* Elimina la necesidad de conocer los contactos (la red) de individuos
* Se asume que cualquiera puede infectar a cualquiera.

### Modelos de contagio simple

> Los modelos observan los cambios de estado de los individuos a lo largo del tiempo para predecir el alcance y la velocidad de propagación de la enfermedad.

Estudiaremos la dinámica de los modelos de propagación  clásicos, que combinan las letras del modelo compartimental:

- Modelo SI
- Modelo SIS
- Modelo SIR

## Modelo SI

### Modelo SI

![](../images/tema08/modeloSI.png)

* Virus del VIH
* Zombies

### Modelo SI

* Cada individuo tiene $\langle k \rangle$ contactos 
* Tasa de contagio $\delta$: Probabilidad de que un individuo infectado transmita la enfermedad a uno susceptible.
* $N$ es el tamaño de la población: $N = S(t) + I(t)$
* $S(t)$: número de individuos que están en el estado susceptible en $t$
* $I(t)$: número de individuos que están en el estado infectado en $t$
* $s(t) = s = \frac{S(t)}{N}$: Proporción de susceptibles
* $i(t) = i = \frac{I(t)}{N}$: Proporción de infectados.
* $s+i=1$
* $\beta = \delta \cdot \langle k \rangle$: Tasa de transmisión

### Modelo SI

Tasa a la que varía el número de infectados

$$\frac{di}{dt} = i \cdot \beta  \cdot s = i \cdot \beta \cdot (1-i)$$

Resolviendo la ecuación:

$$i = \frac{i_0exp(\beta t)}{1-i_0+i_0exp(\beta t)}$$

### Modelo SI

![](../images/tema08/graficaSI.png)

### Conclusiones del modelo SI

> Inicialmente el número de infectados crece exponencialmente

> A medida que el número de infectados se hace mayor, hay menos individuos susceptibles por lo que el crecimiento de infectados se ralentiza

> La infección termina cuando todos están infectados
> <br/>$i(t \to \infty)= 1$

## Modelo SIS

### Modelo SIS

![](../images/tema08/modeloSIS.png)

* Resfriado común

### Modelo SIS

* Parámetros anteriores
* Tasa de recuperación $\mu$: Proporción de infectados que se recuperan y pasan al estado susceptible en cada instante de tiempo.

### Modelo SIS

Tasa a la que varía el número de infectados:

$$\frac{di}{dt} =  i \cdot \beta  \cdot s - \mu \cdot i=  i \cdot \beta \cdot (1-i) - \mu \cdot i$$

La resolución de esta ecuación:

$$i = \Big(1- \frac{\mu}{\beta}\Big) \frac{C \cdot e^{(\beta - \mu)t}}{1 + C \cdot e ^{(\beta -\mu)t}}$$

$$C= \frac{\beta \cdot i_0}{\beta - \mu - \beta \cdot i_0}$$

### Modelo SIS

![Representación de la proporción de infectados en el Modelo SIS](../images/tema08/graficaSIS.png)

### Conclusiones del Modelo SIS

- Como la recuperación es posible, el sistema alcanza un __estado endémico__ en el que la tasa de infectados es constante:

$$i(\infty) = 1 - \frac{\beta}{\mu}$$

- Sólo se produce cuando la tasa de recuperación es inferior a la tasa de transmisión ($\mu < \beta$)


- Si $\mu > \beta$ entonces, llegado a un determinado punto, la proporción de infectados comienza a decrecer exponencialmente, alcanzado un estado libre de enfermedad en la que todos los individuos se han recuperado y no hay infectados.

### Ritmo reproductivo básico

> El ritmo reproductivo básico ($R_0$) representa el número promedio de individuos susceptibles que serán infectados por un individuo infectado

$$R_0 = \frac{\beta}{\mu}$$

* Si $R_0<1$ entonces la enfermedad termina desapareciendo de la población
* Si $R_0>0$ entonces la enfermedad se propagará

### Ritmo reproductivo básico

* Cuanto mayor sea $R_0$, más rápido es el proceso de propagación de la enfermedad

> Sarampión: $R_0= 12-18$
> 
> Gripe: $R_0 = 2-3$

## Modelo SIR

### Modelo SIR

![Esquema del Modelo SIR](../images/tema08/modeloSIR.png)

### Modelo SIR

* $\mu$ representa la tasa de recuperación: es la tasa de individuos infectados que pasan al estado __recuperado__.
* $N = S(t) + I(t) + R(t)$
* $i = 1-s-r$.
* Condiciones iniciales habituales

$$i_0 = \frac{c}{N}\text{;  }s_0 = 1- \frac{c}{N}\text{;  }r_0 = 0$$


### Modelo SIR

$$\frac{di}{dt} = i \cdot \beta \cdot s - \mu \cdot i$$
$$\frac{ds}{dt} = -i \cdot \beta \cdot s$$
$$\frac{dr}{dt} = \mu \cdot i$$

### Modelo SIR

![Representación de la proporción de infectados, susceptibles y recuperados en el Modelo SIR](../images/tema08/graficaSIR.png)

### Conclusiones del Modelo SIR

- $\beta>\mu$: la proporción de infectados crece hasta un pico máximo y luego decrece hasta valer 0.
- $s$ decrece de forma monótona pero no llega nunca a 0
- Los individuos que se mantienen susceptibles hasta fases avanzadas pueden no llegar a infectarse nunca.

### Conclusiones del Modelo SIR

- $r$ crece de manera monótona.
- Nunca llega a valer 1
- Su valor asintótico __representa el número de individuos afectados__

$$r = 1- s_0 \cdot e^{-\beta \frac{r}{\mu}}$$

## Comportamientos importantes de los modelos epidemiológicos

### Comportamientos importantes

* __Comportamiento temprano__: patrón de comportamiento en las fases iniciales
    * Es importante para saber cuánto tiempo tenemos para el desarrollo de vacunas e intervenciones médica 
* __Comportamiento tardío__: patrón de comportamiento en las fases más avanzadas de la epidemia (cuando $t \to \infty$)
    * Permite predecir el alcance, número de infectados, etc.

### Comportamiento temprano

> En todos los modelos el número de infectados en la fase temprana es bajo pero crece exponencialmente.

> El modelo SI es el más relevante para describir este comportamiento

### Comportamiento tardío 

> Cada modelo realiza una predicción distinta

- En el modelo SI todos terminan infectados
- En el modelo SIS ($R_0>1$) se alcanza un estado endémico en el que una proporción de la población queda infectada
- En el modelo SIS ($R_0<1$) la enfermedad desaparece
- En el modelo SIR todos terminan recuperados (en el estado susceptible o recuperado, pero no infectados)


### Comportamientos de los modelos

![Características básicas de los modelos epidemiológicos](../images/tema08/resumenModelos.png)

### Modelos de contagio simple

> Estos modelos no tienen en cuenta la red de contactos ya que suponen que hay una mezcla homogénea

> Realmente, las epidemias se propagan a través de los contactos de las personas, es decir, a través de los enlaces de su red social

> La estructura de la red modificará el comportamiento de estos modelos simples
