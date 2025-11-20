FROM jenkins/jenkins:lts

# Switch to root to install packages
USER root

# Install docker CLI (docker.io) and clean up
RUN apt-get update \
  && apt-get install -y --no-install-recommends docker.io \
  && rm -rf /var/lib/apt/lists/*

# Add the jenkins user to the docker group (group created by docker.io package)
RUN usermod -aG docker jenkins || true

# Return to jenkins user
USER jenkins
