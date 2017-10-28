FROM registry.fedoraproject.org/fedora:26

ENV NAME=planet.projectatomic.io VERSION=0 RELEASE=1 ARCH=x86_64
RUN dnf install planet -y && dnf clean all

LABEL com.redhat.component="planet" \
      name="$FGC/$NAME" \
      version="$VERSION" \
      release="$RELEASE.$DISTTAG" \
      maintainer="Josh Berkus <josh@berkus.org>" \
      architecture="$ARCH" \
      summary="Container to run planet hourly in order to update planet.projectatomic.io" \
      usage="docker run -v " \
      url="https://github.com/projectatomic/planet.projectatomic.io"

COPY runplanet.sh /
COPY templates /
VOLUME /www-share/

COMMAND ["/usr/bin/bash /runplanet.sh"]
