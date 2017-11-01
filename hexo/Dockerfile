FROM node:alpine
LABEL maintainer="Ray Chow <raychow.info@gmail.com>"

RUN apk -U add tini && \
  npm i -g --unsafe-perm hexo-cli && \
  npm cache clean --force && \
  rm -rf /var/cache/apk/* /tmp/*

WORKDIR /hexo

CMD ["/sbin/tini", "--", "hexo", "g", "-w"]
