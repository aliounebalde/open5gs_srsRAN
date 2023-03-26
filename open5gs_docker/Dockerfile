# Utilisez une image de base Ubuntu 20.04
FROM ubuntu:18.04
# Mettre à jour les paquets et installer les dépendances nécessaires
RUN apt-get update && \
apt-get install -y git build-essential libmnl-dev make g++ libsctp-dev lksctp-tools iproute2 \
libcurl4-gnutls-dev  libssl-dev libidn11-dev \
libmongoc-dev libbson-dev python3 python3-pip python3-setuptools python3-wheel \
python3-dev iproute2 curl wget

RUN wget -qO - https://www.mongodb.org/static/pgp/server-6.0.asc | apt-key add -

RUN echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0 multiverse"|tee /etc/apt/sources.list.d/mongodb-org-6.0.list
RUN apt update && \
apt install -y mongodb
RUN apt-get install -y software-properties-common && \
add-apt-repository ppa:open5gs/latest
RUN apt update && \
apt install -y open5gs
# Clonez Open5GS depuis le repo git
RUN curl -fsSL https://deb.nodesource.com/setup_14.x | bash -E
RUN apt-get install -y nodejs
RUN service mongodb start
#RUN curl -fsSL https://open5gs.org/open5gs/assets/webui/install | bash -E
#curl -fsSL https://open5gs.org/open5gs/assets/webui/install |-E bash -

# Exposer les ports nécessaires pour Open5GS
EXPOSE 2152/udp 80/tcp 443/tcp 3478/tcp 3478/udp 3000/tcp

