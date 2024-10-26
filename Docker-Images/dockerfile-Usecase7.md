# Create a dockerfile from ubuntu base image and make it behave like nginx

# 1 Create a dockerfile
  vim dockerfile
  FROM ubuntu
  MAINTAINER shamsheer
  RUN apt-get update
  RUN apt-get install -y nginx
  ENTRYPOINT ["/usr/sbin/nginx","-g","daemon off;"]
  EXPOSE 80

# 2 Create an image from the above dockerfile
  docker build -t myubuntu .

# 3 Create a container from the above image and it will work like nginx
  docker run --name n1 -d -P myubuntu

# 4 Check the ports used by nginx
  docker container ls

# 5 To access nignx from browser
  public_ip_of_dockerhost:port_no_captured_from_step4
