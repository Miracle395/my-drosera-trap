FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    curl wget git build-essential lz4 jq make gcc nano automake autoconf tmux htop \
    nvme-cli libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip \
    ca-certificates gnupg zstd software-properties-common libgbm1 pkg-config \
    docker.io docker-compose iptables ufw

# Add docker permissions
RUN groupadd docker && usermod -aG docker vscode

# Install Foundry
RUN curl -L https://foundry.paradigm.xyz | bash && \
    echo 'source ~/.bashrc && foundryup' >> /home/vscode/.bashrc

# Install Bun
RUN curl -fsSL https://bun.sh/install | bash

# Install Drosera CLI
RUN curl -L https://app.drosera.io/install | bash

# Set env
ENV PATH="/home/vscode/.bun/bin:$PATH"
