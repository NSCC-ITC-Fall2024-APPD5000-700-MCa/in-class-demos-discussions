FROM mcr.microsoft.com/devcontainers/universal:latest
#FROM mcr.microsoft.com/devcontainers/javascript-node:latest

# Update to latest packages
RUN apt-get update && apt-get install -y && rm -rf /var/lib/apt/lists/*

# Install VS Code extensions
RUN mkdir --parents /opt/cs50/extensions && \
    cd /tmp && \
    git clone https://github.com/cs50/explain50.vsix.git && \
    cd explain50.vsix && \
    npm install && \
    npx vsce package && \
    mv explain50-1.0.0.vsix /opt/cs50/extensions && \
    cd /tmp && \
    rm --force --recursive explain50.vsix && \
    git clone https://github.com/cs50/ddb50.vsix.git && \
    cd ddb50.vsix && \
    npm install && \
    npx vsce package && \
    mv ddb50-2.0.0.vsix /opt/cs50/extensions && \
    cd /tmp && \
    rm --force --recursive ddb50.vsix && \
    git clone https://github.com/cs50/style50.vsix.git && \
    cd style50.vsix && \
    npm install && \
    npx vsce package && \
    mv style50-0.0.1.vsix /opt/cs50/extensions && \
    cd /tmp && \
    rm --force --recursive style50.vsix
