---
id: 1163
title: Cómo utilizar org2blog con bloques de código
author: Adolfo Antón Bravo
layout: post
guid: http://infotics.es/?p=1163
permalink: /2015/02/06/como-utilizar-org2blog-con-bloques-de-codigo/
categories:
  - emacs
  - org-mode
  - wordpress
tags:
  - elisp
  - emacs
  - highlight
  - lisp
  - org2blog
---
Si utilizas Emacs con org-mode y tu blog es WordPress, org2blog es la mejor herramienta para publicar directamente desde orgmode a WordPress. Si no sabes de qué estoy hablando, no dejes de leer por si quieres adaptar esta forma escribir no solo artículos para tu blog sino también todo tipo de textos y documentación. 

<!--more-->

<div class="figure">
  <p>
    <img src="http://i0.wp.com/blogs.cuartocanal.es/infotics/files/2015/02/wpid-screenie-org2blog11.png?w=660" alt="wpid-screenie-org2blog1.png" data-recalc-dims="1" />
  </p></p>
</div>

En este artículo, basado en el de [vxlabs][1] y [binchen][2], pretende animarte a introducir bloques de código en tus artículos de tal forma que resulte útil su identificación como código, facilite su lectura y permita su reutilización. 

<div id="outline-container-sec-1" class="outline-2">
  <h2 id="sec-1">
    Primer paso: adaptar org2blog/wp-sourcecode-langs
  </h2>
  
  <div class="outline-text-2" id="text-1">
    <p>
      org2blog tiene una variable <code>org2blog/wp-sourcecode-langs</code> que soporta muchos lenguajes de programación&#x2026; pero no incluye <i>lisp</i>.
    </p>
    
    <p>
      Por tanto, hay que modificar ese código añadiendo <i>lisp</i>, <i>elisp</i> y <i>lua</i>:
    </p>
    
    <div class="org-src-container">
      <pre class="src src-lisp">(setq org2blog/wp-sourcecode-langs
      '(<span style="color: #CC9393;">"actionscript3"</span> <span style="color: #CC9393;">"bash"</span> <span style="color: #CC9393;">"coldfusion"</span> <span style="color: #CC9393;">"cpp"</span> <span style="color: #CC9393;">"csharp"</span> <span style="color: #CC9393;">"css"</span> <span style="color: #CC9393;">"delphi"</span>
        <span style="color: #CC9393;">"erlang"</span> <span style="color: #CC9393;">"fsharp"</span> <span style="color: #CC9393;">"diff"</span> <span style="color: #CC9393;">"groovy"</span> <span style="color: #CC9393;">"javascript"</span> <span style="color: #CC9393;">"java"</span> <span style="color: #CC9393;">"javafx"</span> <span style="color: #CC9393;">"matlab"</span>
        <span style="color: #CC9393;">"objc"</span> <span style="color: #CC9393;">"perl"</span> <span style="color: #CC9393;">"php"</span> <span style="color: #CC9393;">"text"</span> <span style="color: #CC9393;">"powershell"</span> <span style="color: #CC9393;">"python"</span> <span style="color: #CC9393;">"ruby"</span> <span style="color: #CC9393;">"scala"</span> <span style="color: #CC9393;">"sql"</span>
        <span style="color: #CC9393;">"vb"</span> <span style="color: #CC9393;">"xml"</span>
        <span style="color: #CC9393;">"sh"</span> <span style="color: #CC9393;">"elisp"</span> <span style="color: #CC9393;">"lisp"</span> <span style="color: #CC9393;">"lua"</span>))
</pre>
    </div>
  </div>
</div>

<div id="outline-container-sec-2" class="outline-2">
  <h2 id="sec-2">
    Segundo paso: modificar SyntaxHighlighter Evolved
  </h2>
  
  <div class="outline-text-2" id="text-2">
    <p>
      Por el lado de WordPress, tendremos que insalar el plugin <a href="http://www.viper007bond.com/wordpress-plugins/syntaxhighlighter/">SyntaxHighlighter Evolved</a> para señalar el código. También hay que editar este plugin para permitir que reconozca lenguajes como <i>elisp</i>. En el archivo <code>syntaxhighlighter.php</code> añade estas líneas donde corresponde:
    </p>
    
    <div class="org-src-container">
      <pre class="src src-php">'text'          =&gt; 'clojure',
'elisp'         =&gt; 'clojure',
'lisp'          =&gt; 'clojure',
'sh'            =&gt; 'bash',
'lua'           =&gt; 'ruby',
</pre>
    </div>
    
    <p>
      En el artículo original decidieron utilizar el resaltado propio de <i>clojure</i> para <i>text</i>, <i>lisp</i> y <i>elisp</i>, <i>bash</i> para <i>sh</i> y <i>ruby</i> para <i>lua</i>. Puedes mantenerlo así o adaptarlo como prefieras con otras configuraciones.
    </p>
    
    <p>
      El motivo por el que señalar un bloque de código en <i>text</i> es porque si no señalas el tipo de lenguaje que estás poniendo en el código, éste no aparecerá señalado. Si usas <i>Emacs</i>, lo habitual es poner mucho código en <i>lisp</i>, por lo que si no quieres identificarlo, de esta manera te aseguras que el bloque de texto <i>text</i> tenga el mismo resaltado que <i>lisp</i>.
    </p>
  </div>
</div>

<div id="outline-container-sec-3" class="outline-2">
  <h2 id="sec-3">
    Postdata: otra opción
  </h2>
  
  <div class="outline-text-2" id="text-3">
    <p>
      Hay un <a href="http://blog.binchen.org/posts/how-to-use-org2blog-effectively-as-a-programmer.html#comment-1348043006">comentario en el blog de binchen</a> que apunta que si añadimos:
    </p>
    
    <div class="org-src-container">
      <pre class="src src-lisp">(setq org-src-fontify-natively t)
</pre>
    </div>
    
    <p>
      Nos evitamos la modificación de emacs. Habrá que probarlo <img src="http://i1.wp.com/blogs.cuartocanal.es/infotics/wp-includes/images/smilies/simple-smile.png?w=660" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" data-recalc-dims="1" />
    </p>
  </div>
</div>

 [1]: http://vxlabs.com/2014/05/25/emacs-24-with-prelude-org2blog-and-wordpress/
 [2]: http://blog.binchen.org/posts/how-to-use-org2blog-effectively-as-a-programmer.html