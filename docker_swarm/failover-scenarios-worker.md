# Create httpd with 6 replicas and delete one replica running on the manager. Check if all 6 replicas are still running
# Drain Worker1 from the docker swarm and check if all 6 replicas are running on Manager and Worker2,make Worker1 rejoin the swarm
# Make Worker2 leave the swarm and check if all the 6 replicas are running on Manager and Worker1

# 1 Create httpd with 6 replicas
  docker service create  --name webserver -p 8888:80 --replicas 6 httpd

# 2 Check the replicas running on Manager
  docker service ps webserver | grep Manager

# 3 Check the container id
  docker container ls

# 4 Delete a replica
  docker rm -f container_id_from_step3

# 5 Check if all 6 replicas are running
  docker service ps webserver

# 6 Drain Worker1 from the swarm
  docker node update --availability drain Worker1

# 7 Check if all 6 replicas are still running on Manager and Worker2
  docker service ps webserver

# 8 Make Worker1 rejoin the swarm
  docker node update --availability active Worker1

# 9 Make Worker2 leave the swarm
  Connect to Worker2 using git bash
  docker swarm leave
  Connect to Manager
  
# 10 Check if all 6 replicas are still running
  docker service ps webserver
