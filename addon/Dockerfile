ARG BUILD_VERSION=dev
FROM celsworth/lxp-bridge:${BUILD_VERSION} AS lxp-bridge

FROM ghcr.io/home-assistant/base:latest
COPY --from=lxp-bridge / /

RUN apk add --no-cache yq-go

COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
