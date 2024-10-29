# Create nginx with 5 replicas and check where these replicas are running

# 1 Create nginx with 5 replicas
  docker service create --name webserver -p 8888:80 --replicas 5 nginx

# 2 To check the services running in swarm
  docker service ls

# 3 To check where these replicas are running
  docker service ps webserver

# 4 To access the nginx from browser
  public_ip_of_manager/worker1/worker2:8888

# 5 To delete the service with all replicas
  docker service rm webserver
