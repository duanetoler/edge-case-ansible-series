# set base image (host OS)
FROM python:3.11

# set the working directory in the container
WORKDIR /home/ansible

# set list of packages to be installed
ENV pip_packages="ansible"

# copy the dependencies file to the working directory
COPY Pipfile Pipfile.lock /home/ansible

# install dependencies
RUN apt-get update
RUN apt-get install sshpass
RUN apt-get install -y jq
RUN pip install --upgrade pip setuptools
RUN pip install $pip_packages
RUN ansible-galaxy collection install -U check_point.mgmt check_point.gaia
RUN pip install pipenv
RUN pipenv install
RUN pipenv install --system
