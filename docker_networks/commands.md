# 1 To see the list of docker networks
    docker network ls

# 2 To create a docker network
    docker network create --driver network_type network_name

# 3 To get detailed info about a network
    docker network insepct network_name/network_id

# 4 To delete a docker network
    docker network rm network_name/network_id

# 5 To connect a running container to a network
    docker netowork connect network_name/network_id container_name/container_id

# 6 To disconnect a running container to a network
    docker netowork disconnect network_name/network_id container_name/container_id
