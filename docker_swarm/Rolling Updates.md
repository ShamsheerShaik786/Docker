# Create redis:3 with 5 replicas and later update it to redis:4 also rollback to redis:3

# 1 Create redis:3 with 5 replicas
  docker service create --name myredis --replicas 5 redis:3

# 2 Check if all 5 replicas of redis:3 are running
  docker service ps myredis

# 3 Perfrom a rolling update from redis:3 to redis:4
  docker service update --image redis:4 myredis

# 4 Check redis:3 replcias are shut down and in its palce redis:4 replicas are running
  docker service ps myredis

# 5 Roll back from redis:4 to redis:3
  docker service update --rollback myredis

# 6 Check if redis:4 replicas are shut down and in its place redis:3 is running
  docker service ps myredis
