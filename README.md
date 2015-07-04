# Esa onda
esaonda, 



Voy a empezar con un tutorial sobre como armar una ofina virtal, en el camino me voy a pelear con Docker, voy a conocer Coreos, trata de enteder sobre DNS, y proxys reversos con Nginx. teniendo como aliados, varios proyectos de codigo libre y abierto, como let's chat, onlyoffice, meteor, el famoso wordpress, etc, etc, etc.





###Instalando onlyoffice con docker
https://registry.hub.docker.com/u/onlyoffice/documentserver/

 Installing ONLYOFFICE Document Server integrated with Community and Mail Servers

ONLYOFFICE Document Server is a part of ONLYOFFICE Free Edition that comprises also Community Server and Mail Server. To install them, follow these easy steps:

 STEP 1: Install ONLYOFFICE Document Server.
```
sudo docker run -i -t -d  --name onlyoffice-document-server onlyoffice/documentserver
```
 STEP 2: Install ONLYOFFICE Mail Server.

 For the mail server correct work you need to specify its hostname 'yourdomain.com'. To learn more, refer to the ONLYOFFICE Mail Server documentation.
```
sudo docker run --privileged -i -t -d --name onlyoffice-mail-server -p 25:25 -p 143:143 -p 587:587 \
-h yourdomain.com onlyoffice/mailserver
```
 STEP 3: Install ONLYOFFICE Community Server
 
```
sudo docker run -i -t -d -p 80:80 -p 5222:5222 -p 443:443 \
--link onlyoffice-mail-server:mail_server \
--link onlyoffice-document-server:document_server \
onlyoffice/communityserver
```





