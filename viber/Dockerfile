FROM debian:jessie

# xhost +local:
# xhost +si:localuser:root
# docker run -v /tmp/.X11-unix:/tmp/.X11-unix -e DISPLAY=unix$DISPLAY --device /dev/snd --device /dev/dri viber

RUN apt-get update && \
    apt-get upgrade -yq && \
    apt-get install -yq \
        wget \
        libgstreamer-plugins-base0.10-0 \
        libgstreamer0.10-0 \
        libsqlite3-0 \
        libxcomposite1 \
        libxml2 \
        libxslt1.1 \
        libc6 \
        libdrm2 \
        libffi6 \
        libgcc1 \
        libgl1-mesa-glx \
        libgl1-mesa-dri \
        libglapi-mesa \
        libglib2.0-0 \
        libpcre3 \
        libstdc++6 \
        libx11-6 \
        libx11-xcb1 \
        libxau6 \
        libxcb1 \
        libxcb-dri2-0 \
        libxcb-dri3-0 \
        libxcb-glx0 \
        libxcb-present0 \
        libxcb-sync1 \
        libxdamage1 \
        libxdmcp6 \
        libxext6 \
        libxfixes3 \
        libxrender1 \
        libxshmfence1 \
        libxxf86vm1 \
        zlib1g \
        libfontconfig1 \
        libharfbuzz-bin \
        libxrandr2 \
        qt5-default && \


    cd /tmp && \
    wget http://download.cdn.viber.com/cdn/desktop/Linux/viber.deb && \
    dpkg -i --force-all /tmp/viber.deb && \
    apt-get install -yf && \
    chmod +x /opt/viber/Viber && \


    apt-get clean -y && \
    apt-get autoclean -y && \
    apt-get autoremove -y && \
    rm -rf /tmp/* /var/tmp/* && \
    rm -rf /usr/share/locale/* && \
    rm -rf /var/cache/debconf/*-old && \
    rm -rf /var/lib/apt/lists/* && \
    rm -rf /usr/share/doc/*

# CMD cd /opt/viber && ./Viber