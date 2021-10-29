# BackendDemoProject
Backend Demo Node JS Project

## Installation
### 1) Install docker & docker-compose.

### 2) Clone this repository: git clone https://github.com/shabbirhussainm/BackendDemoProject.git .

### 3) Modify configuration:

**init-letsencrypt.sh** fetches and ensures the renewal of a Let’s Encrypt certificate for one or multiple domains in a docker-compose setup with nginx. This is useful when you need to set up nginx as a reverse proxy for an application.

a) Add domains and email addresses to **init-letsencrypt.sh**
b) Replace all occurrences of dockernodejs.com with primary domain (the first one you added to init-letsencrypt.sh) in nginx/config/nginx.conf

### 4) Run the init script:

     $ ./init-letsencrypt.sh
 
### 5) Access the App:

     $ docker-compose ps
     
     Access the Application using http://IP
     
     The following Docker Images are used for this Application flow. 
          
              **Proxy Server -> Node Js -> MongoDB & MySQL**
              
     a) nodejs-app (custom Image using Dockerfile)
     b) mongo 
     c) mysql
     d) nginx (for reverse proxy)
     e) certbot (for SSL Cert)
     
### Important Points/Limitations:

1) nginx/config/nginx.conf is implemented for http and https protocols. But as the domain/DNS limitation, it has been enabled for http protocol only.
2) This app has been migrated to single container based using docker and docker-compose as the time constraint, next it can be extended to multi container deployment using **Container Orchestration Engine** like K8s.
