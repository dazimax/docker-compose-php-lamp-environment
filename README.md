# docker-compose-php-lamp-environment

Setup Docker with docker-compose in PHP 5.6 and PHP 7.1 LAMP environment

Steps to setup;

1) Install docker, docker-compose
2) Setup the network in docker-compose.yml

      2.1) Comment out the external network
      2.2) Enable the new network 

networks:
 app_net:
  driver: bridge
  ipam:
   driver: default
   config:
    - subnet: 10.0.0.0/24
      gateway: 10.0.0.1

3) Add host to /etc/hosts file

     10.0.0.2 dev.projectname

4) Up (First time) and Start the docker-composer
     
     docker-compose up

5) After containers loaded visit the http://dev.projectname
