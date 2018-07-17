This is my local docker environment for php development.  
It uses LEMP stack.  

Use the next command to work. It affects only local-* containers:   
1. `./docker/lemp/start` - start all containers  
2. `./docker/lemp/stop` - stop all containers  
3. `./docker/lemp/restart` - restart all containers  
4. `./docker/lemp/into` [php-fpm|mariadb|nginx] - dive into bash of the entered container  

How to use:  
0. Make sure that you have `docker` and `docker-compose` installed and they have current versions > 16   
1. Download the repository with command  
`git clone https://github.com/AlxMrz/php-docker sites`  
2. Go to the `sites/` directory:  
`cd sites`    
2. Make sure that the port 4000 is not busy or change setting in docker-compose.yml and start containers with command:  
`./docker/lemp/start`  
3. Add a test site to you file /etc/hosts  
`127.0.0.1 test.local`  
4. Enter in your browser the next address(change port if you changed him) and you will see phpinfo() output:  
`test.local:4000/`  


To connect mariadb you need to input:  
* host = 127.0.0.1  
* port = 4003  
* user = myuser  
* password = myuser  

To make your site enabled you will need to do:  
1. Put your sites sources in `www/` directory  
2. Make another `*-local.conf` file inside `docker/nginx/` directory  
3. Write about your site in `/etc/hosts` file  
After these steps everything must work.
