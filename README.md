# Esa onda
esaonda, 



Voy a empezar con un tutorial sobre como armar una ofina virtal, en el camino me voy a pelear con Docker, voy a conocer Coreos, trata de enteder sobre DNS, y proxys reversos con Nginx. teniendo como aliados, varios proyectos de codigo libre y abierto, como let's chat, onlyoffice, meteor, el famoso wordpress, etc, etc, etc.


Primero creo na mauina virtual en azure con la version estable de CoreOS abriendo los puertos 22 , 80 y 443.

Me logueo atravez de ssh y traigo la version de bitnami de nginx con docker

` docker pull bitnami/nginx:latest `
 
 y lo mapeo para trabajar directamente sobre el 

` docker run -p 80:80 -p 443:443 bitnami/nginx `

*ref: https://github.com/bitnami/bitnami-docker-nginx*

