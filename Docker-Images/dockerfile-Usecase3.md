# Create a dockerfile from ubunt base image and downlaod jenkins.warinto it

# 1 Create a dockerfile
  vim dockerfile
  FROM ubuntu
  MAINTIANER shamsheer
  ADD https://get.jenkins.io/war-stable/2.263.4/jenkins.war  /

# 2 Create an image from the above dockerfile
  docker build -t myjenkins .

# 3 Create a container from this image
  docker run --name u1 -it myjenkins
 
# 4 Check if jenkins.war is present
  ls
