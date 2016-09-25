# README

An example of two dockerized apps communicating using built in Docker DNS with Nginx as the router

## Installation
* Clone this Repo
```
  git clone https://github.com/practo/docker-dns-nginx.git && cd docker-dns-nginx
  sudo echo "127.0.0.1 accounts.myproduct.local" >> /etc/hosts
  sudo echo "127.0.0.1 calendar.myproduct.local" >> /etc/hosts
```
* Start the nginx, accounts(app1) and calendar(app2) containers
```  
	export COMPOSE_PROJECT_NAME=dockerX	&& docker-compose up
```
* Want to access `accounts.myproduct.local` from the other container(app2) and vice versa
```
    docker exec -it dockerx_calendar_1 /bin/bash
	ping -c 5 accounts.myproduct.local ========> resolves to 127.0.0.1 :( 
	curl accounts.myproduct.local =============> resolves locally not to the other container :(  how to do that?
``` 
