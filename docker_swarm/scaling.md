# Create httpd with 4 replicas and scale it to 8 and scale it down to 2 

# 1 Create httpd with 4 replicas
  docker service create --name websserver -p 9090:8080 --replicas 4 httpd

# 2 Check if 4 replicas are running
  docker service ps webserver

# 3 Increase the replicas count to 8
  docker service scale webserver=8

# 4 Check if 8 replicas are running
  docker service ps webserver

# 5 Decrese the replicas count to 2
  docker service scale webserver=2

# 6 Check if 2 replicas are running
  docker service ps webserver
