FROM jenkins/jenkins:lts-jdk21

USER root

ARG COMPOSE_VERSION=v5.4.0

RUN apt-get update \
    && apt-get install -y --no-install-recommends docker-cli curl \
    && mkdir -p /usr/local/lib/docker/cli-plugins \
    && curl -fsSL \
       "https://github.com/docker/compose/releases/download/${COMPOSE_VERSION}/docker-compose-linux-x86_64" \
       -o /usr/local/lib/docker/cli-plugins/docker-compose \
    && chmod +x /usr/local/lib/docker/cli-plugins/docker-compose \
    && rm -rf /var/lib/apt/lists/*

USER jenkins
