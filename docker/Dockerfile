FROM node:22-slim

LABEL org.opencontainers.image.source="https://github.com/dbgate/dbgate"
ENV http_proxy=http://172.18.8.60:7890
ENV https_proxy=http://172.18.8.60:7890
RUN apt-get update && apt-get install -y \
    ca-certificates \
    iputils-ping \
    iproute2 \
    unixodbc \
 && rm -rf /var/lib/apt/lists/*

WORKDIR /home/dbgate-docker

COPY . .

RUN ["chmod", "+x", "/home/dbgate-docker/entrypoint.sh"]

WORKDIR /home/dbgate-docker
EXPOSE 3000
VOLUME /root/.dbgate

CMD ["/home/dbgate-docker/entrypoint.sh"]
