# Start from the official Jenkins image
FROM jenkins/jenkins:lts

# Switch to the root user
USER root

# Install Docker inside the Jenkins container
RUN apt-get update && \
    apt-get install -y docker.io curl && \
    usermod -aG docker jenkins

# Install Node.js and npm
RUN curl -sL https://deb.nodesource.com/setup_18.x | bash - && \
    apt-get install -y nodejs


# Switch back to the jenkins user
USER jenkins

# Expose Jenkins ports
EXPOSE 8080 50000

# Install additional Jenkins plugins (optional)
# RUN /usr/local/bin/install-plugins.sh github docker-workflow pipeline-stage-view


# Set the entrypoint for Jenkins
ENTRYPOINT ["/usr/bin/tini", "--", "/usr/local/bin/jenkins.sh"]
