# Configure Docker Networks and Containers for Selective Connectivity Testing
# 1 Create 2 bridge networks
  docker network create --driver bridge Network1
  docker network create --driver bridge Network2

# 2 Check the list of available networks
  docker network ls

# 3 Create a busybox container c1 on Network1 network
  docker run --name c1 -it --network Network1 busybox
  Come out of the c1 container without exit ctrl+p,ctrl+q

# 4 Identify the ipaddress of c1
  docker inspect c1

# 5 Create another busybox container c2 on Netowrk1 network
  docker run --name c2 -it --network Netowrk1 busybox
  ping ipaddress_of_c1    (It will ping)
  Come out of the c2 container without exit ctrl+p,ctrl+q

# 6 Identify the ipaddress of c2
  docker inspect c2

# 7 Create another busybox container c3 on Netowrk2 network
  docker run --name c3 -it --network Netowrk2 busybox
  ping ipaddress_of_c1  (It should not ping)
  ping ipaddress_of_c2  (It should not ping)
  Come out of the c3 container without exit ctrl+p,ctrl+q

# 8 Identify the ipaddress of c3
  docker inspect c3 

# 9 Now attach Netowrk2 network to c2 container
  docker network connect Netowrk2 c2

# 10 Since c2 is now on both Netowrk1 and Netowrk2 networks it should ping
   to both c1 and c3 containers
   docker attach c2
   ping ipaddress_of_c1  (It should  ping)
   ping ipaddress_of_c3  (It should  ping)
   Come out of the c2 container without exit ctrl+p,ctrl+q

# 11 But c1 and c3 should not ping each other
   docker attach c3
   ping ipaddress_of_c1  (It should not ping)

