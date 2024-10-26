# Create a docekerfile from nginx base image and expose 90 port
# 1 vim dockerfile
  FROM nginx
  MAINTAIENR shamsheer
  EXPOSE 90

# 2 Create an image from the above file
  docker build -t mynginx .

# 3 Create a container from the above image
  docker run --name n1 -d -P mynginx

# 4 To check the port
  docker port n1
