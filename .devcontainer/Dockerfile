FROM ubuntu:20.04

# Avoid warnings by switching to noninteractive
ENV DEBIAN_FRONTEND=noninteractive

# This will automatically accept all prompts during package installation
ARG DEBIAN_FRONTEND=noninteractive

# Update and install necessary tools
RUN apt-get update && \
    apt-get -y install build-essential git cmake pkg-config \
    libbz2-dev libxml2-dev libzip-dev libboost-all-dev \
    lua5.2 liblua5.2-dev libtbb-dev wget && \
    apt-get autoremove -y && \
    apt-get clean -y && \
    rm -rf /var/lib/apt/lists/*

# Switch back to dialog for any ad-hoc use of apt-get
ENV DEBIAN_FRONTEND=dialog
