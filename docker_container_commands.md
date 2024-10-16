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
# 14.  To create a docker container
docker run image_name/image_id
# run command options
--name:  USed to give a name to the container
--restart: Used to keep the container in runnign condition
-d: Used to run the container in detached mode in background
-it: Used to open interactive terminal in the container
-e: Used to pass environment varibales to the container
-v : Used to attach an external device or folder as a volume
--volumes-from: Used to share volume between multiple containers
-p : Used for port mapping.It will link the container port with host port.
Eg: -p 8080:80 Here 8080 is host port(external port) and 80 is container port(internal port)
-P: Used for automatic port mapping where the container port is mapped with some host port that is greate than 30000
--link : Used to create a link between multiple containers to create a microservices architecture.
--network: Used to start a container on a specific network
-rm : Used to delete a container on exit
-m: Used to specify the upper limit on the amount of memeory that a container can use
-c: Used to specify the upper limit on the amout of cpu a container can use
-ip: Used to asssign an ip to the container
# 15. To see the ports used by a container
docker port container_id/container_name
# 16. To run any process in a container from outside the container
docker exec -it container_id/container_name process_name
Eg: To run the bash process in a container
docker exec -it container_id/container_name bash
# 17. To come out of a container without exit
ctrl+p,ctrl+q
# 18. To go back into a container from where the interactive terminal is running
docker attach container_id/container_name
# 19. To see the processes runnign in a container
docker container container_id/container_name top
