# Start with a base Python 2.7.8 image
FROM python:2.7.8

MAINTAINER Juan L. Negron <jnegron11@bloomberg.net>

# Add the licenses for third party software and libraries
ADD licenses /licenses

# Add pip.conf
ADD pip.conf /etc/pip.conf
ADD pip.conf ~/.pip/pip.conf

# Reflect new pip config file
ENV PIP_CONFIG_FILE /etc/pip.conf

# Add the external tasks directory into /tasks
ADD locust-tasks /locust-tasks

# Install the required dependencies via pip
RUN pip install -r /locust-tasks/requirements.txt

# Expose the required Locust ports
EXPOSE 5557 5558 8089

# Set script to be executable
RUN chmod 755 /locust-tasks/run.sh

# Start Locust using LOCUS_OPTS environment variable
ENTRYPOINT ["/locust-tasks/run.sh"] 
