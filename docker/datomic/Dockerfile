FROM eclipse-temurin:17-jre

ARG DATOMIC_VERSION=1.0.7482
ARG DATOMIC_DOWNLOAD_URL="https://datomic-pro-downloads.s3.amazonaws.com/${DATOMIC_VERSION}/datomic-pro-${DATOMIC_VERSION}.zip"

RUN apt-get update \
  && apt-get install -y --no-install-recommends curl unzip \
  && rm -rf /var/lib/apt/lists/*

RUN curl -fsSL "${DATOMIC_DOWNLOAD_URL}" -o /tmp/datomic.zip \
  && unzip /tmp/datomic.zip -d /opt \
  && mv "/opt/datomic-pro-${DATOMIC_VERSION}" /opt/datomic \
  && rm /tmp/datomic.zip

COPY transactor.properties /opt/datomic/transactor.properties

WORKDIR /opt/datomic

EXPOSE 4334 4335 4336

CMD ["bin/transactor", "/opt/datomic/transactor.properties"]
