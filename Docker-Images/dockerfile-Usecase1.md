# Download docker shell script into the docker host and copy it into the customsied docker image and later install it at the time of creating the image
# 1 Download docker script
  curl -fsSL https://get.docker.com -o get-docker.sh

# 2 Create the dockerfile
  vim dockerfile
  FROM ubuntu
  MAINTIANER Shamsheer
  COPY get-docker.sh /
  RUN sh get-docker.sh

# 4 Create an image from the dockerfile
  docker build -t myubuntu .

# 5 Create a container from the above image
  docker run --name u1 -it myubuntu

# 6 Check if the get-docker.sh is present in / and also see if docker is installed
  docker --version
