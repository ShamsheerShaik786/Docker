# To remove a worker from swarm cluster
docker node update --availability drain Worker1

# To make this worker rejoin the swarm
docker node update --availability active Worker1

# To make worker2 leave the swarm
Connect to worker2 usig git bash
docker swarm leave

# To make manager leave the swarm
docker swarm leave --force

# To generate the tokenid for a machine to join swarm as worker
docker swarm join-token worker

# To generate the tokenid for a machine to join swarm as manager
docker swarm join-token manager

# To promote Worker1 as a manager
docker node promote Worker1

# To demote "Worker1" back to a worker status
docker node demote Worker1
