# clone repo and repo contain script to install docker and setup newuser inside ec2 instance

step 1: git clone https://github.com/ankitaj85/docker-swarm-demo.git

step 2: cd docker-swarm-demo

step 3: ./docker-install.sh

step 4: Check docker installation : docker run hello-world

setp 5: git clone https://github.com/docker/example-voting-app.git


# Initializing Docker Swarm 
sudo docker swarm init --advertise-addr ipaddress

############## Node Command ################
sudo docker node ls
sudo docker swarm leave --force (worker removes itself)
sudo docker node rm  -f id (manager removes the worker)
docker node ps 
docker node rm id 


######################Get Join token run mangaer node########################################
sudo docker swarm join-token worker


################## First Example:Creating a service  ###########################################
sudo docker service create --name default-app --replicas 3 -p 80:80 nginx:latest
sudo docker service ls
sudo docker service ps <name>
sudo docker service rm <name>
sudo docker service scale <name>=5


#####################Second example: Runing vote app #########################################
sudo docker stack deploy --compose-file docker-stack.yml vote
sudo docker service ls
sudo docker service ps 






 

