FROM mcr.microsoft.com/devcontainers/base:focal

ARG USERNAME=developer
ARG USER_UID=1001
ARG USER_GID=$USER_UID

RUN groupadd --gid $USER_GID $USERNAME \
	&& useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
	&& apt-get update \
	&& apt-get install -y sudo \
	&& echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
	&& chmod 0440 /etc/sudoers.d/$USERNAME

RUN  sudo apt-get install -y gnupg wget curl
RUN wget -qO - https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -
RUN echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list
RUN sudo apt-get update && export DEBIAN_FRONTEND=noninteractive \
&& sudo apt-get install -y mongodb-org

RUN (curl -sf -L https://download.daytona.io/daytona/install.sh | sudo bash) && daytona server -y && daytona