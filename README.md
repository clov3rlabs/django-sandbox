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

1. Para Publicar, utiliza una directiva equivalente a esta para establecer la configuración a ambiente de producción

    $ export DJANGO_SETTINGS_MODULE=django_project.settings.production


2. Coloca tu favicon.ico en /static

3. Las imagenes (img), javascripts (js), hojas de estilos (css) y otros recursos estaticos del sitio, van en /static en sus correspondientes carpetas.

4. En /media se colocan los archivos subidos
