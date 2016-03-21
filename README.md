# blog.infotics.es

[Infotics](https://infotics.es) deja de ser un blog para convertirse en la web de Adolfo Antón Bravo.

El blog se traslada a [blog.infotics.es](http://blog.infotics.es). Esto ha supuesto algunos cambios y mejoras:

- Pasamos de Wordpress a Jekyll (leer más abajo).
- Las URLs antiguas se reescriben en Apache para que sigan respondiendo al dominio infotics.es y las nuevas se crean con *blog.infotics.es*
- En infotics.es hemos instalado un certificado digital que extenderemos a blog.infotics.es
- Las nuevas entradas se crean sin el permalink de la fecha, solo el título del post.

## Bienvenidx a Jekyll

Después de mucho tiempo haciendo pruebas y dejándolas a medias hemos completado esta primera etapa, que no la última, del paso del blog de un gestor de contenidos como Wordpress a un generador de contenido estático como Jekyll.

Han sido muchos y emocionantes años en Wordpress. Gracias a [http://cuartocanal.es](Cuarto Canal) y su infraestructura de [http://blogs.cuartocanal.es](blogs), *Infotics* ha sobrevivido como espacio de experimentación desde la comunicación de temáticas transversales a las tecnologías de la información y del conocimiento.

Han sido muchos los placeres saboreados con *Wordpress* y también muchos los sinsabores, los problemas con los plugins, la falta de acceso al servidor, el servicio de alojamiento que día sí y día también dejaba el blog fuera de servicio.

En la última y larga etapa, desde que practico con *Emacs* y su maravilloso *Org-mode*, utilizaba [https://github.com/punchagan/org2blog/](org2blog) para publicar directamente desde el archivo *.org* a *WP* a través de *XML-RPC*. *Org2blog* te permite gestionar varios blogs y además una vez que has publicado el contenido de esa manera, ese mismo contenido lo puedes modificar también en local.

Esa dinámica de trabajo creo que me acercaba cada vez más a *Jekyll*. Si he elegido éste y no otro de los muchos que hay y que he probado, como *Nikola*, por ejemplo, es porque en esta fase de publicación del sitio a través de *GitHub*, *Jekyll* parecía la opción más sencilla, a la vez que muy interesante por su soporte, *plugins*, etc., y también porque con alguno hay que practicar esta nueva filosofía de edición completa.

Aunque buena parte del contenido de *infotics.es* lo tenía disponible en *orgmode*, y por tanto lo podía exportar a *Markdown*, el *plugin* [https://github.com/benbalter/wordpress-to-jekyll-exporter](Wordpress to Jekyll Exporter) es una muy buena manera de descargarte todo el contenido del sitio *WP* y cargarla en el nuevo *Jekyll*.

De un alojamiento propio, ahora **blog.infotics.es** se encuentra alojado en [Github](https://github.com/flowsta/blog.infotics.es).

## El flujo de escritura

1. Para no perder las buenas costumbres, los artículos seguirán siendo escritos en *orgmode*.
2. Luego los exporto a *Markdown*
3. Los copio a la carpeta `posts`.
4. Incluyo la cabecera en *yaml*.
4. Actualizo el repositorio *git*
5. Se publican en [http://blog.infotics.es](blog.infotics.es)

(*Continuará*)
