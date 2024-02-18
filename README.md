# Instalar LAMP con dockers

### Para esta parte, lo que haré sera crear un dockerfile que me haga la imagen de Apache a mi medida. Despues con docker compose, iniciare un LAMP tomando mi propia imagen del Apache.

## Creo Dockerfile:
![img](img/df1.PNG)
![img](img/df2.PNG)

## Creo la carpeta src donde estara la info del sitio 
![img](img/df3creando_src.PNG)

## Creo el index.php dentro...
![img](img/df4index.PNG)

## También cree el conf de apache y lo meti en la carpeta /conf:
![img](img/Creo_conf_apache.PNG)

## Creare la imagen con `docker build - t`
![img](img/df5imagen.PNG)

## Creo la carpeta sql con la base de datos:
![img](img/df6creando_sql.PNG)

## Ahora, el archivo que creará el LAMP es el docker-compose.yml que queda asi:
![img](img/df8compose.PNG)

## Lanzo con `docker compose up -d`
![img](img/df9lanzando.PNG)

![img](img/Dockerps.PNG)

## Resultado...
![img](img/resultado.PNG)

## * Al final tuve un problema porque en el dockerfile no indiqué que copiase el contenido de /conf a sites-available del servidor...
### Esto hacía que no me llevase al index.php porque por defecto esta index.html

## Modifico el dockerfile...
![img](img/modifico_dockerfile.PNG)

### Creare una imagen con la etiqueta v2...
![img](img/creo_imagenv2.PNG)


## Solo falta modificar el compose para que use esa nueva imagen...
![img](img/modifico_compose_para_v2.PNG)

## Resultado...
![img](img/resultadov2.PNG)
