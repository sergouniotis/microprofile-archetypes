FROM azul/zulu-openjdk-alpine:8

RUN apk add bash curl nss tree \
        && rm -rf /var/cache/apk/*

ARG APP_NAME

ENV APP_NAME ${APP_NAME}
ENV APP_HOME /opt/applications/${APP_NAME}
ENV APP_FILE ${APP_NAME}.jar

WORKDIR ${APP_HOME}

COPY target/${APP_FILE} ${APP_HOME}

EXPOSE 8080 9999

ADD scripts/run.sh /run.sh
CMD ["/bin/sh", "/run.sh"]
