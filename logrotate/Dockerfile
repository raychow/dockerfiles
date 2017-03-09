FROM alpine:3.5
LABEL maintainer="Ray Chow <raychow.info@gmail.com>"

ADD logrotate.conf /logrotate/
ADD start.sh /logrotate/
RUN apk add -U --no-cache logrotate && \
  rm -rf /var/cache/apk/* && \
  chmod u+x /logrotate/start.sh

VOLUME /log

CMD ["/logrotate/start.sh"]
