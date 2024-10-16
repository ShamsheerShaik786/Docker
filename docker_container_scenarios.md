# Usecase1
# Create an nginx contaienr in detached mode and name it webserver Also perfrom port mapping
docker run  --name webserver -p 8888:80 -d nginx
# To check if the nginx container is running
docker container ls
# To access the nginx container from the leve of browser
public_ip_of_dockerhost:8888
