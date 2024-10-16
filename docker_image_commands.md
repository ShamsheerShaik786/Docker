# Important commands to work on Docker images
# 1. To pull a Docker Image: 
docker pull image_name
# 2. To search for a docker image: 
docker search image_name
# 3. To upload an image into docker hub: 
docker push image_name
# 4. To see the list of images that are downloaded: 
docker images or docker image ls
# 5. To get detailed info about a docker image:
docker image inspect image_name/image_id
# 6. To delete a docker image that is not linked to any container:
docker rmi image_name/image_id
# 7. To delete a image that is linked to a container: 
docker rmi -f image_name/image_id
# 8. To save the docker image as a tar file: 
docker save image_name
# 9. To untar this tar file and get image: 
docker load tarfile_name
# 10. To delete all image: 
docker system prune -af
# 11. To create a docker image from a dockerfile:
docker build -t image_name .
# 12. To create an image from a customised container:
docker commit container_id/container_name image_name