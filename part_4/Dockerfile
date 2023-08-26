FROM nginx

COPY server/server.c /

RUN apt update && apt install gcc libfcgi-dev spawn-fcgi -y

COPY nginx/nginx.conf /etc/nginx/

COPY start.sh /

ENTRYPOINT ["bash", "start.sh"]