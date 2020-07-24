#-------------------------------------------------------------------------------------------------------------
# Copyright (c) Microsoft Corporation. All rights reserved.
# Licensed under the MIT License. See https://go.microsoft.com/fwlink/?linkid=2090316 for license information.
#-------------------------------------------------------------------------------------------------------------

# To fully customize the contents of this image, use the following Dockerfile instead:
# https://github.com/microsoft/vscode-dev-containers/tree/v0.128.0/containers/javascript-node-14/.devcontainer/Dockerfile
FROM mcr.microsoft.com/vscode/devcontainers/javascript-node:0-14

# Wine needed to generate electron for windows
#
RUN apt-get update \
     && export DEBIAN_FRONTEND=noninteractive \
     && apt-get -y install --no-install-recommends wine

# Clean up
RUN apt-get clean && \
  apt-get autoclean && \
  rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* /var/cache/apt && \
  npm cache clean --force

# Install the electron packager
RUN npm install electron-packager -g