FROM resin/rpi-raspbian

RUN apt-get -y update
RUN apt-get -y upgrade

RUN apt-get install -y tightvncserver fluxbox sudo

RUN apt-get install -y xterm x11vnc

RUN useradd -ms /bin/bash vnc
RUN adduser vnc sudo

RUN echo 'vnc:12341234' | chpasswd


RUN mkdir /home/vnc/.vnc
ADD .vnc/passwd /home/vnc/.vnc/passwd
RUN chown -R vnc:vnc /home/vnc/.vnc
RUN chmod 700 /home/vnc/.vnc
RUN chmod 600 /home/vnc/.vnc/passwd

RUN mkdir /home/vnc/.fluxbox
ADD .fluxbox /home/vnc/.fluxbox
RUN chown -R vnc:vnc /home/vnc/.fluxbox

USER vnc
ENV USER vnc
ENV HOME /home/vnc
EXPOSE 5900

CMD vncserver :0 -geometry 1280x1024 -depth 24 -dpi 96 && \ 
    tail -F /home/vnc/.vnc/*.log
