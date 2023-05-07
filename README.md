# lab-3

Tâches:
> - Créez un réseau docker de type bridge

``
docker network create --driver=bridge --subnet=192.168.2.0/24 sharednetwork
``
> - Listez les réseaux disponibles

``
docker network ls
``
> - Créez deux conteneurs ubuntu dans le réseau créé précédement

``
docker run -it --name ubuntu1 --network sharednetwork -d ubuntu /bin/bash
  145  docker run -it --name ubuntu2 --network sharednetwork -d ubuntu /bin/bash
``
> - Installer la commande ping et tentez de pinguer les conteneurs entre eux avec leur ip et par leur nom

``
ping ubuntu1
``

``
ping ubuntu2
``