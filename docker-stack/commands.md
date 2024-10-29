# 1 To create a stack from a compose file
  docker stack deploy -c compose_filename stack_name

# 2 To see the list of stacks created
  docker stack ls

# 3 To see on which nodes the stack services are running
  docker stack ps stack_name

# 4 To delete a stack
  docker stack rm stack_name
