# 1 Create a dockerfile from ubuntu baseimage and make if behave like jenkins
  vim dockerfile
  FROM ubuntu
  MAINTAINER intelliqit
  RUN apt-get update
  RUN apt-get install -y openjdk-11-jdk
  ADD https://get.jenkins.io/war-stable/2.426.2/jenkins.war /
  ENTRYPOINT  ["java","-jar","jenkins.war"]

# 2 Create an image
  docker build -t myubuntu .

# 3 Create a container
  docker run  --name u1 -it myubuntu
  the container behaves like jenkins