FROM ubuntu:20.04

# Avoid warnings by switching to noninteractive
ENV DEBIAN_FRONTEND=noninteractive

# This will automatically accept all prompts during package installation
ARG DEBIAN_FRONTEND=noninteractive

# Update and install necessary tools
RUN apt-get update && \
    apt-get -y install --no-install-recommends build-essential git pkg-config \
    libbz2-dev libxml2-dev libzip-dev libboost-all-dev \
    lua5.2 liblua5.2-dev libtbb-dev wget unzip && \
    apt-get autoremove -y && \
    apt-get clean -y && \
    rm -rf /var/lib/apt/lists/*

# Manually install a more recent version of CMake
RUN wget https://github.com/Kitware/CMake/releases/download/v3.21.1/cmake-3.21.1-linux-x86_64.sh && \
    chmod +x cmake-3.21.1-linux-x86_64.sh && \
    ./cmake-3.21.1-linux-x86_64.sh --skip-license --prefix=/usr/local

# Switch back to dialog for any ad-hoc use of apt-get
ENV DEBIAN_FRONTEND=dialog
