Plantilla de Proyecto para Django 1.5+

Instalación
===========

Para github
-----------

    django-admin.py startproject --template=https://github.com/clov3rlabs/django-sandbox/zipball/master --extension=py,rst project_name

Para bitbucket
--------------

    django-admin.py startproject --template=https://bitbucket.org/clov3rlabs/django-sandbox/zipball/master --extension=py,rst project_name

Reemplaza el nombre *project_name* al final de la cadena por el del proyecto.

Instrucciones
=============

Para Publicar, utiliza una directiva equivalente a esta para establecer la configuración a ambiente de producción

    $ export DJANGO_SETTINGS_MODULE={{ project_name }}.settings.production

Coloca tu favicon.ico en /static

Las imagenes (img), javascripts (js), hojas de estilos (css) y otros recursos estaticos del sitio, van en /static en sus correspondientes carpetas.

En /media se colocan los archivos subidos
