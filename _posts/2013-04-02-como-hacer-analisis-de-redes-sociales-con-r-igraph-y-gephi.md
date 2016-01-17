---
id: 724
title: Cómo hacer análisis de redes sociales con R-igraph y Gephi
author: Adolfo Antón Bravo
layout: post
guid: http://blogs.cuartocanal.es/infotics/?p=724
permalink: /2013/04/02/como-hacer-analisis-de-redes-sociales-con-r-igraph-y-gephi/
dublin_core_author:
  - Enter author here
dublin_core_subject:
  - Enter comma separated keywords here
dublin_core_title:
  - Enter title here
dublin_core_description:
  - Enter description here
dublin_core_source:
  - Enter source here
dublin_core_publisher:
  - Enter publisher here
dublin_core_contributor:
  - Enter contributor here
dublin_core_rights:
  - Enter rights here
oc_metadata:
  - |
    {		version:'1.1',		tags: {'gregorio-serrano-los': {"text":"Gregorio Serrano Los","slug":"gregorio-serrano-los","source":{"_className":"Entity","url":"http://d.opencalais.com/pershash-1/56b35139-e0c4-3283-9f29-9bdfdc8df144","subjectURL":null,"type":{"_className":"ArtifactType","url":"http://s.opencalais.com/1/type/em/e/Person","name":"Person"},"name":"Gregorio Serrano Los","rawRelevance":0.155,"normalizedRelevance":0.3235908141962422},"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'carlos-ortega-shiny': {"text":"Carlos Ortega Shiny","slug":"carlos-ortega-shiny","source":{"_className":"Entity","url":"http://d.opencalais.com/pershash-1/57d77f79-cece-35f2-aec4-e977ac013781","subjectURL":null,"type":{"_className":"ArtifactType","url":"http://s.opencalais.com/1/type/em/e/Person","name":"Person"},"name":"Carlos Ortega Shiny","rawRelevance":0.168,"normalizedRelevance":0.35073068893528186},"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'colegio-argentino': {"text":"Colegio Argentino","slug":"colegio-argentino","source":{"_className":"Entity","url":"http://d.opencalais.com/genericHasher-1/f6a497e1-8ed1-3e8c-9560-4ef8e8ac11ee","subjectURL":null,"type":{"_className":"ArtifactType","url":"http://s.opencalais.com/1/type/em/e/Organization","name":"Organization"},"name":"Colegio Argentino","rawRelevance":0.109,"normalizedRelevance":0.22755741127348644},"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'martn-fierro': {"text":"Martín Fierro","slug":"martn-fierro","source":{"_className":"Entity","url":"http://d.opencalais.com/pershash-1/dee78131-4313-3aa9-84ee-cb67a93f3d99","subjectURL":null,"type":{"_className":"ArtifactType","url":"http://s.opencalais.com/1/type/em/e/Person","name":"Person"},"name":"Martín Fierro","rawRelevance":0.146,"normalizedRelevance":0.3048016701461378},"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'juan-de-herrero': {"text":"Juan de Herrero","slug":"juan-de-herrero","source":{"_className":"Entity","url":"http://d.opencalais.com/pershash-1/f876ce51-dfd8-38aa-908b-5e3dbcd2f699","subjectURL":null,"type":{"_className":"ArtifactType","url":"http://s.opencalais.com/1/type/em/e/Person","name":"Person"},"name":"Juan de Herrero","rawRelevance":0.109,"normalizedRelevance":0.22755741127348644},"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'pedro-concejero': {"text":"Pedro Concejero","slug":"pedro-concejero","source":{"_className":"Entity","url":"http://d.opencalais.com/pershash-1/2da8390a-20ea-3d7b-a091-464ffd3577b0","subjectURL":null,"type":{"_className":"ArtifactType","url":"http://s.opencalais.com/1/type/em/e/Person","name":"Person"},"name":"Pedro Concejero","rawRelevance":0.155,"normalizedRelevance":0.3235908141962422},"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'r-de-madrid': {"text":"R de Madrid","slug":"r-de-madrid","source":{"_className":"Entity","url":"http://d.opencalais.com/comphash-1/3ccacab3-5166-32b8-9623-ffc277163173","subjectURL":null,"type":{"_className":"ArtifactType","url":"http://s.opencalais.com/1/type/em/e/Company","name":"Company"},"name":"R de Madrid","rawRelevance":0.325,"normalizedRelevance":0.6784968684759917},"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'rafael-garca-leiva': {"text":"Rafael García Leiva","slug":"rafael-garca-leiva","source":{"_className":"Entity","url":"http://d.opencalais.com/pershash-1/19fe6d41-cd96-38ad-84c6-f6628a4f9560","subjectURL":null,"type":{"_className":"ArtifactType","url":"http://s.opencalais.com/1/type/em/e/Person","name":"Person"},"name":"Rafael García Leiva","rawRelevance":0.155,"normalizedRelevance":0.3235908141962422},"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'po': {"text":"Pío","slug":"po","source":{"_className":"Entity","url":"http://d.opencalais.com/pershash-1/1e3797af-fc97-3709-9da3-38ca66b8539e","subjectURL":null,"type":{"_className":"ArtifactType","url":"http://s.opencalais.com/1/type/em/e/Person","name":"Person"},"name":"Pío","rawRelevance":0.109,"normalizedRelevance":0.22755741127348644},"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'presentacin-de-entropycs': {"text":"Presentación de Entropycs","slug":"presentacin-de-entropycs","source":{"_className":"Entity","url":"http://d.opencalais.com/pershash-1/d82da742-4f0b-3310-9bdf-50120abbaa76","subjectURL":null,"type":{"_className":"ArtifactType","url":"http://s.opencalais.com/1/type/em/e/Person","name":"Person"},"name":"Presentación de Entropycs","rawRelevance":0.155,"normalizedRelevance":0.3235908141962422},"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'enron-creditors-recovery-corp': {"text":"ENRON CREDITORS RECOVERY CORP.","slug":"enron-creditors-recovery-corp","source":{"_className":"Entity","url":"http://d.opencalais.com/er/company/ralg-tr1r/81eb7e94-8357-375d-a8e3-d04f09e95813","subjectURL":"http://d.opencalais.com/comphash-1/e1b8a0e7-cca0-32fb-b542-748ebdcf3ad7","type":{"_className":"ArtifactType","url":"http://s.opencalais.com/1/type/er/Company","name":"Company"},"name":"ENRON CREDITORS RECOVERY CORP.","rawRelevance":0.479,"normalizedRelevance":1},"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'environmental-protection-agency': {"text":"Environmental Protection Agency","slug":"environmental-protection-agency","source":{"_className":"Entity","url":"http://d.opencalais.com/genericHasher-1/f863f041-5b94-3d97-a9e1-9861afae21c8","subjectURL":null,"type":{"_className":"ArtifactType","url":"http://s.opencalais.com/1/type/em/e/Organization","name":"Organization"},"name":"Environmental Protection Agency","rawRelevance":0.211,"normalizedRelevance":0.4405010438413361},"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'facultad-de-ciencias-econmicas-de-la-ucm': {"text":"Facultad de Ciencias Económicas de la UCM","slug":"facultad-de-ciencias-econmicas-de-la-ucm","source":{"_className":"Entity","url":"http://d.opencalais.com/genericHasher-1/e9b7c30f-5c93-3c6b-a630-0caeebe9115a","subjectURL":null,"type":{"_className":"ArtifactType","url":"http://s.opencalais.com/1/type/em/e/Organization","name":"Organization"},"name":"Facultad de Ciencias Económicas de la UCM","rawRelevance":0.13,"normalizedRelevance":0.27139874739039666},"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'francisco-mauro': {"text":"Francisco Mauro","slug":"francisco-mauro","source":{"_className":"Entity","url":"http://d.opencalais.com/pershash-1/789c3ca2-1180-307a-88a2-9dea2dfc081d","subjectURL":null,"type":{"_className":"ArtifactType","url":"http://s.opencalais.com/1/type/em/e/Person","name":"Person"},"name":"Francisco Mauro","rawRelevance":0.155,"normalizedRelevance":0.3235908141962422},"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'carlos-ortega': {"text":"Carlos Ortega","slug":"carlos-ortega","source":{"_className":"Entity","url":"http://d.opencalais.com/pershash-1/16767bcb-5186-309e-b51b-ef49764f9f5b","subjectURL":null,"type":{"_className":"ArtifactType","url":"http://s.opencalais.com/1/type/em/e/Person","name":"Person"},"name":"Carlos Ortega","rawRelevance":0.155,"normalizedRelevance":0.3235908141962422},"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'carlos-gil-bellosta': {"text":"Carlos Gil Bellosta","slug":"carlos-gil-bellosta","source":{"_className":"Entity","url":"http://d.opencalais.com/pershash-1/285d9175-2bc6-385c-bef8-98cb2d2bca59","subjectURL":null,"type":{"_className":"ArtifactType","url":"http://s.opencalais.com/1/type/em/e/Person","name":"Person"},"name":"Carlos Gil Bellosta","rawRelevance":0.24,"normalizedRelevance":0.5010438413361169},"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'facultad-de-ciencias-de-la-uned': {"text":"Facultad de Ciencias de la UNED","slug":"facultad-de-ciencias-de-la-uned","source":{"_className":"Entity","url":"http://d.opencalais.com/genericHasher-1/d70dbf27-cb59-3dbf-9af6-b89d8615e7ab","subjectURL":null,"type":{"_className":"ArtifactType","url":"http://s.opencalais.com/1/type/em/e/Organization","name":"Organization"},"name":"Facultad de Ciencias de la UNED","rawRelevance":0.13,"normalizedRelevance":0.27139874739039666},"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}, 'twitter-inc': {"text":"TWITTER INC.","slug":"twitter-inc","source":null,"bucketName":"current","bucketPlacement":"auto","_className":"Tag"}}	}
oc_commit_id:
  - http://blogs.cuartocanal.es/infotics/2013/04/02/como-hacer-analisis-de-redes-sociales-con-r-igraph-y-gephi/1364858350
categories:
  - cultura
  - data
  - evento
  - hacktivismo
  - LinkedData
  - LinkedOpenData
  - opendata
  - periodismo de datos
  - R
  - Sin categoría
  - social
  - softwarelibre
  - tecnología
  - web
tags:
  - Carlos Gil Bellosta
  - Carlos Ortega
  - Carlos Ortega Shiny
  - Colegio Argentino
  - Enron
  - ENRON CREDITORS RECOVERY CORP.
  - Environmental Protection Agency
  - Facultad de Ciencias de la UNED
  - Facultad de Ciencias Económicas de la UCM
  - Francisco Mauro
  - Gephi
  - Gregorio Serrano Los
  - Juan de Herrero
  - Martín Fierro
  - Pedro Concejero
  - Pío
  - Presentación de Entropycs
  - R de Madrid
  - Rafael García Leiva
  - twitter
  - TWITTER INC.
---
El [grupo de usuarios de R de Madrid][1] dedicará la [reunión][2] del jueves 4 de abril de 18 a 20h a [Cómo hacer análisis de redes sociales con R-igraph y Gephi][3]. Para ello se apoyarán en el [análisis guiado][4] de un subconjunto de correos de Enron y posteriormente se aclararán dudas o se incidirá en alguno de los pasos del análisis. Para aprovechar el taller, conviene llevar ordenador portátil que tenga instalado una versión reciente de R (preferiblemente 2.15.3), con las librerías [igraph][5] y twitteR -además de sus respectivas dependencias-, [Gephi][6] para visualizaciones de datos y haber descargado previamente el [conjunto de datos][7]. Recomiendan igualmente disponer de un USB de datos para copiar y/o repartir datos.  
<a href="http://i2.wp.com/blogs.cuartocanal.es/infotics/files/2013/04/Reunion-Grupo-Usuarios-de-R-de-Madrid-4-Abril-2013-V9.png" data-rel="lightbox-0" title=""><img class="alignnone  wp-image-728" alt="Reunion Grupo Usuarios de R de Madrid - 4-Abril-2013 - V9" src="http://i2.wp.com/blogs.cuartocanal.es/infotics/files/2013/04/Reunion-Grupo-Usuarios-de-R-de-Madrid-4-Abril-2013-V9.png?resize=576%2C432" data-recalc-dims="1" /></a>  
Ésta es la sexta reunión del grupo desde que comenzaron el 21 de marzo de 2012, y en este tiempo han tenido las siguientes charlas en sus talleres:

  * [Introducción al Análisis Cuantitativo de Estrategias de Trading con R][8]
  * [Las Matemáticas de Lego][9]
  * Optimización mediante Gramáticas Evolutivas. Aplicación a los Sistemas de Trading
  * [PCA con matrices sparse para clasificación automática de contenidos][10] (p.ej. películas)
  * [Pongamos que hablo&#8230; del aiRe de Madrid][11]
  * MicroDatosEs: un paquete para leer ficheros de microdatos públicos, por Carlos Gil Bellosta. Se trata de una versión extendida de la charla presentada en las IV Jornadas de Usuarios de R que incluirá ejemplos prácticos (en modo taller, de ser posible) sobre cómo trabajar con los datos de la última EPA. La presentación y el código estudiado pueden bajarse de este enlace.
  * Presentación de Entropycs &#8211; La plataforma de trading cuantitativo basada en R, por Rafael García Leiva
  * [PRo Evolution SocceR y los FueRa de SeRie][12], por Carlos Ortega
  * [Shiny][13], por <a href="https://vimeo.com/58727850?width=1080" data-rel="lightbox-video-0">Pedro Concejero</a>
  * [Identificación de modelos ARIMA con Shiny][14], por Gregorio Serrano
  * [Los 500,000 e-mails del escándalo financiero de ENRON][15], un <a href="https://vimeo.com/60791571?width=1080" data-rel="lightbox-video-1">análisis de Carlos Ortega</a>
  * <a href="https://vimeo.com/60996486?width=1080" data-rel="lightbox-video-2">Cartografía de recursos forestales</a> empleando [datos][16] [LiDAR][17] y R. Material, por Francisco Mauro. Para seguir la presentación utilizar los paquetes: rgdal, maptools, leaps, plotKML

Su lugar de reunión ha pasado por la Facultad de Ciencias Económicas de la [UCM][18], la [Tabacalera][19], Matadero y finalmente la Facultad de Ciencias de la UNED, C/ Senda del Rey, 9. Para llegar puedes ir desde el autobús 46: en la parada de Senda del Rey con Obispo Trejo, viniendo desde Gran Vía o Príncipe Pío; en la parada de Avenida de Séneca con Senda del Rey, viniendo desde Moncloa; autobús U: en la parada de Juan de Herrero con Martín Fierro (al lado del Colegio Argentino); autobús A: en la parada de Avenida de Séneca con Senda del Rey, bajando desde Moncloa; si se viene desde Somosaguas, la Avenida de Séneca con Martín Fierro; 160: en la parada de Avenida de Séneca con Senda del Rey, bajando desde Moncloa; si se viene desde Aravaca, la Avenida de Séneca con Martín Fierro.  
[osm_map lat=&#8221;40.436&#8243; long=&#8221;-3.734&#8243; zoom=&#8221;15&#8243; width=&#8221;600&#8243; height=&#8221;450&#8243; type=&#8221;Mapnik&#8221;]

 [1]: http://r-es.org/Grupo+de+Inter%C3%A9s+Local+de+Madrid+-+GIL+Madrid
 [2]: http://www.r-es.org/GILMadrid
 [3]: http://r-es.org/Grupo+de+Inter%C3%A9s+Local+de+Madrid+-+GIL+Madrid#Prevista_Jueves_4_de_Abril_de_2013
 [4]: http://en.wikipedia.org/wiki/Social_network_analysis
 [5]: http://igraph.sourceforge.net/igraphbook/index.html
 [6]: https://gephi.org/
 [7]: http://dl.dropbox.com/u/109745848/TallerSNA-GrupoR-2013-04-04.Rdata
 [8]: http://r-es.org/tiki-download_file.php?fileId=4
 [9]: http://prezi.com/zo2aqesvxomx/las-matematicas-de-lego-version-extendida/
 [10]: http://concejero.wdfiles.com/local--files/home/PCA_movies_matrices_sparse.ppt
 [11]: http://prezi.com/fipcfjen_fck/pongamos-que-hablo-del-aire-de-madrid/
 [12]: http://prezi.com/ycj5fhelvdll/pro-evolution-soccer-y-los-fuera-de-serie/
 [13]: http://www.slideshare.net/concejero/r-shinygrupousuariosrdef
 [14]: http://intecca.uned.es/portalavip/grabacion.php?ID_Sala=74977&ID_Grabacion=74968&hashData=a70cd192fe84d5461bba9dc8085797f5&paramsToCheck=SURfR3JhYmFjaW9uLElEX1NhbGEs
 [15]: http://prezi.com/gq9j-izoytf-/los-500000-correos-de-enron/
 [16]: http://dl.dropbox.com/u/34832597/R_es_Madrid.zip
 [17]: http://dl.dropbox.com/u/34832597/Ejemplos.zip
 [18]: http://www.ucm.es
 [19]: http://www.latabacalera.net