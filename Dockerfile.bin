FROM alpine:3.7

ENV USE_HELM_VERSION v2.8.2

RUN apk add --no-cache --virtual build-dependencies curl && \
    mkdir -p /tmp/helm && \
    curl https://storage.googleapis.com/kubernetes-helm/helm-${USE_HELM_VERSION}-linux-amd64.tar.gz | \
      tar -xzv -C /tmp/helm && \
    mv /tmp/helm/linux-amd64/helm /usr/bin/helm && \
    rm -rf /tmp/helm && \
    apk del build-dependencies

ENTRYPOINT ["/usr/bin/helm"]

