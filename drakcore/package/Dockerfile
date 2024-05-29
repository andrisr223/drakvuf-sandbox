ARG IMAGE
FROM $IMAGE

ENV DEBIAN_FRONTEND=noninteractive

#    if [ $(apt-cache search --names-only '^python3\.10$' | wc -l) -ne 0 ]; then apt-get install -y python3.10 python3.10-dev ; else apt-get install -y python3.7 python3.7-dev ; fi && \
# curl "http://snapshot.debian.org/archive/debian/20201029T084118Z/pool/main/d/dh-virtualenv/dh-virtualenv_1.2.1-1_all.deb" -o dh-virtualenv.deb && \

#     python3 -m pip install --break-system-packages pip && \

#     pip3 install --break-system-packages virtualenv==20.1.0 && \

#     curl -sL https://deb.nodesource.com/setup_14.x | bash - && \

RUN apt-get update && \
    apt-get install -y wget curl python3 python3-venv python3-pip debhelper devscripts lsb-release && \
    apt-get install -y python3.11 python3.11-dev && \
    curl "https://snapshot.debian.org/archive/debian/20240430T084606Z/pool/main/d/dh-virtualenv/dh-virtualenv_1.2.2-1.4_all.deb" -o dh-virtualenv.deb && \
    curl -fsSL https://deb.nodesource.com/setup_20.x | bash - && \
    apt-get install -y nodejs python3-virtualenv python3-pip && \
    dpkg -i --ignore-depends=sphinx-rtd-theme-common ./dh-virtualenv.deb

COPY drakcore /build
WORKDIR /build
