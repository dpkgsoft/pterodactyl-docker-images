FROM openjdk:22-bullseye

LABEL author="DpkgSoft"
LABEL org.opencontainers.image.source="https://github.com/dpkgsoft/pterodactyl-docker-images"
LABEL org.opencontainers.image.licenses=MIT

COPY ./../packages /packages

RUN apt update
RUN xargs apt install -y --no-install-recommends < /packages
RUN adduser -D -h /home/container container

USER        container
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./../entrypoint.sh /entrypoint.sh
CMD         ["/bin/bash", "/entrypoint.sh"]