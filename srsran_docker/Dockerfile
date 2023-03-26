# Utilisez une image de base Ubuntu 18.04
FROM ubuntu:18.04
# Mettre à jour les paquets et installer les dépendances nécessaires
RUN apt update
RUN apt install -y cmake libfftw3-dev libmbedtls-dev libboost-program-options-dev \
libconfig++-dev libsctp-dev libtool autoconf automake git libzmq3-dev
#Installer libzmq

RUN git clone https://github.com/zeromq/libzmq.git && \
cd libzmq && \
./autogen.sh && ./configure &&\
make && make install && ldconfig

#Installez czmq

RUN git clone https://github.com/zeromq/czmq.git
RUN cd czmq && ./autogen.sh && ./configure && make &&make install &&ldconfig
#RUN make && make install && ldconfig
RUN cd 
#installation SRSRAN
RUN git clone https://github.com/srsRAN/srsRAN.git
RUN cd srsRAN && \
mkdir build && cd build && \
cmake ../ && make
