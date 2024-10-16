# Usecase1
# Create an nginx contaienr in detached mode and name it webserver Also perfrom port mapping
docker run --name webserver -p 8888:80 -d nginx
# To check if the nginx container is running
docker container ls
# To access the nginx container from the leve of browser
public_ip_of_dockerhost:8888

# Usecase2
# Start tomcat as a container and perfrom automatic port mapping
docker run --name appserver -d -P tomcat
# To see the ports used by the above container
docker port appserver
# To access the tomcat from borwser
piblic_ip_of_dockerhost: hostport

# Usecase3
# Start a jenkins container in detached mode and also perfrom port mapping
docker run --name myjenkins -d -p 9999:8080 jenkins/jenkins
# To see the ports used by the above container
docker port appserver
# To access jenkins from browser
public_ip_of_docker_host:9999

# Usecase4
# Create a mysql container and login as root user and create some sql tables
#  Create a mysql container
docker run --name db -d -e MYSQL_ROOT_PASSWORD=intelliqit mysql:5
# To check if the mysql container is running
docker container ls
# To go into the bash shell of the container
docker exec -it db bash
# To login into the database
mysql -u root -p
Password: mydatabase
# To see the list of databases
show databases;
# To move into any of the above database
use databasename;
Eg: use sys;
# To create emp and dept tables here
Open "https://justinsomnia.org/2009/04/the-emp-and-dept-tables-for-mysql/" Copy script from emp and dept tables creation Paste in the mysql container
# To see the data of the tables
select * from emp;
select * from dept;
