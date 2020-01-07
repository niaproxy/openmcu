FROM debian:buster-slim

# name image: videoswitch/debian_base:buster
# Install dependenties

RUN echo "deb http://www.deb-multimedia.org buster main non-free" >> /etc/apt/sources.list \
 && echo "deb-src http://www.deb-multimedia.org buster main non-free" >> /etc/apt/sources.list \
 && apt update --allow-insecure-repositories \
 && apt install --allow-unauthenticated -y deb-multimedia-keyring \
 && apt update \
 && apt install -y locales tzdata gnupg2 procps \
 && echo "Europe/Moscow" > /etc/timezone  \
 && dpkg-reconfigure -f noninteractive tzdata \
 && sed -i -e 's/# en_US.UTF-8 UTF-8/en_US.UTF-8 UTF-8/' /etc/locale.gen \
 && locale-gen \
 && DEBIAN_FRONTEND=noninteractive apt install -y build-essential flex bison yasm pkg-config autoconf automake pkg-config git \
 libmp3lame-dev libvorbis-dev libtheora-dev libspeex-dev libfaac-dev libx264-dev \
 libfreetype6-dev libvpx-dev libx264-dev libavcodec-dev libavutil-dev libsofia-sip-ua-dev \
 libsamplerate0-dev libopus-dev libssl-dev libtool libjpeg62-turbo-dev libswscale-dev libavcodec58 libavformat-dev ffmpeg \
 && rm -rf /var/cache/apt/* \
 && rm -rf /var/lib/apt/lists/* \
 && rm -rf /tmp/*
