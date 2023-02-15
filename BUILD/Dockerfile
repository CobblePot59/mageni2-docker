FROM ubuntu:20.04


RUN apt-get update >/dev/null 2>/dev/null && \
    apt-get -yq --no-install-recommends install supervisor curl sudo netcat net-tools >/dev/null 2>/dev/null

COPY install /tmp/install

RUN chmod u+x /tmp/install && \
    /tmp/install && \
    rm /tmp/install && \
    apt-get clean && \
    apt-get autoclean >/dev/null 2>/dev/null

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 443
CMD ["/usr/bin/supervisord"]
