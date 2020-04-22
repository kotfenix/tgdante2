FROM alpine:3.11

ENV WORKERS "10"
ENV PORT "1080"

RUN set -x \
  # Runtime dependencies
  && apk --no-cache add \
    bash \
    apg \
    dumb-init\
  && apk add dante dante-server --no-cache --repository https://dl-3.alpinelinux.org/alpine/edge/community

ADD files /
ADD entrypoint.sh /entrypoint.sh

EXPOSE ${PORT}

ENTRYPOINT ["/usr/bin/dumb-init", "--"]
CMD ["/entrypoint.sh", "sockd"]
