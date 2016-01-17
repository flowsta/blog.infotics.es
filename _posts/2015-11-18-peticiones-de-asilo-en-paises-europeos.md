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
En el artículo de la Wikipedia [La crisis migratoria en Europa][1], hay un gráfico de [Chumwa][2] con un mapa que combina una serie de datos: 

<ul class="org-ul">
  <li>
    Gráfico de barras de países de origen de lxs refugiadxs, divididas las peticiones de asilo si son la primera vez o si repiten.
  </li>
  <li>
    Gráfico de barras sobre los países con el número de peticiones de asilo durante los seis primeros meses de 2015, con la misma división.
  </li>
  <li>
    Cartograma con cloropetas en función de las peticiones de asilo por cada 10.000 habitantes
  </li>
  <li>
    Flechas más o menos gruesas sobre el mapa con las rutas migratorias más importantes.
  </li>
  <li>
    Gráfico de áreas con el número de solicitudes por mes, con la misma división.
  </li>
</ul>

<div class="figure">
  <p>
    <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/8/80/Map_of_the_European_Migrant_Crisis_2015.png/516px-Map_of_the_European_Migrant_Crisis_2015.png" alt="516px-Map_of_the_European_Migrant_Crisis_2015.png" />
  </p></p>
</div>

El gráfico completo de 2192 x 2040 pixels se encuentra <a href="https://upload.wikimedia.org/wikipedia/commons/8/80/Map_of_the_European_Migrant_Crisis_2015.png" data-rel="lightbox-0" title="">aquí</a>. 

<div id="outline-container-orgheadline1" class="outline-2">
  <h2 id="orgheadline1">
    Fuentes de datos
  </h2>
  
  <div class="outline-text-2" id="text-orgheadline1">
    <p>
      Las fuentes del mapa son varias:
    </p>
    
    <ul class="org-ul">
      <li>
        Datos de peticiones de asilo de Eurostat: <a href="http://appsso.eurostat.ec.europa.eu/nui/show.do?dataset=migr_asyappctzm">http://appsso.eurostat.ec.europa.eu/nui/show.do?dataset=migr_asyappctzm</a>
      </li>
      <li>
        Datos de población de países de Europa de Eurostat: <a href="http://appsso.eurostat.ec.europa.eu/nui/show.do?dataset=tps00001">http://appsso.eurostat.ec.europa.eu/nui/show.do?dataset=tps00001</a>
      </li>
      <li>
        Rutas migratorias según FRONTEX: <a href="http://frontex.europa.eu/trends-and-routes/migratory-routes-map/">http://frontex.europa.eu/trends-and-routes/migratory-routes-map/</a>
      </li>
    </ul>
  </div>
</div>

<div id="outline-container-orgheadline2" class="outline-2">
  <h2 id="orgheadline2">
    Peticiones de asilo
  </h2>
  
  <div class="outline-text-2" id="text-orgheadline2">
    <p>
      Siguiendo los datos de peticiones de asilo, he creado este <a href="https://flowsta.github.io/refugees-wellcome/">gráfico</a> en Datawrapper sobre las peticiones de asilo aprobadas en países europeos:
    </p>
    
    <p>
      Dado que <a href="https://datawrapper.de/">Datawrapper</a> cambió en diciembre de 2014 sus <a href="http://blog.datawrapper.de/2014/new-usage-guidelines-for-datawrapper/">condiciones de publicación</a> y como usuarix gratuito te permite descargarte un <i>zip</i> con el proyecto, he creado una rama en el proyecto de GitHub llamada <i>gh-pages</i> para publicar el contenido del <i>zip</i>, que está publicado aquí:
    </p>
    
    <p>
      <a href="https://flowsta.github.io/refugees-wellcome/">https://flowsta.github.io/refugees-wellcome/</a>
    </p>
    
    <p>
      Si se quiere embeber en una página, se puede incluir este código:
    </p>
    
    <div class="org-src-container">
      <pre class="src src-html">&lt;<span style="color: #93E0E3;">iframe</span> <span style="color: #DFAF8F;">src</span>=<span style="color: #CC9393;">"https://flowsta.github.io/refugees-wellcome/"</span> <span style="color: #DFAF8F;">width</span>=<span style="color: #CC9393;">"600"</span> <span style="color: #DFAF8F;">height</span>=<span style="color: #CC9393;">"980"</span> <span style="color: #DFAF8F;">frameborder</span>=<span style="color: #CC9393;">"0"</span> <span style="color: #DFAF8F;">allowfullscreen</span>=<span style="color: #CC9393;">"allowfullscreen"</span>&gt;&lt;/<span style="color: #93E0E3;">iframe</span>&gt;
</pre>
    </div>
  </div>
</div>

<div id="outline-container-orgheadline3" class="outline-2">
  <h2 id="orgheadline3">
    El gráfico
  </h2>
  
  <div class="outline-text-2" id="text-orgheadline3">
  </div>
</div>

 [1]: https://es.wikipedia.org/wiki/Crisis_migratoria_en_Europa
 [2]: https://de.wikipedia.org/wiki/User:Chumwa