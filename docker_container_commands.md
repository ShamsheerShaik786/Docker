# Working on Docker Containers
# 1. To see the list of running containers
docker container ls
# 2. To see the list of all containers (running and stopped)
docker ps -a
# 3. To start a container
docker start container_id/container_name
# 4. To stop a container
docker stop container_id/container_name
# 5. To restart a container
docker restart container_id/container_name
# 6. To restart after 10 seconds
docker restart -t 10 container_id/container_name
# 7. To delete a stopped container
docker rm container_id/container_name
# 8. To delete a running container
docker rm -f container_id/container_name
# 9. To stop all running container
docker stop $(docker ps -aq)
# 10. To delete all stopped containers
docker rm $(docker ps -aq)
# 11. To delete all running and stopped containers
docker rm -f $(docker ps -aq)
# 12. To get detailed info about a container
docker inspect container_id/container_name
# 13. To see the logs genearated by a container
docker logs container_id/container_name

