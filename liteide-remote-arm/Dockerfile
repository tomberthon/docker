FROM tomberthon/vnc

# Set up dev env

USER root
RUN apt-get -y --no-install-recommends install g++ make qt4-dev-tools libqt4-dev libqt4-core libqt4-gui libqtwebkit-dev golang git

RUN mkdir /opt/liteide

WORKDIR /opt/liteide
RUN git clone https://github.com/visualfc/liteide.git

WORKDIR /opt/liteide/liteide/build
RUN ./update_pkg.sh
#RUN QTDIR=/usr ./build_linux.sh

# get lite ide and compile

USER vnc
