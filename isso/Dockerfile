# forked from https://hub.docker.com/r/wonderfall/isso/
FROM alpine:3.5
LABEL maintainer="Ray Chow <raychow.info@gmail.com>"

ARG ISSO_VER=0.10.6

RUN echo "@community https://nl.alpinelinux.org/alpine/v3.5/community" >> /etc/apk/repositories \
 && BUILD_DEPS=" \
    python-dev \
    libffi-dev \
    py2-pip \
    build-base" \
 && apk -U add \
    ${BUILD_DEPS} \
    python \
    py-setuptools \
    sqlite \
    libressl \
    ca-certificates \
    tini@community \
 && pip install --no-cache cffi \
 && pip install --no-cache misaka==1.0.2 \
 && pip install --no-cache "isso==${ISSO_VER}" \
 && apk del ${BUILD_DEPS} \
 && rm -rf /var/cache/apk/* /tmp/*

EXPOSE 8080

VOLUME /db /config

CMD ["/sbin/tini", "--", "isso", "-c", "/config/isso.conf", "run"]
