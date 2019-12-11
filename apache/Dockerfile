#Indica a imagem a servir como base
FROM debian

#Lista de comandos que deseja executar na criação da imagem
RUN apt-get update && apt-get install -y apache2 && apt-get clean

#Define variáveis de ambiente
ENV APACHE_LOCK_DIR="/var/lock"
ENV APACHE_PID_FILE="/var/run/apache2.pid"
ENV APACHE_RUN_USER="www-data"
ENV APACHE_RUN_GROUP="www-data"
ENV APACHE_LOG_DIR="/var/log/apache2"

#Adiciona metadados à imagem, como descrição, versão e fabricante
LABEL description="Webserver"

#Define um volume a ser montado no container
VOLUME /var/www/html/

#Informa qual porta o container estará ouvindo
EXPOSE 80

#Configura o container para rodar um executável. 
#Quando esse executável for finalizado, o container também será
ENTRYPOINT [ "/usr/sbin/apachectl" ]

#Executa um comando, diferente do RUN que executa no build da imagem 
#O CMD executa quando o container for iniciado
CMD [ "-D", "FOREGROUND" ]