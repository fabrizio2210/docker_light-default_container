FROM debian
ENV DOCKERVERSION=19.03.1
ENV DOCKERARCH=x86_64

RUN apt-get update && \
    apt-get install -y curl git ssh \
    && apt-get clean

# install docker client
RUN curl -fsSLO https://download.docker.com/linux/static/stable/${DOCKERARCH}/docker-${DOCKERVERSION}.tgz \
    && tar xzvf docker-${DOCKERVERSION}.tgz --strip 1 -C /usr/local/bin docker/docker \
    && rm docker-${DOCKERVERSION}.tgz


WORKDIR /usr/local/bin/
