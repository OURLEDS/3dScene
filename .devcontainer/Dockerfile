# .devcontainer/Dockerfile

# Start from an official dev container image that already has a lot of C++ essentials.
# This base helps with dependencies like CMake, compilers, etc. You can pick a version you prefer.
FROM mcr.microsoft.com/vscode/devcontainers/cpp:0-ubuntu-20.04

# Install dependencies via apt
# - The base image includes some C++ packages, but we must explicitly add PCL, SDL2, etc.
USER root

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get install -y --no-install-recommends \
       libpcl-dev \
       libsdl2-dev \
       libeigen3-dev \
       libglew-dev \
       libassimp-dev \
       libboost-all-dev \
       libglm-dev \
    && rm -rf /var/lib/apt/lists/*

# ImGui v1.83 is not always available via apt. If you want the official source:
# Uncomment the lines below to clone and build ImGui from source if needed.
# (Often, many projects just include ImGui as part of their own project tree.)
# 
# RUN git clone https://github.com/ocornut/imgui.git /tmp/imgui \
#     && cd /tmp/imgui \
#     && git checkout v1.83
#   // Add any extra build steps or place the files within your project as needed

# Switch back to the vscode user
USER vscode
