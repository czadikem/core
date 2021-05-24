# What is core-services-swarm
It is a docker swarm that has traefik and portainer and is the core of https://silkky.cloud/ and my docker swarm.

# core-services-swarm Install
1.  Do ```git clone https://github.com/czadikem/core.git```
2.  Then ```cd core```
3.  ```cp .env.template .env```
4.  ```nano.env```  Put your hostnames for traefik and portainer in this file  "You can get three free ones from noip"
5.  ```nano traefik-data/traefik.yml```  change example@example.com to your email
6.  ```echo $(htpasswd -nb <username> <password>)``` change <username> to your username and change <password> to your password(it can't contain symbols like !.,)
7.  copy the out put of the above to your clipboard
8.  then do ```nano traefik-data/configurations/dynamic.yml```  replace youradmintoken with your copied password from step 6.
9.  do ```chmod 600 traefik-data/acme.json```


# core-services-swarm Deployment
1.  ```docker stack deploy -c <(docker-compose config) core```
2.  ```docker network create --driver=overlay traefik-public```

# Acknowledgments
Thanks to Oscar at https://silkky.cloud/ for helping me get this setup.  I also have to thank his wonderful Discord Community at https://discord.gg/BvqJQ3hNrQ
