# Use a base image with Ansible installed
FROM python:3.9-slim
LABEL MAINTAINER="Vivek Bangare <vivek.bangare@gmail.com>"
LABEL description="Containerized Ansible Script"

# Set the working directory in the container
WORKDIR /ansible

# Copy the ansible scripts and playbook files to the container
COPY . /ansible

# Upgrade pip and install Ansible
RUN pip install --no-cache-dir --upgrade pip ansible 

# Set the entry point command to run the ansible playbook with verbose output
ENTRYPOINT ["ansible-playbook", "-i inventory.ini"]
CMD [ "main.yaml" ]
