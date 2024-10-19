# Usecase
#Create a volume "myvolume" and create files in it and create a centos container and mount the above volume into it /tmp folder and check the files.
# Create a volume 
docker volume create myvolume
# To check the location where the mounted the volume works
docker volume inspect myvolume
# Copy the path shown in "MountPoint" and cd to that Path
cd "MountPoint"
# Create few files here
touch file1 file2
# Create a centos container and mount the above volume into the tmp folder
docker run --name c1 -it -v myvolume:/tmp centos
# Change to tmp folder and check for the files
cd /tmp
ls
