FROM videoswitch/debian_base:buster

# name image: videoswitch/openmcu-ru

WORKDIR /tmp

RUN git clone git://github.com/muggot/openmcu.git ./openmcu-ru \
 && cd ./openmcu-ru \
 && git checkout 4.1 \
 && ./autogen.sh \
 && ./configure --disable-openssl \
 && make -j 3 \
 && make install \
 && rm -rf /tmp/*

EXPOSE 5060 5061 1420 1554 1720

CMD ["/opt/openmcu-ru/bin/openmcu-ru", "-x"]