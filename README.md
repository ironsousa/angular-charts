# **angular-charts**

## **BUILD STEPS**
---

## **Table of Contents**
[1. Without Docker](#without-docker)  
[2. With Docker](#with-docker)  
[3. With Docker Compose](#with-docker-compose)  

<a name="without-docker"></a>
## 1. **Without Docker**
### **Required CLI for the fake REST API (Backend)**
    npm install -g json-server

### **Running the fake API**
From the projects' root directory, do the following step: 

    json-server --watch ./backend/data.json --port 4000 -H 0.0.0.0
    
Where: 
- ``--watch ./backend/data.json`` specify the endpoint ``/results``;
- ``--port 4000`` specify the connection access of the client, through the port 4000
- ``-H 0.0.0.0`` accepts connection from any IP address of the host through the lan (required with docker).

Next, you can access the following endpoints:
- [http://localhost:4000](http://localhost:4000) - the root endpoint of the fake api.
- [http://localhost:4000/results](http://localhost:4000/results) - the /results endpoint of the mocked ``data.json``.
### **Required CLI for the Angular Web APP (Frontend).**
    npm install -g @angular/cli

### **Installing the Angular Web App dependencies**

From the projects' root directory, do the following steps:

    cd ./frontend
    npm install

### **Running the Web APP**

From the projects' frontend directory, do the following command:

    ng serve --open --host 0.0.0.0 --disable-host-check
  
Where:
- ``ng serve --open`` starts the server on port 4200; and
- ``--host 0.0.0.0 --disable-host-check`` accepts connection from any IP address of the host with no check.

Next, you can access the web application from the following url:
- [http://localhost:4200](http://localhost:4200) - which requires that the fake api is already serving.

<a name="with-docker"></a>
## 2. **With Docker**

From the projects' root directory, build the following images (Backend and Frontend):

    docker build . -t fake-server -f ./frontend/Dockerfile
    docker build . -t angular-charts -f ./frontend/Dockerfile

Next, run the containers:

    docker run --rm -p 4000:4000 -d --name fake-server_container fake-server
    docker run --rm -p 4200:4200 -d --name angular-charts_container angular-charts

Now, you can already access the web application through the following url:
- [http://localhost:4200](http://localhost:4200)

<a name="with-docker-compose"></a>
## 3. **With Docker Compose**

From the projects' root directory, build the following images (Backend and Frontend):

    docker-compose up -d --build

Where:

- ``docker-compose up`` starts the containers with the configured images;
- ``-d `` detach the active tty from the executed command line; and
- ``--build`` builds all the images and containers if not build before.

Now, you can already access the web application through the following url:
- [http://localhost:4200](http://localhost:4200)