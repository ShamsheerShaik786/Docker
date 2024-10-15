# Docker
# Virtualization:
This is the process of running multiple OS's parallelly on a single pice of h/w. Here we have h/w(bare metal) on top of which we have host os and on the host os we install an application called as hypervisor On the hypervisor we can run any no of OS's as guest OS. The disadvantage of this approach is these application running on the guest OS have to pass through n number of lavers to access the H/W resources.
# Containarization:
Here we have bare metal on top of which we install the host OS and on the host OS we install an application called as Docker Engine On the docker engine we can run any application in the form of containers Docker is a technology for creating these containers. Docker achieve what is commonly called as "process isolation" i.e. all the applications(processes) have some dependency on a specific OS.This dependency is removed by docker and we can run them on any OS as containers if we have Docker engine installed. These containers pass through less no of layers to access the h/w resources also organizations need not spend money on purchasing licenses of different OS's to maintain various applications. Docker can be used at the stages of S/W development life cycle Build---->Ship--->Run
# Installing Docker on Linux
1. Create an Ubuntu instance on AWS
2. Connect to it using git bash
3. Execute the below 2 commands
4. curl -fsSL https://get.docker.com -o get-docker.sh
5. sh get-docker.sh
