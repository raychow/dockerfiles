FROM almir/webhook
LABEL maintainer="Ray Chow <raychow.info@gmail.com>"

RUN apk add --update git && \
  rm -rf /var/cache/apk/*

COPY pull.sh /webhook/
RUN chmod u+x /webhook/pull.sh
