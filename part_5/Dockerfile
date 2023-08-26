FROM ubuntu

WORKDIR /home/

RUN apt update && apt install nginx gcc libfcgi-dev spawn-fcgi -y && rm -rf /var/lib/apt/lists

RUN useradd olugash

RUN  touch /var/run/nginx.pid && \
     chmod -R 777 /home/ /var/run/nginx.pid /var/log/nginx/ /var/lib/nginx/

USER olugash

COPY --chown=olugash server/server.c /home/

COPY --chown=olugash nginx/nginx.conf /etc/nginx/

COPY --chown=olugash start.sh /home/

ENTRYPOINT ["bash", "start.sh"]