# UseCase
# Create an ubuntu container and install some s/w's in it. Save this container as an image and later create a new container from the newly created image. We will find all the s/w's that we installed.

# Create an ubuntu container
  docker run --name u1 -it ubuntu

# In the container update the apt repo and install s/w's
  apt-get update
  apt-get install -y git

# Check if git is installed or not
  git --version
  exit

# Save the customised container as an image
  docker commit u1 myubuntu

# Check if the new image is created or not
  docker images

# Delete the previousely create ubuntu container
  docker rm -f u1

# Create an new container from the above created image 
  docker run --name u1 -it myubuntu

# Check for git 
  git --version
