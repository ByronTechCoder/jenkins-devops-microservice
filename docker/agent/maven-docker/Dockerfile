FROM maven:3.8.1-jdk-11

# Install docker CLI
USER root
RUN apt-get update \
  && apt-get install -y --no-install-recommends docker.io ca-certificates \
  && rm -rf /var/lib/apt/lists/*

# Ensure we run as root by default (agents often run as root inside Jenkins)
USER root

# Default command
CMD ["bash"]
