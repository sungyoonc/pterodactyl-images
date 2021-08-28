FROM        --platform=linux/arm64 debian:buster-slim

LABEL       author="winter" maintainer="winterolym@protonmail.com"

LABEL       org.opencontainers.image.source="https://github.com/winterolym/pterodactyl-images"
LABEL       org.opencontainers.image.licenses=MIT

RUN         apt update && apt upgrade -y \
						&& apt-get install -y curl ca-certificates openssl git tar sqlite fontconfig tzdata iproute2 \
						&& useradd -d /home/container -m container

USER        container
ENV         USER=container HOME=/home/container
ENV         DEBIAN_FRONTEND noninteractive

WORKDIR     /home/container

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
