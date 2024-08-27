FROM mcr.microsoft.com/devcontainers/base:focal

RUN  sudo apt-get install -y gnupg wget curl
RUN wget -qO - https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -
RUN echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list
RUN sudo apt-get update && export DEBIAN_FRONTEND=noninteractive \
&& sudo apt-get install -y mongodb-org
