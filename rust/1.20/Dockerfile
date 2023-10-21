FROM rust:1.20-stretch

LABEL author="DpkgSoft"
LABEL org.opencontainers.image.source="https://github.com/dpkgsoft/pterodactyl-docker-images"
LABEL org.opencontainers.image.licenses=MIT

COPY ./../packages /packages

RUN xargs apt install -y --no-install-recommends < /packages
RUN adduser -D -h /home/container container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         ["/bin/bash", "/entrypoint.sh"]