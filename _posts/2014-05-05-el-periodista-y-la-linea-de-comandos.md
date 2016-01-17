---
id: 1027
title: El periodista y la línea de comandos
author: Adolfo Antón Bravo
excerpt: 'Algunas notas al taller sobre línea de comandos realizado por Óscar Corcho para #jpd14'
layout: post
guid: http://infotics.es/?p=1027
permalink: /2014/05/05/el-periodista-y-la-linea-de-comandos/
oc_metadata:
  - |
    {		version:'1.1',		tags: {'command-line': {"text":"command line","slug":"command-line","source":null,"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'jpd14': {"text":"jpd14","slug":"jpd14","source":null,"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'lnea-de-comandos': {"text":"línea de comandos","slug":"lnea-de-comandos","source":null,"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'linux': {"text":"Linux","slug":"linux","source":null,"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'localidata': {"text":"localidata","slug":"localidata","source":null,"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'macos': {"text":"MacOS","slug":"macos","source":null,"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'medialab': {"text":"medialab","slug":"medialab","source":null,"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'medialab-prado': {"text":"medialab prado","slug":"medialab-prado","source":null,"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'scar-corcho': {"text":"Óscar Corcho","slug":"scar-corcho","source":null,"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}}	}
oc_commit_id:
  - http://blogs.cuartocanal.es/infotics/2014/05/05/el-periodista-y-la-linea-de-comandos/1399328109
categories:
  - big data
  - copyleft
  - cultura
  - data
  - debian
  - evento
  - Linked Data
  - Linked Open Data
  - Open Data
  - Open Data Gov
  - Open Gov
tags:
  - command line
  - jpd14
  - línea de comandos
  - Linux
  - localidata
  - MacOS
  - medialab
  - medialab prado
  - Óscar Corcho
---
**Óscar Corcho** ([@ocorcho][1]) realizó un taller sobre la *línea de comandos* para periodistas -es decir, para personas con un perfil técnico básico, pero perfil al fin y al cabo- en las últimas [II Jornadas de Periodismo de Datos y Open Data][2] celebradas en [Medialab Prado][3] entre el 22 y el 27 de abril. 

<figure id="attachment_1029" style="width: 1024px;" class="wp-caption alignnone"><a href="http://i1.wp.com/blogs.cuartocanal.es/infotics/files/2014/05/terminal.png" data-rel="lightbox-0" title=""><img src="http://i1.wp.com/blogs.cuartocanal.es/infotics/files/2014/05/terminal.png?fit=660%2C387" alt="Terminal en GNU/Linux" class="size-full wp-image-1029" data-recalc-dims="1" /></a><figcaption class="wp-caption-text">Terminal en GNU/Linux</figcaption></figure> 

Para el taller escribió este [artículo en el blog][4] de [LocaliData][5], empresa de la que es socio, de tal forma que pudiéramos tener una guía de referencia según nos iba contando. Os recomiendo seguirlo. Yo me he puesto con ello, a lxs periodistas nos viene muy bien manejar la línea de comandos. 

Pero antes, unos consejos que repetí a lxs asistentes mientras les ayudaba por las terminales: 

<ul class="org-ul">
  <li>
    Cuando se escribe el comando con algo parecido a <code>$ ls -la</code>, nótese que el símbolo del dólar solo indica el comienzo de la ejecución de órdenes, no hay que copiarla en tu línea de comandos, ya está ahí en tu propia terminal, si te fijas.
  </li>
  <li>
    La terminal autocompleta los comandos con tabulación. Si escribimos <code>cu</code> y le damos al tabulador, nos aparecerá en pantalla el listado de comandos que empiezan por <i>cu</i>
  </li>
  <li>
    Para echar un vistazo a los ficheros, tenemos el comando <code>more</code> y también <code>less</code>. Para salir de ellos hay que pinchar en la tecla <code>q</code>
  </li>
  <li>
    Como cuenta Óscar, las órdenes que damos van quedando almacenadas en un fichero al que podemos acceder viendo su listado completo tecleando el comando <code>history</code>.
  </li>
  <li>
    También nos puede resultar muy útil ejecutar algo que antes ya hemos ejecutado, pero cambiando una letra o una palabra porque no es exactamente igual lo que queremos hacer. Entonces le damos al cursor para arriba y nos saldrán las últimas órdenes que hemos escrito. Con el cursor hacia la izqda. o hacia la dcha. podemos posicionarnos sobre la palabra que queremos cambiar.
  </li>
  <li>
    Si hemos escrito mal un comando puede que no cante error y se quede esperando que escribas más o cualquier otra cosa, o puede que estés haciendo algo que lleva mucho tiempo y no se lo puedes dedicar. Para salir de ahí, teclea <i>CTRL + C</i>.
  </li>
</ul>

<div id="outline-container-sec-1" class="outline-2">
  <h2 id="sec-1">
    Retos
  </h2>
  
  <div class="outline-text-2" id="text-1">
    <p>
      En el taller planteaba algunos retos, que comentaré por aquí:
    </p></p>
  </div>
  
  <div id="outline-container-sec-1-1" class="outline-3">
    <h3 id="sec-1-1">
      ¿Cómo dividirías el fichero de comercios que hemos utilizado anteriormente para que los nombres de los ficheros que se generen comiencen como ComerciosMadrid_?
    </h3>
    
    <div class="outline-text-3" id="text-1-1">
      <p>
        Se trata de una funcionalidad del comando <code>split</code>. Tal como Óscar sugiere, a través de <code>split --help</code> o de <code>man split</code> vemos que la forma de añadir un prefijo a los archivos generados es añadir ese prefijo al final de la línea de opciones del comando. Es decir, si antes utilizamos:
      </p>
      
      <pre class="example">
$ split -l 2000 ComerciosMadrid.csv
</pre>
      
      <p>
        donde dividíamos el fichero <a href="https://dl.dropboxusercontent.com/u/1406775/ComerciosMadrid.csv">ComerciosMadrid.csv</a> en archivos de 2000 líneas con la estructura de nombres que ofrece <i>split</i> por defecto, en esta ocasión tendremos que poner:
      </p>
      
      <pre class="example">
$ split -l 2000 ComerciosMadrid.csv ComerciosMadrid_
</pre>
      
      <p>
        Hecho!
      </p></p>
    </div></p>
  </div>
  
  <div id="outline-container-sec-1-2" class="outline-3">
    <h3 id="sec-1-2">
      El comando cut también se puede utilizar para dividir un fichero en campos si tienen un tamaño predefinido (por ejemplo, los ficheros de Catastro o algunos ficheros de microdatos del INE). ¿Cuál sería el comando a utilizar para obtener del fichero de comercios de Madrid todos los códigos de los locales, que se encuentran en cada línea entre las posiciones 2 y 10? ¿Cuál es el tamaño final del fichero obtenido?
    </h3>
    
    <div class="outline-text-3" id="text-1-2">
      <p>
        Para los códigos entre las posiciones 2 y 10:
      </p>
      
      <pre class="example">
$ cut -f 2-10 -d ';' ComerciosMadrid.csv &gt; ComerciosMadridCodigosLocales.csv
</pre>
      
      <p>
        Tamaño del fichero, lo haremos con el comando <i>du</i> con la opción <code>-h</code> para que la salida del tamaño sea legible por humanos <img src="http://i1.wp.com/blogs.cuartocanal.es/infotics/wp-includes/images/smilies/simple-smile.png?w=660" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" data-recalc-dims="1" />
      </p>
      
      <pre class="example">
$ du -h ComerciosMadridCodigosLocales.csv 
14M	ComerciosMadridCodigosLocales.csv
</pre></p>
    </div></p>
  </div>
  
  <div id="outline-container-sec-1-3" class="outline-3">
    <h3 id="sec-1-3">
      Cómo buscarías los ficheros que contengan 100 MONTADITOS o 100 Montaditos? Es decir, ¿cómo harías las búsquedas independientes de si se utilizan mayúscula o minúsculas? ¿Cómo guardarías en un fichero todas las líneas que contienen 100 MONTADITOS?
    </h3>
    
    <div class="outline-text-3" id="text-1-3">
      <p>
        Enlazo estos dos retos para ponerlos en una sola línea, pasando la salida de la búsqueda al fichero deseado.
      </p>
      
      <p>
        Para la búsqueda con <i>grep</i> la opción <code>i</code> que ignora si son mayúsculas o minúsculas:
      </p>
      
      <pre class="example">
$ grep '100 MONTADITOS' -ri ComerciosMadrid.csv &gt; 100montaditos.csv
</pre>
      
      <p>
        Con <code>100 MONTADITOS</code> no he visto diferencias pero si buscas por ejemplo <code>peluqueria</code> verás los resultados con mayúsculas y minúsculas.
      </p></p>
    </div></p>
  </div>
  
  <div id="outline-container-sec-1-4" class="outline-3">
    <h3 id="sec-1-4">
      ¿Cómo reemplazarías cadenas como 100 MONTADITOS, y en general cualquier número seguido de un conjunto de caracteres, por la cadena de caracteres seguida del número (es decir, MONTADITOS 100)?
    </h3>
    
    <div class="outline-text-3" id="text-1-4">
      <p>
        Óscar ha puesto el ejemplo de <code>sed</code> de reemplazar la cadena <code>100 MONTADITOS</code> por <code>CIEN MONTADITOS</code>. Ojo que en el ejemplo que pone si queremos guardar el resultado, debemos enviarlo a un fichero. Es decir, si ponemos:
      </p>
      
      <pre class="example">
$ sed s/100\ MONTADITOS/CIEN\ MONTADITOS/ 100montaditos.csv
</pre>
      
      <p>
        Yo tengo el archivo <i>100montaditos.csv</i> de antes. Si escribo eso, la salida me aparecerá por la terminal. El fichero <i>100montaditos.csv</i> sigue tal cual estaba y no podemos hacer nada con el resultado del comando. Para hacer algo, para comprobarlo, para lo que sea, lo enviamos a otro fichero así:
      </p>
      
      <pre class="example">
$ sed s/100\ MONTADITOS/CIEN\ MONTADITOS/ 100montaditos.csv &gt; cienMontaditos.csv
</pre>
      
      <p>
        Si queremos, como plantea Óscar, cambiar el orden de las palabras, pues así lo escribimos al reves y lo enviamos al fichero <code>montaditosCien.csv</code> para luego comprobar el cambio con <code>more</code> (o <code>less</code>, como prefiráis).
      </p>
      
      <pre class="example">
$ sed s/100\ MONTADITOS/MONTADITOS\ CIEN/ 100montaditos.csv &gt; montaditosCien.csv
$ more montaditosCien.csv
</pre>
      
      <p>
        Para paginar en <code>more</code> utilizamos la barra espaciadora y para salir sin llegar al final, la tecla <code>q</code>
      </p>
      
      <p>
        El funcionamiento de <code>sed</code>, en esta orden, es muy fácil: cambia una cosa por otra, como si después quieres poner un soneto de Góngora. Eso sí, tienes que estar pendiente de que en la orden de sustitución, los espacios se <i>escapan</i>, son caracteres especiales, y por eso antes del espacio hay una barra invertida <i>\</i> que indica que va a escapar ese caracter. Si no pusiéramos la barra, el comando daría error, comprobadlo si queréis:
      </p>
      
      <pre class="example">
$ sed s/100 MONTADITOS/MONTADITOS CIEN/ 100montaditos.csv 
sed: -e expresión #1, carácter 5: orden `s' sin termina
</pre></p>
    </div></p>
  </div>
  
  <div id="outline-container-sec-1-5" class="outline-3">
    <h3 id="sec-1-5">
      ¿Podéis acceder a la descripción de la API de datos abiertos de Zaragoza e intentar determinar cuántos restaurantes hay en Zaragoza, según esta API?
    </h3>
    
    <div class="outline-text-3" id="text-1-5">
      <p>
        Lo he hecho enviando el resultado de <code>curl</code> a un fichero <code>restaurantesZaragoza.csv</code> y luego aplicando otra de las enseñanzas de Óscar, contar las líneas del fichero con <code>wc -l</code>, suponiendo que cada resultado esté en una línea, da como resultado <b>87</b>
      </p>
      
      <pre class="example">
$ curl -H "Accept:text/csv" http://www.zaragoza.es/api/recurso/turismo/restaurante &gt; restaurantesZaragoza.csv
$ wc -l restaurantesZaragoza.csv
87 restaurantesZaragoza.csv
</pre></p>
    </div></p>
  </div>
  
  <div id="outline-container-sec-1-6" class="outline-3">
    <h3 id="sec-1-6">
      ¿Cómo creéis que se podría obtener información de la provincia de Huesca en la API de datos de Open Data Aragón?
    </h3>
    
    <div class="outline-text-3" id="text-1-6">
      <p>
        Siguiendo el ejemplo que puso Óscar para la petición a <a href="http://opendata.aragon.es/">AragoDBpedia</a> del municipio de Jaca:
      </p>
      
      <pre class="example">
$ curl -H "Accept:text/csv" http://opendata.aragon.es/recurso/territorio/Municipio/Jaca.csv?api_key=e103dc13eb276ad734e680f5855f20c6\&_view=ampliada
</pre>
      
      <p>
        Y siguiendo la <a href="http://opendata.aragon.es/portal/desarrolladores/api-aragodbpedia">lógica expuesta en la web</a> de la <i>API</i> de AragoDBpedia
      </p>
      
      <pre class="example">
$ curl -H "Accept:text/csv" http://opendata.aragon.es/recurso/territorio/Provincia/Huesca.csv?api_key=e103dc13eb276ad734e680f5855f20c6\&_view=ampliada &gt; huesca.csv
</pre></p>
    </div></p>
  </div>
  
  <div id="outline-container-sec-1-7" class="outline-3">
    <h3 id="sec-1-7">
      ¿Cómo podemos obtener en un único fichero los datos completos de todos los restaurantes de Zaragoza, utilizando su API y algún script para tratar los datos adecuadamente?
    </h3>
    
    <div class="outline-text-3" id="text-1-7">
      <p>
        En un ejemplo anterior me bajaba los datos a un fichero <code>csv</code>, cuando en realidad no se trata de un fichero <code>csv</code>. En cualquier caso, por ahí podríamos empezar a tratarlos, aunque no se me ocurro cómo.
      </p></p>
    </div></p>
  </div>
  
  <div id="outline-container-sec-1-8" class="outline-3">
    <h3 id="sec-1-8">
      ¿Cuál sería el script a utilizar para que, dado el listado de todos los municipios de la provincia de Huesca, podamos hacer llamadas a la API de AragoDBpedia y obtener todos sus datos?
    </h3>
    
    <div class="outline-text-3" id="text-1-8">
      <p>
        Esto se lo preguntaré a Óscar <img src="http://i1.wp.com/blogs.cuartocanal.es/infotics/wp-includes/images/smilies/simple-smile.png?w=660" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" data-recalc-dims="1" />
      </p></p>
    </div></p>
  </div></p>
</div>

 [1]: https://www.twitter.com/ocorcho
 [2]: http://periodismodatos.okfn.es
 [3]: http://www.medialab-prado.es
 [4]: http://blog.localidata.com/2014/04/puede-un-periodista-usar-la-linea-de.html
 [5]: http://www.localidata.com