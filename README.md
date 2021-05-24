# What is core-services-swarm
It is a docker swarm that has traefik and portainer and is the core of https://silkky.cloud/ and my docker swarm.

# core-services-swarm Install
1.  ```git clone https://github.com/czadikem/core.git```
2.  ```cd core```
3.  ```rm portainer-data/blank.txt```  had to put in git repository so git would not remove the portainer-data folder
4.  ```cp .env.template .env```
5.  ```nano.env```  Put your hostnames for traefik and portainer in this file  "You can get three free ones from noip"
6.  ```nano traefik-data/traefik.yml```  change example@example.com to your email
7.  ```echo $(htpasswd -nb <username> <password>)``` change <username> to your username and change <password> to your password(it can't contain symbols like !.,)
8.  Copy the output of the above to your clipboard
9.  Then do ```nano traefik-data/configurations/dynamic.yml```  replace youradmintoken with your copied password from step 6.
10.  ```chmod 600 traefik-data/acme.json```


# core-services-swarm Deployment
1.  ```docker stack deploy -c <(docker-compose config) core```
2.  ```docker network create --driver=overlay traefik-public```

# Acknowledgments
Thanks to Oscar at https://silkky.cloud/ for helping me get this setup.  I also have to thank his wonderful Discord Community at https://discord.gg/BvqJQ3hNrQ
