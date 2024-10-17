# Usecase1
# Create 2 busybooks containers c1 and c2 and link them
# Create a busybox contaienr and name it c1
docker run --name c1 -it busybox
# To come out of the c1 contaienr without exit
ctrl+p,ctrl+q
# Create another busybox container c2 and link it with c1 container
docker run --name c2 -it --link c1:mybusybox  busybox
# Check if c2 is pinging to c1
ping c1

# Usecase2
# Setup wordpress and link it with mysql container
# Create a mysql container
docker run --name mydb -d -e MYSQL_ROOT_PASSWORD=mydatabase mysql
# Create a wordpress container and link with the mysql container
docker run --name mywordpress -d -p 8888:80 --link mydb:mysql wordpress
# To check if wordpress and mysql containers are running
docker container ls
# To access wordpress from a browser
public_ip_dockerhost:8080
# To check if wordpress is linked with mysql
docker inspect mywordpress
Search for "Links" section
