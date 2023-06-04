FROM balenalib/armv7hf-debian
ENV DOCKERVERSION=24.0.2
ENV DOCKERARCH=armhf


RUN [ "cross-build-start" ]
RUN apt-get update && \
    apt-get install -y curl git ssh \
    && apt-get clean

# install docker client
RUN curl -fsSLO https://download.docker.com/linux/static/stable/${DOCKERARCH}/docker-${DOCKERVERSION}.tgz \
    && tar xzvf docker-${DOCKERVERSION}.tgz --strip 1 -C /usr/local/bin docker/docker \
    && rm docker-${DOCKERVERSION}.tgz

RUN curl -L "https://github.com/docker/compose/releases/download/v2.2.1/docker-compose-linux-armv7" \
    -o /usr/local/bin/docker-compose \
    && chmod +x /usr/local/bin/docker-compose

RUN [ "cross-build-end" ]

WORKDIR /usr/local/bin/
