# docker-compose-wordpress

Creamos un archivo docker-compose.yml para poder levantar un servidor MySQL y Wordpress. Dentro del archivo docker debemos escribir:
```
version: '3.1'

services:

  wordpress:
    image: wordpress
    restart: always
    ports:
      - 8080:80
    environment:
      WORDPRESS_DB_HOST: db
      WORDPRESS_DB_USER: exampleuser
      WORDPRESS_DB_PASSWORD: examplepass
      WORDPRESS_DB_NAME: exampledb

  db:
    image: mysql:5.7
    restart: always
    environment:
      MYSQL_DATABASE: exampledb
      MYSQL_USER: exampleuser
      MYSQL_PASSWORD: examplepass
      MYSQL_RANDOM_ROOT_PASSWORD: '1'
```

Accedemos a la carpeta usando la terminal, y mediante el siguiente comando descaragremos las imágenes de MySQL y Wordpress:
<img width="1080" alt="2022-05-19 (1)" src="https://user-images.githubusercontent.com/91556453/169323403-ee5b6afc-cd6b-4231-be35-6a3e02f87016.png">

Mediante la IP **http://localhost:8080/wp-admin/install.php** accedemos a las bases de datos:
<img width="1061" alt="image" src="https://user-images.githubusercontent.com/91556453/169324058-9e8d4c65-aff7-4f0f-b7ed-11ce28122441.png">
