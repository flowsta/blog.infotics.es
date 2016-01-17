---
id: 1079
title: El uso de RefTeX en Emacs con orgmode
author: Adolfo Antón Bravo
excerpt: Cómo utilizar RefTex en Emacs con orgmode
layout: post
guid: http://infotics.es/?p=1079
permalink: /2014/09/03/el-uso-de-reftex-en-emacs-con-orgmode/
oc_commit_id:
  - http://infotics.es/2014/09/03/el-uso-de-reftex-en-emacs-con-orgmode/1409769432
categories:
  - bibtex
  - emacs
  - latex
  - orgmode
  - reftex
tags:
  - bibliografía
  - bibtex
  - documentación
  - edición
  - emacs
  - latex
  - orgmode
  - tesis
---
*(actualizado 2015/08/01)* 

Hace unos meses me preguntaba [cómo citar una URL con BibTex][1], una pregunta que me intenté responder y que no considero cerrada, ya que lo que me gustaría es contar con una *solución* estándar, consensuada o al menos ampliamente utilizada. 

En esta ocasión, una vez que contamos con la bibliografía en *BibTeX* y estamos trabajando con *Emacs* en *orgmode*, como es mi caso, podemos utilizar *RefTeX* para gestionar la bibliografía. Me baso e el blog de [Marios Braindump][2] y en la experiencia propia. Hemos de realizar tres pasos: 

<ol class="org-ol">
  <li>
    Configurar <i>Emacs</i>
  </li>
  <li>
    Enlazar la bibliografía
  </li>
  <li>
    Realizar las referencias bibliográficas.
  </li>
</ol>

<div id="outline-container-unnumbered-1" class="outline-2">
  <h2 id="unnumbered-1">
    Configurar <i>Emacs</i>
  </h2>
  
  <div class="outline-text-2" id="text-unnumbered-1">
    <p>
      Hemos de configurar nuestro <i>Emacs</i> para que desde <i>orgmode</i> invoquemos a <i>RefTex</i> y definimos una bibliografía. Para ello, añadimos a nuestro archivo de configuración, por ejemplo, a <code>~/.emacs</code>
    </p>
    
    <pre class="example">
(defun org-mode-reftex-setup ()
(load-library "reftex")
(and (buffer-file-name)
(file-exists-p (buffer-file-name))
(reftex-parse-all))
(define-key org-mode-map (kbd "C-c )") 'reftex-citation)
)
(add-hook 'org-mode-hook 'org-mode-reftex-setup)
; Definimos nuestra bibliografía
(setq org-latex-to-pdf-process (list "latexmk -pdf -bibtex %f"))
(setq reftex-default-bibliography
      (quote
       ("~/ruta/bibliografia.bib")))
</pre>
  </div>
</div>

<div id="outline-container-unnumbered-2" class="outline-2">
  <h2 id="unnumbered-2">
    Enlazar la bibliografía
  </h2>
  
  <div class="outline-text-2" id="text-unnumbered-2">
    <p>
      Luego, enlazamos la bibliografía en el documento <i>org</i>, poniendo al final del mismo, pero antes de <code>\end{document}</code> las siguientes líneas:
    </p>
    
    <pre class="example">
\bibliographystyle{plain}
\bibliography{bibliografia}
</pre>
    
    <p>
      Donde <code>plain</code> es el estilo deseado para la bibliografía (<a href="http://www.reed.edu/cis/help/latex/bibtexstyles.html">hay siete estilos estándar</a>, multitud de estilos específicos e incluso puedes crear uno a tu medida) y <code>bibliografia</code> es la ruta al archivo con la bibliografía en <i>BibTeX</i>; en este caso, el archivo <code>bibliografia.bib</code>, se encuentra en el mismo directorio que el archivo <code>org</code>. También podemos incluir bibliografía en el propio documento <code>org</code> con el entorno de <i>LaTeX</i> <code>\thebibliography</code>.
    </p>
  </div>
</div>

<div id="outline-container-unnumbered-3" class="outline-2">
  <h2 id="unnumbered-3">
    Referencias bibliográficas
  </h2>
  
  <div class="outline-text-2" id="text-unnumbered-3">
    <p>
      Para insertar las citas bibliográficas escribiremos en <i>Emacs</i>, tal como hemos configurado en <code>.emacs</code>, <code>C-c )</code> o bien invocando <code>reftex-citation</code>.
    </p>
    
    <div class="figure">
      <p>
        <img src="http://i2.wp.com/infotics.es/files/2015/08/wpid-sugerencia-reftex.png?w=660" alt="sugerencia-reftex.png" data-recalc-dims="1" />
      </p>
      
      <p>
        <span class="figure-number">Figure 1:</span> Invocando RefTeX nos sugiere si queremos buscar con respecto a las palabras que hemos seleccionado en el documento, en este caso Berners. Si no es esa la palabra, podemos escribir otra. Luego pulsamos Enter
      </p></p>
    </div>
    
    <p>
      <i>RefTex</i> nos sugerirá una palabra de nuestra selección para realizar la búsqueda sobre la bibliografía. Si no nos gusta esa sugerencia, podemos introducir una expresión regular -el apellido del autor del libro o una palabra del título, por ejemplo&#x2026; en definitiva, algo que recordemos de esa referencia- con la que buscará en nuestra bibliografía, bien en el archivo <code>bib</code> externo, bien en las referencias embebidas o en la bibliografía externa.
    </p>
    
    <p>
      Se mostrará un <i>buffer</i> con la lista de resultados y podremos seleccionar el que estemos buscando.
    </p>
    
    <div class="figure">
      <p>
        <img src="http://i0.wp.com/infotics.es/files/2015/08/wpid-listado-citas.png?w=660" alt="listado-citas.png" data-recalc-dims="1" />
      </p>
      
      <p>
        <span class="figure-number">Figure 2:</span> Buscamos sobre la/s bibliografías que hayamos enlazado la expresión regular Invocando RefTeX nos sugiere si queremos buscar con respecto a las palabras que hemos seleccionado en el documento, en este caso Berners. Si no es esa la palabra, podemos escribir otra. Luego pulsamos Enter
      </p></p>
    </div>
    
    <p>
      En el texto nos aparace la cita:
    </p>
    
    <pre class="example">
(...) fue inaugurada por Tim Berners-Lee \cite{berners-lee2000tejiendo} en el laboratorio (...)
</pre>
    
    <div class="figure">
      <p>
        <img src="http://i1.wp.com/infotics.es/files/2015/08/wpid-cita-reftex.png?w=660" alt="cita-reftex.png" data-recalc-dims="1" />
      </p>
      
      <p>
        <span class="figure-number">Figure 3:</span> La cita se ha insertado correctamente en el documento
      </p></p>
    </div>
  </div>
</div>

 [1]: http://infotics.es/2014/04/15/como-citar-una-url-con-bibtex/
 [2]: http://www.mfasold.net/blog/2009/02/using-emacs-org-mode-to-draft-papers/