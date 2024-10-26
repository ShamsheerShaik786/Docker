# Create a docker image with a volume on an image 
# 1 Create a dockerfile
  vim dockerfile
  FROM ubuntu
  MAINTAINER intelliqit
  VOLUME /data

# 2 Create a image
  docker build -t myubuntu .

# 3 Create a container
  docker run --name u1 -it myubuntu
  cd data
  touch file1 file2
  exit

# 4 Delete container
  docker rm -f u1
Files will be available
