FROM alpine:3.9

ENV WORKERS "10"
ENV PORT "1080"

RUN set -x \
  # Runtime dependencies
  && apk --no-cache add \
    bash apg \
  && apk add dante dante-server --update-cache --repository http://dl-3.alpinelinux.org/alpine/edge/testing/ --allow-untrusted \
  && rm -rf /var/cache/apk/* /tmp/*

ADD files /
ADD entrypoint.sh /entrypoint.sh

EXPOSE ${PORT}

CMD /entrypoint.sh sockd