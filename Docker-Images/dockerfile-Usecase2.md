# Create a dockerfile to create an ansible image
# 1 vim dockerfile
  FROM ubuntu
  RUN apt-get update
  RUN apt-get install -y software-properties-common
  RUN apt-get install -y ansible

# 2 Build an image
  docker build -t ansible .
  This container will have ansible installed in it
