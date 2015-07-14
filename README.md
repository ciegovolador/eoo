# Esa onda
esaonda, 



Voy a empezar con un tutorial sobre como armar una ofina virtal, en el camino me voy a pelear con Docker, voy a conocer Coreos, trata de enteder sobre DNS, y proxys reversos con Nginx. teniendo como aliados, varios proyectos de codigo libre y abierto, como let's chat, onlyoffice, meteor, el famoso wordpress, etc, etc, etc.


Primero creo na mauina virtual en azure con la version estable de CoreOS abriendo los puertos 22 , 80 y 443.

Me logueo atravez de ssh y traigo la version de bitnami de nginx con docker

` docker pull bitnami/nginx:latest `

luego creo una carpeta para menejar la configuracion del contenedor desde el host

` mkdir nginx `

y otra para aljar las aplicaciones 

` mkdir app `
 
 luego corro el contenedor, mapeando los puertos al exterior, dandole nombre y montando un voulmen para la configuracion mas otro para las aplicaciones,

esto se hace remplazado */path/to/* con el resultado del comando ` pwd ` 

` sudo docker run  -p 80:80 -p 443:44 --name nginx -v /home/mauro/nginx/conf:/bitnami/nginx/conf  -v /home/mauro/app:/app bitnami/nginx:1.8.0-4 `

entoces puedo ver la pagina de bienbenida de nginx desde el navegador en la direccion ip de la maquina virtual

el proximo paso es hacer un backup, por las dudas.

` sudo cp nginx/conf/nginx.conf nginx/conf/nginx.conf.$(date "+%b_%d_%Y_%H.%M.%S") `

y ahora si, a jugar

*ref: https://github.com/bitnami/bitnami-docker-nginx*

sudo docker run -it --rm -v "$(pwd)":/app danieldent/meteor meteor -p 80
