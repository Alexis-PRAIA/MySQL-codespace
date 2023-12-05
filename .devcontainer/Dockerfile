# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.195.0/containers/php/.devcontainer/base.Dockerfile
# [Choice] PHP version (use -bullseye variants on local arm64/Apple Silicon): 8, 8.0, 7, 7.4, 7.3, 8-bullseye, 8.0-bullseye, 7-bullseye, 7.4-bullseye, 7.3-bullseye, 8-buster, 8.0-buster, 7-buster, 7.4-buster, 7.3-buster
ARG VARIANT=7-bullseye
FROM mcr.microsoft.com/vscode/devcontainers/php:0-${VARIANT}

# [Choice] Node.js version: none, lts/*, 16, 14, 12, 10
ARG NODE_VERSION="none"
RUN if [ "${NODE_VERSION}" != "none" ]; then su vscode -c "umask 0002 && . /usr/local/share/nvm/nvm.sh && nvm install ${NODE_VERSION} 2>&1"; fi

# Use a base image with the desired version of MySQL client
FROM mysql:8.0

# Set environment variables for configuration
ENV MYSQL_HOST=localhost \
    MYSQL_PORT=3306 \
    MYSQL_USER=root \
    MYSQL_PASSWORD=secret

# Add labels for better maintainability
LABEL maintainer="Your Name <your.email@example.com>"

# Update package lists and install MySQL client
RUN apt-get update && apt-get install -y mysql-client

# Set the default command to run when the container starts
CMD ["mysql"]


# [Optional] Uncomment this line to install global node packages.
# RUN su vscode -c "source /usr/local/share/nvm/nvm.sh && npm install -g <your-package-here>" 2>&1
