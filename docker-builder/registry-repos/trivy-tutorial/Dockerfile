#frase de prueba PR
FROM debian

ENV DEBIAN_FRONTEND noninteractive

# +---------------------------------------------------------+
# INSTALACIÓN A NIVEL DE SISTEMA MEDIANTE GESTOR DE PAQUETES
# +---------------------------------------------------------+

RUN apt-get update -y &&\
    apt-get dist-upgrade -y &&\
    apt-get install -y apache2 \
        wget \
	python3-pip\
#	libncursesw5-dev libssl-dev \
#	libsqlite3-dev tk-dev libgdbm-dev libc6-dev libbz2-dev libffi-dev zlib1g-dev \
        build-essential &&\
    apt-get autoremove &&\
    apt-get clean &&\
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

#RUN wget http://snapshot.debian.org/archive/debian/20130319T033933Z/pool/main/o/openssl/libssl1.0.0_1.0.1e-2_amd64.deb -O /tmp/libssl1.0.0_1.0.1e-2_amd64.deb && \
#    dpkg --ignore-depends=multiarch-support -i /tmp/libssl1.0.0_1.0.1e-2_amd64.deb

#RUN wget http://snapshot.debian.org/archive/debian/20130319T033933Z/pool/main/o/openssl/openssl_1.0.1e-2_amd64.deb -O /tmp/openssl_1.0.1e-2_amd64.deb &&\
#    dpkg --ignore-depends=multiarch-support -i /tmp/openssl_1.0.1e-2_amd64.deb


# +--------------------+
# INSTALACIÓN CON MAKE (Shellshock)
# (instalacióin a nivel de sistema SIN gestor de paquetes)
# +--------------------+

RUN wget https://ftp.gnu.org/gnu/bash/bash-4.3.tar.gz && \
    tar zxvf bash-4.3.tar.gz && \
    cd bash-4.3 && \
    ./configure && \
    make && \
    make install

# +------------------------------------------------------------------------+
# INSTALACIÓN A NIVEL DE APLICACIÓN MEDIANTE GESTOR DE PAQUETES (regex DoS)
# +------------------------------------------------------------------------+

#COPY lang_dependencies/Pipfile.lock /app/Pipfile.lock

RUN pip3 install httplib2==0.18.1
