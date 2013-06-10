Plantilla de Proyecto para Django 1.5+

Instalación
===========

Para github
-----------

    django-admin.py startproject --template=https://github.com/clov3rlabs/django-sandbox/zipball/master --extension=py,rst,gitignore,example project_name

Para bitbucket
--------------

    django-admin.py startproject --template=https://bitbucket.org/clov3rlabs/django-sandbox/get/master.zip --extension=py,rst,gitignore,example project_name

Reemplaza el nombre *project_name* al final de la cadena por el del proyecto.

Instrucciones
=============

* Para Publicar, utiliza una directiva equivalente a esta para establecer la configuración a ambiente de producción

        export DJANGO_SETTINGS_MODULE={{ project_name }}.settings.production

* Coloca tu favicon.ico en /static

* Las imagenes (img), javascripts (js), hojas de estilos (css) y otros recursos estaticos del sitio, van en /static en sus correspondientes carpetas.

* En /media se colocan los archivos subidos

Configuración
=============

Apache
------

Recomendamos configuren apache de la siguiente manera.

    <VirtualHost *:80>
        ServerName  example.com
        ServerAlias www.example.com
        #ServerAlias www1.example.com

        DocumentRoot /path-to/project-root/public

        ErrorLog /path-to/project-root/logs/_error.log
        CustomLog /path-to/project-root/logs/_access.log combined

        Alias /assets /path-to/project-root/assets
        Alias /media /path-to/project-root/media

        WSGIDaemonProcess {{ project_name }} processes=2 maximum-requests=500 threads=15 display-name=%{GROUP} python-path=/path-to/project-root:/path-to-python/site-packages
        WSGIProcessGroup {{ project_name }}
        WSGIScriptAlias / /path-to/project-root/{{ project_name }}/wsgi.py

        <Directory /path-to/project-root/{{ project_name }}/assets>
            Order allow,deny
            Allow from all
        </Directory>
        <Directory /path-to/project-root/{{ project_name }}/media>
            Order allow,deny
            Allow from all
        </Directory>
        <Directory /path-to/project-root/{{ project_name }}>
            <Files wsgi.py>
                Order allow,deny
                Allow from all
            </Files>
        </Directory>
    </VirtualHost>

Reemplazar:

1. /path-to/project-root
2. /path-to-python
3. {{ project_name }}


Tecnologías
===========

- Bootstrap 2.3.2
- LESS 1.3.3
- Django 1.5
