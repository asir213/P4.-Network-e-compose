# P4.-Network-e-compose

    Crear unha rede en docker
Para crear unha rede en docker poñemos o comando 
docker network create <nome da red>.

    Crear dous contenedores unidos a esa rede
Para crear dous contenedores nesa rede utilizaremos o comando
docker run -itd --name=<nome_do_contenedor> --network=<nome_da_network>

    Comprobar que os contenedores están na rede
Para comprobar que ambos contenedores estan na rede debemos facer o seguinte comando 
docker network inspect <nome da red>.

    Comprobar que os contenedores poden verse entre eles
Para saber se os contenedores se ven entre eles debemos hacer ping, para iso entraremos nunha terminal, facendo ping, se non o temos podemos descargar o paquete nettools,co comando docker exec -it <nome_do_contenedor> sh

    Listar os contenedores conectados á rede
Para listar os contenedores debemos poñer o comando docker network inspect <nome da red>.

    Listar as propiedades da rede
Para ver os detalles dunha rede utilizamos o comando anterior
docker network inspect <nome_da_rede>

    Crea outra rede
Para crear outra rede facemos o mesmo que no primeiro paso docker network create <nome da red>.

    Lanza dous contenedores novos conectados a esa nova rede
Para facer este apartado escribiremos o mesmo comando que no apartado 2 cambiando unicamente os nomes e a rede á que está conectada.
docker run -itd --name=<nome_do_contenedor> --network=<nome_da_network>

    Comproba as posibles conexións entre os 4 contenedores
Como os contenedores están en distintas redes 2 a 2, estes so poderan ver os contenedores que están na sua rede. Para saber se os contenedores se ven entre eles debemos hacer ping, para iso entraremos nunha terminal, facendo ping, se non o temos podemos descargar o paquete nettools,co comando:
docker exec -it <nome_do_contenedor> sh

    Docker compose:

    Segue os pasos da guía de iniciación de docker-compose, e explica coas túas palabras os pasos que segues e qué fan
O primeiro que faremos será descargar docker compose isto o faremos co comando
sudo apt install docker-compose

    Agora que sabes algo máis de docker-compose, crea un arquivo (ou varios arquivos) de configuración que ó ser lanzados cun docker-compose up, resulten nunha rede docker á que estean conectados 3 contenedores, explica os parámetros do .yaml usado

Os parametros do documento son os seguintes:

Versióm: versión de docker compose

Volumes : directorio nun directorio do contenedor

Image: neste caso empreguei nginx

Container_name: o nome que queremos do contenedor

Networks: redes as que están conectadas

ports: mapeo o porto

    Busca e proba 4 parámetros e configuracións diferentes que podes incluir no arquivo compose, explica qué fan. (por exemplo diferentes cousas que facer coa opción RUN)
    
Build: se queremos crear una imaxe

Restars: para configurar o reinicio automatico

Expose: o porto que poñamos queda exposto para outros contenedores pero sin que esté accesible dende o host

Privileged(true/false): da permisos ao contenedor, o que permite o acceso completo ao resto de host.