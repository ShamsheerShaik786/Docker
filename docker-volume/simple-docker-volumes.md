# UsedCase
# Create a directory /data and mount it as a volume on an ubuntu container and create some files in the mounted volumes and check if the files are preserved on the host machine even after the container is deleted
# Create /data directory
mkdir /data
# Create an ubuntu container and mount the above directory as volume
docker run --name u1 -it -v /data ubuntu
# In the container u1 go into /data directory and create some files
cd /data
touch file1 file2 file3
exit
# Identify the location where the mounted data is preserved
docker inspect u1
Search for "Mounts" section and copy the "Source" path
# Delete the container
docker rm -f u1
# check if the data is still present 
cd "source_path"
ls
