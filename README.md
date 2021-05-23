1.  Do ```git clone https://github.com/czadikem/core.git```
2.  Then ```cd core```
3.  ```cp .env.template .env```
4.  ```nano.env```  change autiboytk.ddns.net and autiboypr.ddns.net to your own a hostnames  "Can get free ones from noip"
5.  ```nano traefik-data/traefik.yml```  change exmple@example.com to your email
6.  ```echo $(htpasswd -nb <username> <password>)``` change <username> to your username and change <password> to your password(it can't contain symbols like !.,)
7.  copy the out put of the above to your clipboard
8.  then do ```nano traefik-data/configurations/dynamic.yml```  replace youradmintoken with your copied password from step 6.
9.  do ```chmod 600 traefik-data/acme.json```


# core-services-swarm
10. ```docker stack deploy -c <(docker-compose config) core```
