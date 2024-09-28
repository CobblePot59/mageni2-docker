FROM ubuntu:20.04

WORKDIR /var/www/html

ARG MAGENI_USERNAME
ARG MAGENI_EMAIL
ARG MAGENI_PASSWORD

RUN apt-get update >/dev/null 2>/dev/null && \
    apt-get -yq --no-install-recommends install supervisor curl sudo netcat net-tools >/dev/null 2>&1

COPY install /tmp/install

RUN sed 's/MAGENI_USERNAME/$MAGENI_USERNAME/g' -i /tmp/install && \
    sed 's/MAGENI_EMAIL/$MAGENI_EMAIL/g' -i /tmp/install && \
    sed 's/MAGENI_PASSWORD/$MAGENI_PASSWORD/g' -i /tmp/install && \
    chmod u+x /tmp/install && \
    /tmp/install && \
    rm /tmp/install && \
    rm -rf /var/lib/apt/lists/* && \
    apt-get clean && \
    apt-get autoclean >/dev/null 2>&1

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

EXPOSE 443
CMD ["/usr/bin/supervisord"]
