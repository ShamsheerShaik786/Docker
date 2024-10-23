# UseCase1
# Create a dockerfile from ubuntu base image and install git in it
# 1 Create dockerfile
  vim dockerfile
  FROM ubuntu
  MAINTAINER Shamsheer
  RUN apt-get update
  RUN apt-get install -y git

# 2 Create an image from the above file
  docker build -t myubuntu .

# 3 Check if the new image is created
  docker images

# 4 Create a container from the new image and it should have git installed
  docker run --name u1 -it myubuntu
  git --version
