FROM debian:jessie

# xhost +local:
# xhost +si:localuser:root
# docker run -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=unix$DISPLAY --device /dev/snd --device /dev/dri viber

RUN dpkg --add-architecture i386 && \
    apt-get update && \
    apt-get upgrade -yq && \
    apt-get install -yq \
        wget:amd64 && \


    cd /tmp && \
    wget https://download.skype.com/linux/skype-debian_4.3.0.37-1_i386.deb && \
    dpkg -i --force-all /tmp/skype-debian_4.3.0.37-1_i386.deb && \
    apt-get install -yf && \


    apt-get clean -y && \
    apt-get autoclean -y && \
    apt-get autoremove -y && \
    rm -rf /tmp/* /var/tmp/* && \
    rm -rf /usr/share/locale/* && \
    rm -rf /var/cache/debconf/*-old && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /usr/share/doc/*