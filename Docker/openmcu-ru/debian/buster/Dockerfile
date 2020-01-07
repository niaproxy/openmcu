FROM videoswitch/debian_base:buster

# name image: videoswitch/openmcu-ru
# Install dependenties

ENV MAKE_OPTS="-j 3" \
 PREFIX="/opt"

ENV PATH=${PREFIX}/bin:${PATH}

WORKDIR /tmp

RUN echo "--------VIDEOSWITCH INSTALL ---------" \
 && git clone git://github.com/muggot/openmcu.git ./openmcu-ru \
 && cd ./openmcu-ru \
 && ./autogen.sh \
 && ./configure --disable-openssl \
 && make \
 && make install \
 && rm -rf /tmp/*

EXPOSE 5060 5061 1420 1554 1720

CMD ["/opt/openmcu-ru/bin/openmcu-ru", "-x"]