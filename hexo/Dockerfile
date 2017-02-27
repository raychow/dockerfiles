FROM node:latest
LABEL maintainer="Ray Chow <raychow.info@gmail.com>"

ENV TINI_VERSION v0.14.0
ADD https://github.com/krallin/tini/releases/download/${TINI_VERSION}/tini /tini
RUN chmod +x /tini

RUN npm i -g hexo-cli && npm cache clean

WORKDIR /hexo

CMD ["/tini", "--", "hexo", "g", "-w"]
