# Usecase
# Create 3 centos containers c1,c2,c3. Mount /data as a volume on c1 container, c2 should use the volume used by c1 and c3 should use the volume used by c2
# Create a centos container c1 and mount /data 
docker run --name c2 -it -v /data centos
# Go into the data folder create files in data folder
cd data
touch f1 f2
# Come out of the container without exit
ctlr+p,ctlr+q
# Create another centos container c2 and it should used the voluems used by c1
docker run --name c2 -it --volumes-from c1 centos  
# In the c2 container go into data folder and create some file
cd data
touch f3 f4
# Come out of the container without exit
ctlr+p,ctlr+q
# Create another centos container c3 and it should use the volume used by c2
docker run --name c3 -it --volumes-from c2 centos
# In the c3 container go into data folder and create some file
cd data
touch f5 f6
# Come out of the container without exit
ctlr+p,ctlr+q
# Go into any of the 3 contianers and we will see all the files
docker attach c1
cd /data
ls
exit
# Identify the location the where the mounted data is stored
docker inspect c1
Search for "Mounts" section and copy the "Source" path
# Delete all containers
docker rm -f c1 c2 c3
# Check if the files are still present
cd "source_path"
