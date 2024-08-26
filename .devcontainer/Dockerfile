FROM mcr.microsoft.com/devcontainers/base:focal

# Install MongoDB command line tools - though mongo-database-tools not available on arm64

RUN  sudo apt-get install gnupg wget
RUN wget -qO - https://www.mongodb.org/static/pgp/server-4.4.asc | sudo apt-key add -
RUN echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/4.4 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-4.4.list
RUN sudo apt-get update && export DEBIAN_FRONTEND=noninteractive \
&& sudo apt-get install -y mongodb-org

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

# [Optional] Uncomment if you want to install an sudo apt updateadditional version of node using nvm
# ARG EXTRA_NODE_VERSION=10software-properties-common gnupg apt-transport-https ca-certificates -ycurl -fsSL https://www.mongodb.org/static/pgp/server-7.0.asc | \
   