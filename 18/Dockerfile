FROM        openjdk:18-slim

LABEL       author="Nils van Lück" maintainer="n.vanlueck@techkings.de"

RUN apt-get update -y \
  && apt-get install -y curl ca-certificates openssl git tar sqlite fontconfig tzdata iproute2 \
  && useradd -d /home/container -m container

USER container
ENV  USER=container HOME=/home/container

USER        container
ENV         USER=container HOME=/home/container

WORKDIR     /home/container

COPY        ./entrypoint.sh /entrypoint.sh

CMD         ["/bin/bash", "/entrypoint.sh"]