---
id: 1354
title: Peticiones de asilo en países europeos
author: Adolfo Antón Bravo
layout: post
guid: http://infotics.es/?p=1354
permalink: /2015/11/18/peticiones-de-asilo-en-paises-europeos/
categories:
  - dataviz
  - datawrapper
  - github
  - project
  - proyecto
  - refugees
tags:
  - 2015
  - asilo
  - Europa
  - refugiados
  - refugiadxs
  - UE
---
En el artículo de la Wikipedia [La crisis migratoria en Europa](https://es.wikipedia.org/wiki/Crisis_migratoria_en_Europa), hay un gráfico de [Chumwa](https://de.wikipedia.org/wiki/User:Chumwa) con un mapa que combina una serie de datos:

-   Gráfico de barras de países de origen de lxs refugiadxs, divididas las peticiones de asilo si son la primera vez o si repiten.
-   Gráfico de barras sobre los países con el número de peticiones de asilo durante los seis primeros meses de 2015, con la misma división.
-   Cartograma con cloropetas en función de las peticiones de asilo por cada 10.000 habitantes
-   Flechas más o menos gruesas sobre el mapa con las rutas migratorias más importantes.
-   Gráfico de áreas con el número de solicitudes por mes, con la misma división.

![img](//upload.wikimedia.org/wikipedia/commons/thumb/8/80/Map_of_the_European_Migrant_Crisis_2015.png/516px-Map_of_the_European_Migrant_Crisis_2015.png)

El gráfico completo de 2192 x 2040 pixels se encuentra [aquí](https://upload.wikimedia.org/wikipedia/commons/8/80/Map_of_the_European_Migrant_Crisis_2015.png).

# Fuentes de datos

Las fuentes del mapa son varias:

-   Datos de peticiones de asilo de Eurostat: <http://appsso.eurostat.ec.europa.eu/nui/show.do?dataset=migr_asyappctzm>
-   Datos de población de países de Europa de Eurostat: <http://appsso.eurostat.ec.europa.eu/nui/show.do?dataset=tps00001>
-   Rutas migratorias según FRONTEX: <http://frontex.europa.eu/trends-and-routes/migratory-routes-map/>

# Peticiones de asilo

Siguiendo los datos de peticiones de asilo, he creado este [gráfico](https://flowsta.github.io/refugees-wellcome/) en [Datawrapper](https://www.datawrapper.de) sobre las peticiones de asilo aprobadas en países europeos:

## Web en GitHub Pages

Dado que [Datawrapper](https://datawrapper.de) cambió en diciembre de 2014 sus [condiciones de publicación](http://blog.datawrapper.de/2014/new-usage-guidelines-for-datawrapper/) y como usuarix gratuito te permite descargarte un *zip* con el proyecto, he creado una rama del [proyecto de GitHub donde está documentado esto](https://github.com/flowsta/refugees-wellcome) llamada *gh-pages* para publicar el contenido del *zip*, que está publicado aquí:

<https://flowsta.github.io/refugees-wellcome/>

Si se quiere embeber en una página, se puede incluir este código:

    <iframe src="https://flowsta.github.io/refugees-wellcome/" width="600" height="980" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

# El gráfico

Incrustado con un `iframe` desde `//flowsta.github.io/refugees-wellcome`

<iframe src="https://flowsta.github.io/refugees-wellcome/" width="600" height="980" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

# Gist

Siguiendo las indicaciones de [ferblape](https://twitter.com/ferblape), me comentó que se podría usar [gist](https://gist.githubeusercontent.com/), una parte de *GitHub* donde se puede subir código y compartirlo con otras personas.

Funciona prácticamente como un nuevo proyecto, de tal manera que tiene una *URL* pública y se puede editar y actualizar, pero *GitHub* no sirve *HTML* de *gist*.

Sin embargo, el proyecto [bl.ocks.org](http://bl.ocks.org) de [Mike Bostock](http://bost.ocks.org/mike/), el creador de [d3](http://www.d3js.org) visualiza todos los proyectos *gist* en *HTML*, como por ejemplo [este que nos sirve de ejemplo](http://bl.ocks.org/flowsta/raw/9aa589f4317ffe8f66d2/).

De esta forma, se puede embeber el *HTML* en nuestra web:

    <iframe src="http://bl.ocks.org/flowsta/raw/9aa589f4317ffe8f66d2/" width="600" height="980" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

Y así se muestra:

<iframe src="http://bl.ocks.org/flowsta/raw/9aa589f4317ffe8f66d2/" width="600" height="980" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

Hay que tener en cuenta que en *gist* subimos todos los archivos que queramos pero si los tenemos relacionados con rutas relativas dentro de carpetas, como por ejemplo los documentos *js* en la carpeta *js*, debemos editar la ruta del `index.html` para que sea relativa al mismo directorio, es decir, que un enlace a un `.js` será:

    <link rel="stylesheet" type="text/css" href="32iVz.all.css"></link>
    <script type="text/javascript" charset="utf-8" src="default-5baee189e1a2f0bf680f4910cc958098.min.js"></script>

De hecho, en un primer momento descarté esta opción porque no salía nada, es decir, la ruta estaba relativa al directorio *js* y no mostraba nada, pero después de mirarlo en otro momento (la importancia del tiempo), de las indicaciones de @ferblape y de los ejemplos que ha trabajado [@adrianblancor](https://twitter.com/adrianblancor) en [bl.ocks.org](http://bl.ocks.org/adrianblanco), reparé en este detalle :)

# Dropbox

Si subimos el contenido del `zip` a nuestro espacio público de [dropbox](https://dropbox.com), también podemos embeberlo con un `iframe`:

-   [Directorio de dropbox](https://www.dropbox.com/sh/s3b71m985f7nzmx/AAA9_Vsne2U0lzTKkmcot02na?dl=0)
-   [index.html](https://dl.dropboxusercontent.com/u/19167367/prueba-dw/index.html)

Se incluye este código, donde solo cambia la *URL*. Hemos de incluir la *URL* que termina en `index.html`. Esto lo conseguimos en la carpeta de dropbox, con el botón derecho sobre el archivo `index.html` y la opción *Copy Public Link*.

    <iframe src="https://dl.dropboxusercontent.com/u/19167367/prueba-dw/index.html" width="600" height="980" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

Y así se muestra:

<iframe src="https://dl.dropboxusercontent.com/u/19167367/prueba-dw/index.html" width="600" height="980" frameborder="0" allowfullscreen="allowfullscreen"></iframe>

Me comenta [@maguilera\_](https://twitter.com/maguilera_) que con su usuario nuevo de [dropbox](https://www.dropbox.com) no le permite hacer esto. Si alguien tiene alguna otra experiencia al respecto, que no dude en comentarlo por aquí o por *twitter*.
