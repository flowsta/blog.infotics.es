---
id: 1011
title: Cómo citar una URL con BibTeX
author: Adolfo Antón Bravo
excerpt: BibTeX no ofrece una solución nativa para la cita de una URL, hay muchas formas de hacerlo.
layout: post
guid: http://infotics.es/?p=1011
permalink: /2014/04/15/como-citar-una-url-con-bibtex/
oc_metadata:
  - |
    {		version:'1.1',		tags: {'bibtex': {"text":"bibtex","slug":"bibtex","source":null,"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'enlace': {"text":"enlace","slug":"enlace","source":null,"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'howpublished': {"text":"howpublished","slug":"howpublished","source":null,"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'misc': {"text":"misc","slug":"misc","source":null,"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'natbib': {"text":"natbib","slug":"natbib","source":null,"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'note': {"text":"note","slug":"note","source":null,"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'tesis': {"text":"tesis","slug":"tesis","source":null,"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'url': {"text":"url","slug":"url","source":null,"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}}	}
oc_commit_id:
  - http://blogs.cuartocanal.es/infotics/2014/04/15/como-citar-una-url-con-bibtex/1397595614
categories:
  - bibtex
  - emacs
  - evento
  - latex
  - orgmode
tags:
  - bibtex
  - enlace
  - howpublished
  - misc
  - natbib
  - note
  - tesis
  - url
---
Al plantear esta pregunta he de suponer que conocemos qué es una *URL* y qué es *BibTeX*. 

Lo primero probablemente lo sabremos, pero por si acaso lo recordamos: [URL][1] es el acrónimo para *Uniform Resource Locator* o *localizador uniforme de recursos*, y nos referimos a él como *dirección* de un documento web, normalmente de una página web, pero también de un archivo *PDF*, cualquier otro archivo de texto, una imagen, un vídeo, una presentación, etc. Por ejemplo, son *urls*: 

<ul class="org-ul">
  <li>
    <a href="http://www.sindominio.net">http://www.sindominio.net</a>, que en realidad apunta al documento <i>HTML</i> o página web <a href="http://www.sindominio.net/index.html">http://www.sindominio.net/index.html</a>
  </li>
  <li>
    <a href="http://www.sindominio.net/ayuda/netiquette.pdf">http://www.sindominio.net/ayuda/netiquette.pdf</a>, la dirección de un archivo <i>PDF</i>
  </li>
</ul>

<img src="http://i2.wp.com/blogs.cuartocanal.es/infotics/files/2014/04/bibtex1.jpg?w=660" alt="relación bibtex y latex" data-recalc-dims="1" />

Para lo segundo tendremos que saber antes -o conviene saber antes- qué es *LaTeX*, y entonces esta introducción va a quedar más larga de lo que pretendía. Tal como dicen en su web, [LaTeX][2] es un sistema de composición de textos de alta calidad cuyas características lo hacen idóneo para la producción de documentación técnica y científica, motivos por los que se ha convertido en un estándar de facto para la comunicación y publicación de documentos científicos. Además, es [Software Libre][3]. Debo decir con pesar que su utilización es amplia en el mundo de las *ciencias puras* pero no es apenas conocido en el mundo de las *ciencias sociales*. Artículos como éste pretenden cambiar esa situación. 

<div id="outline-container-sec-1" class="outline-2">
  <h2 id="sec-1">
    Qué es BibTeX
  </h2>
  
  <div class="outline-text-2" id="text-1">
    <p>
      <i>BibTeX</i> permite gestionar bibliografías muy fácilmente con <i>LaTeX</i>. Para ello, comenzaremos por un archivo de texto simple que guardaremos con extensión <code>bib</code>. Éste va a contener todas las referencias bibliográficas que utilizaremos en uno o varios documentos a través de un enlace.
    </p>
    
    <p>
      Cada referencia que guardamos en el archivo <code>.bib</code> comienza con la información del tipo de documento que es esa referencia, seguido del identificador único para esa referencia en ese archivo <code>bib</code> y una serie de atributos. Cada tipo de documento tiene un nombre, unos atributos o campos obligatorios y otros opcionales.
    </p>
    
    <p>
      Veamos un ejemplo, imaginemos que tenemos un libro de <b>Gonzalo Abril</b> titulado <i>Teoría General de la información. Datos, relatos y ritos</i>, publicado por la <i>Editorial Cátedra</i> en Madrid en 1997. En <i>BibTeX</i>, estos datos se mostrarían así:
    </p>
    
    <pre class="example">
@book{abril1997teoria,
  title={Teor{'i}a general de la informaci{'o}n: datos, relatos y ritos},
  author={Abril, Gonzalo},
  year={1997},
  publisher={C{'a}tedra},
  address={Madrid}
  }
</pre>
    
    <p>
      Destripemos cada línea de esta referencia bibliográfica que compone nuestra bibliografía:
    </p>
    
    <ol class="org-ol">
      <li>
        La referencia empieza por el carácter <code>@</code> seguido del tipo de documento, en este caso <code>book</code> por tratarse de un libro.
      </li>
      <li>
        A continuación se abre la llave que guarda la información de ese elemento, que se cerrará al final del mismo.
      </li>
      <li>
        Dentro de la llave del elemento, cada atributo o campo se separa por comas.
      </li>
      <li>
        El primer elemento se trata del identificador único <code>abril1997teoria</code>, y esta es la referencia que luego vamos a utilizar desde el documento en <i>LaTeX</i> para citar.
      </li>
      <li>
        Los siguientes campos se declaran siguiendo la estructura <i>nombre_de_campo</i>, símbolo de igual <code>=</code> y <i>propiedad del campo</i> entre comillas dobles <code>""= o llaves ={}</code>. Aunque puede dar igual poner comillas dobles o llaves, con las llaves nos aseguramos de que el texto que ponemos se traduzca -en la exportación a <i>PDF</i>&#8211; tal cual.
      </li>
      <li>
        El último campo no hace falta que lleve coma al final.
      </li>
      <li>
        Nótese que para los carácteres <i>non-ASCII</i>, como por ejemplo las tildes, escribimos algo más que el propio carácter. Por ejemplo, en el caso de la <code>í</code> de <i>Teoría</i>, escribimos <code>Teor{'i}a</code>. De esta forma nos aseguramos el correcto trato y visualización de ese carácter.
      </li>
    </ol>
    
    <p>
      En este caso:
    </p>
    
    <ul class="org-ul">
      <li>
        <code>@book</code>, indica que se trata de un libro.
      </li>
      <li>
        <code>abril1997teoria</code>, es el identificador único de este libro en nuestro archivo bibliográfico, compuesto por tres nombres escrito todo seguido. Puede llamarse de otras formas en otros archivos pero el nombre responde a unas convenciones que nos resultarán útiles seguir: <ul class="org-ul">
          <li>
            <code>abril</code>, se corresponde con el apellido del autor/a.
          </li>
          <li>
            <code>1997</code>, se corresponde con el año de publicación, en este caso, del libro.
          </li>
          <li>
            <code>teoria</code>, responde a la primera palabra del título, sin tildes ni caracteres que no sean <i>us-ASCII</i> para facilitar su interoperabilidad. Esto permite diferenciarlo de otros libros del autor escritos el mismo año o incluso de autores distintos con el mismo apellido, por ejemplo.
          </li>
        </ul>
      </li>
      
      <li>
        Los otros campos obvio comentarlos.
      </li>
    </ul>
  </div></p>
</div>

<div id="outline-container-sec-2" class="outline-2">
  <h2 id="sec-2">
    Cómo citamos una URL con <i>BibTeX</i>
  </h2>
  
  <div class="outline-text-2" id="text-2">
    <p>
      Exacto, este era el título del artículo. Como señala <a href="http://nschloe.blogspot.de/2009/06/bibtex-how-to-cite-website_21.html">nschloe</a>, cuando se creó <i>BibTeX</i> no se introdujo un tipo de contenido para sitio web o <i>url</i>, por lo que se puede hacer de varias maneras. Ésta es sin duda la única pega que se le puede poner a <i>BibTeX</i> y se espera que se resuelva en la versión 1.0, que no tiene visos de llegar en breve.
    </p>
    
    <div id="wikipedia" class="figure">
      <p>
        <img src="http://i0.wp.com/blogs.cuartocanal.es/infotics/files/2014/04/lHzR31.png?w=660" alt="lHzR3.png" data-recalc-dims="1" />
      </p>
      
      <p>
        <span class="figure-number">Figure 1:</span> Ejemplo de citas de Wikipedia creadas con BibTeX
      </p></p>
    </div>
    
    <p>
      Por lo que he leído navegando por webs, foros y listas de correo, tenemos tenemos varias opciones para hacerlo, aquí muestro algunas:
    </p></p>
  </div>
  
  <div id="outline-container-sec-2-1" class="outline-3">
    <h3 id="sec-2-1">
      Tipo <code>Misc</code> y atributos
    </h3>
    
    <div class="outline-text-3" id="text-2-1">
      <p>
        La <a href="http://www.tex.ac.uk/cgi-bin/texfaq2html?label%3DciteURL">lista de correo de LaTeX de Reino Unido</a> propone utilizar el tipo de documento <code>@misc</code> con el atributo <code>howpublished</code> para incluir la <i>url</i> y <code>urldate</code> para indicar la fecha de acceso a esa <i>url</i>, donde quedaría así:
      </p>
      
      <pre class="example">
@misc{ASH:2013:Online,
author = {Varios Autores},
title = {Archivo Situacionista Hispano},
year = {1999},
howpublished = "url{http://sindominio.net/ash}",
urldate = {01-10-2013}
}
</pre>
      
      <p>
        No debemos olvidar, en este caso utilizar el paquete <code>url</code> de LaTeX en nuestro documento <code>tex</code>:
      </p>
      
      <pre class="example">
usepackage{url}
</pre>
      
      <p>
        En <a href="http://tex.stackexchange.com/questions/3587/how-can-i-use-bibtex-to-cite-a-web-page">StackExchange</a> sugieren utilizar el atributo <code>note</code> para indicar la fecha de acceso a la <i>url</i>, quedando algo así:
      </p>
      
      <pre class="example">
@misc{ASH:2013:Online,
author = {Varios Autores},
title = {Archivo Situacionista Hispano},
year = {1999},
howpublished = {url{http://sindominio.net/ash}},
note = {Accedido 01-10-2013}
}
</pre>
      
      <p>
        Y en <a href="http://www.citeulike.org/groupforum/1272">CiteULike</a> sugieren indicar la fecha en el mismo atributo <code>howpublished</code>, con lo cual entiendo que el atributo <code>note</code> queda libre para otro tipo de notas:
      </p>
      
      <pre class="example">
@misc{ASH:2013:Online,
author = {Varios Autores},
title = {Archivo Situacionista Hispano},
year = {1999},
howpublished = {Accedido en 01-10-2013 a url{http://sindominio.net/ash}},
}
</pre>
      
      <p>
        Por su parte, la <a href="https://en.wikipedia.org/w/index.php?title%3DSpecial%253aCite&#038;page%3DLaTeX&#038;id%3D413720397">Wikipedia</a> recomienda el tipo de entrada <code>@Misc</code> y el campo <code>url</code>:
      </p>
      
      <pre class="example">
@misc{ASH:2013:vvaa,
   author = {VVAA},
   title = {Archivo Situacionista Hispano},
   year = {1996},
   url = {URL{http://www.sindominio.net/ash}},
   note = "[Web; accedido el 06-11-2013]"
 }
</pre></p>
    </div></p>
  </div>
  
  <div id="outline-container-sec-2-2" class="outline-3">
    <h3 id="sec-2-2">
      Usar el paquete <i>natbib</i> y el atributo <code>url</code>
    </h3>
    
    <div class="outline-text-3" id="text-2-2">
      <p>
        <i>Natbib</i> extiende la funcionalidad de <i>Bibtex</i>, ampliando las posibilidades del comando <code>cite</code>. Aunque tampoco hay un tipo de entrada específico para recursos <i>online</i>, se pueden emplear los tipos de documento <code>@MISC</code>, <code>@OTHER</code>, y <code>@BOOKLET</code> con el atributo <code>url</code>. En el siguiente ejemplo, donde pone <code>BOOKLET</code> podemos poner cualquiera de los otros tipos de documentos.
      </p>
      
      <pre class="example">
@BOOKLET{ASH:2013:Booklet,
title = {Archivo Situacionista Hispano, {@BOOKLET}},
author = {VVAA},
year = {2013},
url = {http://www.sindominio.net/ash}
}
</pre>
      
      <p>
        Nótese que incorporamos <i>Booklet</i> como identificador para saber que se trata de una <i>url</i>
      </p>
      
      <p>
        En el archivo <code>tex</code> habría que añadir el paquete <i>natbib</i> y el <i>url</i>
      </p>
      
      <pre class="example">
documentclass{article}
usepackage{natbib}
bibliographystyle{plainnat}
usepackage{url}
title{Citar sitios web con BibTeX y el paquete texttt{natbib}}
date{}
begin{document}
maketitle
nocite{ASH:2013:Booklet,
ASH:2013:Misc,
ASH:2013:Other}
bibliography{test}
end{document}
</pre></p>
    </div></p>
  </div>
  
  <div id="outline-container-sec-2-3" class="outline-3">
    <h3 id="sec-2-3">
      Con el paquete <code>babelbib</code>
    </h3>
    
    <div class="outline-text-3" id="text-2-3">
      <p>
        El uso del paquete <code>babelbib</code>, que tal como cuentan en la <a href="http://www.tex.ac.uk/cgi-bin/texfaq2html?label%3DciteURL">lista de correo de LaTeX del Reino Unido</a> es otra posibilidad para citar sitios web. Además, nos permite utilizar elementos de la bibliografía de <i>BibTeX</i> en el idioma del documento, cuando es distinto del inglés con el comando <code>selectbiblanguage</code>. También lo explican en el blog <a href="http://utilidad-publica.blogspot.com.es/2012/02/bibtex-en-espanol.html">Servicio de Utilidad Pública</a>.
      </p>
      
      <pre class="example">
usepackage[fixlanguage]{babelbib}
selectbiblanguage{spanish}
</pre>
      
      <p>
        Esto nos permite utilizar las palabras en castellano en la referencia bibliográfica, es decir, <code>y</code> en vez de <code>and</code>, <code>editores</code> en vez de <code>editors</code>, <code>páginas</code> en vez de <code>pages</code> o <code>en</code> en lugar de <code>in</code>.
      </p>
      
      <p>
        Para utilizarlo correctamente, debemos utilizar un <i>estilo de bibliografía</i> que soporte <code>babelbib</code>, como son: <code>babplain</code>, <code>babplai3</code>, <code>babalpha</code>, <code>babunsrt</code>, <code>bababbrv</code> o <code>bababbr3</code>. En el caso del español, deberemos utilizar el estilo <code>spain</code>. La lista de estilos la podemos encontrar <a href="http://www.tex.ac.uk/cgi-bin/texfaq2html?label%3Di18nbib">aquí</a>.
      </p>
      
      <pre class="example">
bibliographystyle{babplain}
bibliography{sample}
</pre>
      
      <p>
        También podemos utilizar en cada entrada bibliográfica el idioma que queramos usar. Para ello, declararemos el paquete <code>babelbib</code> sin opciones y luego declaramos el idioma en la entrada:
      </p>
      
      <pre class="example">
usepackage{babelbib}
</pre>
      
      <pre class="example">
@article{mueller08,
  % ...
  language = {german}
}
</pre></p>
    </div></p>
  </div>
  
  <div id="outline-container-sec-2-4" class="outline-3">
    <h3 id="sec-2-4">
      <i>Biblatex</i> con el tipo <code>ONLINE</code>
    </h3>
    
    <div class="outline-text-3" id="text-2-4">
      <p>
        Según <a href="http://nschloe.blogspot.de/2009/06/bibtex-how-to-cite-website_21.html">nschloe</a>, otra posibilidad es utilizar el tipo de documento <code>ONLINE</code> que existe en <i>Biblatex</i>, una alternativa a <i>BibTeX</i>.
      </p>
      
      <p>
        Para ello, tendremos que utilizar el paquete <code>biblatex</code>:
      </p>
      
      <pre class="example">
usepackage{biblatex}
</pre>
      
      <p>
        Y en el archivo <code>bib</code>:
      </p>
      
      <pre class="example">
@ONLINE{ASH:2013:Online,
author = {Varios Autores},
title = {Archivo Situacionista Hispano, tipo {@ONLINE}},
year = {1999},
url = {http://sindominio.net/ash},
urldate = {2013-10-01}
}
</pre>
      
      <p>
        <i>Biblatex</i> contempla también otros tipos de contenidos como por ejemplo <code>@AUDIO</code> y <code>@VIDEO</code>.
      </p></p>
    </div></p>
  </div></p>
</div>

 [1]: https://es.wikipedia.org/wiki/Url
 [2]: http://www.latex-project.org/
 [3]: http://latex-project.org/lppl/