#--------------------------------------------------------
# My Dockerfilе: build Docker Image Nginx v.1
# Chuyan_Andrey 24.05
#--------------------------------------------------------
# Базовая платформа для запуска Nginx
FROM ubuntu:18.04

RUN apt-get -y update && \
    apt-get install -y nginx 
    
RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/*
# Копируем файл конфигурации Nginx из локальной директории в контейнер
COPY configs/nginx.conf /etc/nginx/nginx.conf
# Копируем файлы сайта из лестницы внутрь контейнера
COPY site/index.html /usr/share/nginx/html/index.html
# Указываем Nginx запускаться на переднем плане (daemon off)
RUN echo "daemon off;" >> /etc/nginx/nginx.conf
# В индексном файле меняем первое вхождение nginx на docker-nginx
RUN sed -i "0,/nginx/s/nginx/docker-nginx/i" /usr/share/nginx/html/index.html
# Запускаем Nginx. CMD указывает, какую команду необходимо запустить, когда контейнер запущен.
CMD [ "nginx" ]