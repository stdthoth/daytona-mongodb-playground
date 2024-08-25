FROM mcr.microsoft.com/devcontainers/base:jammy

# Install MongoDB command line tools - though mongo-database-tools not available on arm64
ARG MONGO_TOOLS_VERSION=7.0
RUN  sudo apt-get install gnupg curl
RUN curl -fsSL https://www.mongodb.org/static/pgp/server-7.0.asc | \
   sudo gpg -o /usr/share/keyrings/mongodb-server-7.0.gpg \
   --dearmor
RUN echo "deb [ arch=amd64,arm64 signed-by=/usr/share/keyrings/mongodb-server-7.0.gpg ] https://repo.mongodb.org/apt/ubuntu jammy/mongodb-org/7.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-7.0.list
RUN sudo apt-get update && export DEBIAN_FRONTEND=noninteractive \
&& sudo apt-get install -y mongodb-org
RUN  sudo systemctl start mongod

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>

# [Optional] Uncomment if you want to install an sudo apt updateadditional version of node using nvm
# ARG EXTRA_NODE_VERSION=10software-properties-common gnupg apt-transport-https ca-certificates -ycurl -fsSL https://www.mongodb.org/static/pgp/server-7.0.asc | \
   