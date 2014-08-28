% Apuntes sobre Markdown y Pandoc
% Guillermo Jiménes Díaz
% 2013/09/4

# Instrucciones para instalar Pandown {#inst}

Estas intrucciones son un resumen de [la documentación de Github][Pandown]. Primero es necesario instalar [PanDoc] y luego se puede instalar PanDown desde Sublime Text 2 usando el _Package Control_.

Para simiplificar el trabajo con MarkDown está bien instalar el paquete `Markdown Editing` y `MultiMarkdown` a través del _Package Control_

Una vez que está todo instalado ya podemos escribir el texto en Markdown. En particular se puede usar la versión de Markdown que utiliza [Pandoc][MDPandoc] y de la que destaco lo principal en la [siguiente sección](#mdpandoc).

Si compilamos con `Alt+Cmd+B` entonces genera en el buffer un HTML del documento (aparece en la misma ventana de Sublime). Con `Shift+Cmd+P` podemos realizar otros `Build` como, por ejemplo, a PDF (a través de Latex), Beamer o pases de dispositivas en HTML como Slidy, DZSlides (las más chulas) S5 o Slidious. Para que esto aparezca es necesario que el BuildSystem activo sea `Pandown MarkDown` (menú Tools-> BuildSystem).

Para saber más acerca de cómo crear transparencias usando Pandoc podemos [leer la siguiente sección del manual  de Pandoc](http://johnmacfarlane.net/pandoc/README.html#producing-slide-shows-with-pandoc)

# Sintaxis básica de Markdown en Pandoc {#mdpandoc}

## Énfasis simple

Cualquier palabra o texto entre `_` o `*` quedará enfatizado. Si ponemos dos `__` o dos `**` lo pondremos en negrita

## Cabeceras

Se escriben poniendo tantos símbolos `#` como nivel de cabecera que queramos poner (estilo ATX) o subrayando el texto de la cabecera con símbolos `=` o `-`. Por ejemplo:

    Cabeceras
    ---------

y 

    # Cabeceras

Generan el código `<h1>Cabeceras</h1>`

Las cabeceras pueden incluir un identificador usando `{#nombreId}`. De esta forma se pueden hacer [referencias cruzadas](#refCruz). También pueden tener otros atributos como `{.unnumbered}` o `{-}`, que hace que esa cabecera no esté numerada.

---

## Enlaces y referencias cruzadas {#refCruz}

Hay varias formas de añadir enlaces:
 
 - Enlaces _inline_: el texto del enlace se pone entre `[]` y la dirección del enlace se pone a continuación entre `()`. En la dirección se puede poner el identificador de una cabecera para hacer una _referencia cruzada_.
 - Enlaces _referencia_: El texto del enlace se pone entre `[]` y, a continuación, se pone el texto de la etiqueta entre `[]`. Si no se pone el texto de la etiqueta entonces el texto del enlace hace las veces de etiqueta. La definición del enlace en sí misma puede aparecer en cualquier otro lugar del texto y consiste en `[idLabel]: URL "título"` donde el título es el título del enlace, puede ir entre `""` o `()` y es opcional. La URL puede ir entre `<>`

---

## Imágenes

Son links precedidos del caracter `!`. El texto entre `[]` hace las veces de pie de figura. Si el enlace termina en `\` entonces significa que la imagen es inline dentro del párrafo en la que está escrita.

Por ejemplo `![Pie de figura: Ciclo](images/usabilityEngineeringCycle.jpg)` hace que salga lo siguiente:

![Pie de figura: Ciclo](images/usabilityEngineeringCycle.jpg)

---

## Enumeraciones y viñetas

Una lista con balas consiste en una serie de párrafos que empiezan con `*`. Por ejemplo, el texto:

    * Un
    * Dos
    * Tres

Se convierte en

* Un
* Dos
* Tres

Se puede añadir un nuevo nivel precediendo cada línea por un tabulador o 4 espacios en blanco. Aunque el símbolo a usar puede ser el mismo (`*`) Por ligibilidad se pueden usar otros símbolos (como `+` o `-`). Por ejemplo, el texto:

    * Uno
    * Uno.Uno
    * Uno.Dos
        * Uno.Dos.Uno


Se convierte en:

* Uno
    * Uno.Uno
    * Uno.Dos
        * Uno.Dos.Uno

Si queremos poner texto indentado con respecto a una viñeta entonces tendremos que dejar una línea en blanco tras la línea de la viñeta y, a continuación, escribir el párrafo comenzando por un tabulador o 4 espacios en blanco.

* Palabra

    Definición de la palabra

Las listas ordenadas comienzan por números, en lugar de símbolos. Los números que se pongan son ignorados por lo que la lista:

    1. Uno
    4. Dos
    5. Tres

Sirve para crear la lista enumerada

1. Uno
4. Dos
5. Tres

Podemos hacer que una lista enumerada continúe con la numeración después de poner algunos párrafos entre medias usando para numerarlos el símbolo `(@)`.

Si queremos que el siguiente texto indentado o de una lista no se considere como de la primera lista entonces tendremos que añadir un párrafo no indentado. Lo más habitual es poner un comentario HTML como `<!-- Fin de lista -->`

Por último, se pueden crear listas de definiciones (tienen sus propias marcas en HTML). Para hacerlo escribimos el nombre del término a definir y, dos párrafos después, escribimos la definición comenzando por `:` o `~`. Por ejemplo:

    Palabra 1

    :   Lorem ipsum dolor sit amet, consectetur adipisicing elit. Reiciendis, ullam, ut, odio, voluptates illum placeat tempora iste numquam delectus voluptas excepturi rem dolorum omnis obcaecati ratione sequi voluptatem earum voluptate.

    Palabra 2 (con **formato**)

    ~   Lorem ipsum dolor sit amet, consectetur adipisicing elit. Laborum, ut, recusandae, quam, aliquid dolores sapiente eveniet dolorem ipsam voluptatibus tempore doloribus voluptatum? Fugit, repudiandae ad mollitia amet temporibus animi quo.


Se convierte en:

Palabra 1

:   Lorem ipsum dolor sit amet, consectetur adipisicing elit. Reiciendis, ullam, ut, odio, voluptates illum placeat tempora iste numquam delectus voluptas excepturi rem dolorum omnis obcaecati ratione sequi voluptatem earum voluptate.

Palabra 2 (con **formato**)

~   Lorem ipsum dolor sit amet, consectetur adipisicing elit. Laborum, ut, recusandae, quam, aliquid dolores sapiente eveniet dolorem ipsam voluptatibus tempore doloribus voluptatum? Fugit, repudiandae ad mollitia amet temporibus animi quo.

## Citas y código

Cualquier párrafo que comienza con el caracter `>` se considera un bloque de cita ('quote'). Los bloques de citas se pueden anidar unos dentro de otros separando el siguiente bloque con un espacio en blanco y el símbolo `>`.

Los bloques de código (_verbatim_) son aquéllos que están indentados con un tabulador o 4 espacios en blanco. También se considera verbatim a todo aquello que haya entre dos líneas de al menos 3 `~` o 3 ` ` `. Como en

    ~~~~~~~
    if (a > 3) {
      moveShip(5 * gravity, DOWN);
    }
    ~~~~~~~
 
 que se convierte en

~~~~~~~
if (a > 3) {
  moveShip(5 * gravity, DOWN);
}
~~~~~~~

Al igual que a las cabeceras, podemos añadir atributos a los bloques de código (como identificadores, nombres de clase, lenguaje, etc.) poniéndolos entre `{ }` tras la línea de virgulillas o tildes.

## Notas al pie

Existen dos tipos de formato:

- Formato corto: Basta con poner `[^1]`. Luego pondremos el contenido de esa nota tal y como lo hicimos con las [referencias cruzadas](#refCruz) de la siguiente forma.

~~~
    [^1]: Contenido de la nota.
~~~

- Formato largo: Se utiliza cuando la nota ocupa varios párrafos. En este caso el enlace se caracteriza por poner un identificador: `[^identificador]`. Al igual que antes, usaremos las referencias cruzadas para poner el contenido de la nota.

## Algunos metadatos y caracteres de escape

Los documentos pueden contenrer ciertos metadatos que ayudan a algunos conversores a añadir información adicional. Por ejemplo, el bloque de título se define de la siguiente manera:

    % Título
    % Autores (separados por comas)
    % Fecha

Si lo convertimos a Beamos, por ejemplo, veremos que se convierte en la primera diapositiva de presentación. En HTML se convierte en el título de la página.

Los símbolos de escape llevan delante el símbolo `\`. Se pueden "escapar" los siguientes símbolos:

```
\`*_{}[]()>#+-.!
```


[PanDoc]: http://johnmacfarlane.net/pandoc/
[Pandown]: https://github.com/phyllisstein/Pandown
[MDPandoc]: http://johnmacfarlane.net/pandoc/README.html#pandocs-markdown