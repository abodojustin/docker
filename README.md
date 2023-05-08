# lab-3

Tâches:
> - Créez un volume de type volumes

``
docker volume create --name share
``
> - Créez deux conteneurs ubuntu (ubuntu1 et ubuntu2) et Montez le volume créé dans le repertoire /tmp de chacun des conteneurs ubuntu

``
docker run -it --name ubuntu1 -v share:/tmp -d ubuntu /bin/bash
``

``
docker run -it --name ubuntu2 -v share:/tmp -d ubuntu /bin/bash
``
> - Créez un fichier toto.txt dans le repertoire /tmp de ubuntu1 et verifier qu'il est bien présent dans /tmp de ubuntu2


> - Créez un conteneur apache dont le site internet affiché sera celui hébergé ici: https://github.com/diranetafen/static-website-example.git (utilisez un volume de type bind mount), n'oubliez pas de vérifier que le site est bien accéssible

``
docker run --name webserver -p 80:80 -d -v ${PWD}/static-website-example:/usr/local/apache2/htdocs/ httpd
``

``
docker logs webserver``