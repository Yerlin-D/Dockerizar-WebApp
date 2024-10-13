# Usar la última versión de Ubuntu como imagen base
FROM ubuntu:latest

# Instalar el software necesario Nginx y Git
RUN apt-get update && apt-get install -y nginx git

# Verificar la instalación de Git
RUN git --version

# Remover archivos dentro
RUN rm -rf /usr/share/nginx/html/*

# Clonar el repositorio de la aplicación 2048 en el directorio de Nginx
RUN git clone https://github.com/josejuansanchez/2048 /tmp/2048

# Copiar archivos del folder temporal al de nginx
RUN cp -r /tmp/2048/* /usr/share/nginx/html/

# Exponer el puerto 80 para Nginx
EXPOSE 80

# Comando para iniciar Nginx
CMD ["nginx", "-g", "daemon off;"]