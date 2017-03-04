FROM node:alpine
LABEL maintainer="Ray Chow <raychow.info@gmail.com>"

RUN apk -U add tini && \
  npm i -g hexo-cli && npm cache clean

WORKDIR /hexo

CMD ["/tini", "--", "hexo", "g", "-w"]
