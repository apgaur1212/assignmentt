# ELL887 Cloud Computing - Assignment 1 

## Overview
This assignment consists of three parts:
1. *Modifying an existing web server container* (Nginx)
2. *Creating and pushing a container* (Python program + MySQL database)
3. *Deploying a web server in Kubernetes*
---

## Part 1: Modifying an Existing Web Server Container

### Objective
This part modifies an Nginx container to serve a custom webpage at http://localhost/ELL887.

### Files Provided:
- Dockerfile (to create a custom Nginx container)
- index.html (to display the required message)

### Steps to Run:
1. *Build the container:*
   ```sh
   docker build -t modified-nginx .

2. **Run the container:**
   ```sh
   docker run -d -p 80:80 modified-nginx
   
![image](https://github.com/user-attachments/assets/6953526e-d044-4e37-8bca-d9a33a7fde98)
)

4. *Verify the output:*
   ```sh
   (htttp://localhost/ELL887)

   OUTPUT: "Hello world! I am Your Aditya Prakash".
![image](https://github.com/user-attachments/assets/67565b47-4c72-4d9f-b1b0-5b161ca9515e)
)

   
## Part 2: Creating and Pushing a Container

### Objective
This part containerizes a Python program that prints "Hello world!! I am Aditya Prakash" and includes a MySQL database.

### Files Provided:
- `Dockerfile` (to create a custom Nginx container)
- `docker-compose.yaml` (to include a MySQL database)
- `index.html` (to display the required message)

### Steps to Run:

**1. Push Python Image to Docker Hub :**
   sh
   docker push apgaur8004/ell887:v1

**2. Run the Python Container:**

   docker run apgaur8004/ell887:v1


   
   OUTPUT: "Hello world!! I am Aditya Prakash".
   
![image](https://github.com/user-attachments/assets/1509fe2a-755b-463a-a8a8-ad61ae550e5c)
)


### 3. Pull MySQL Image:

   docker pull mysql:latest
   
### 4. Tag MySQL Image
   docker pull mysql:latest

### 5. Push MySQL Image to Docker Hub
docker push apgaur8004/ell887:mysql

### 6. Run MySQL Container
docker run -d --name mysql-db -e MYSQL_ROOT_PASSWORD=password -e MYSQL_DATABASE=mydb -e MYSQL_USER=apgaur8004 -e MYSQL_PASSWORD=password apgaur8004/ell887:mysql

### 7. Verify MySQL Container
docker ps



![image](https://github.com/user-attachments/assets/1ba33e3d-bc19-4a9b-864e-4a2ec9f311ae)
)


## Part 3: Modifying an Existing Web Server Container

### Objective
Deploy a web server in a Kubernetes cluster using Minikube. web server runs on port 30001

### Files Provided:
- webserver-deployment.yaml
- webserver-service.yaml

### Steps to Run:
1. **Start Minikube**
   ```sh
   minikube start

3. **Apply the Kubernetes configurations:**
   ```sh
   kubectl apply -f webserver-deployment.yaml
   kubectl apply -f webserver-service.yaml
   
4. *Verify the deployment:*
   ```sh
   kubectl get deployments
   kubectl get pods
   kubectl get services

5. *Access the web server:*
   ```sh
   minikube service webserver-service

![image](https://github.com/user-attachments/assets/d37d632b-6c86-4fbc-87fb-9651a6e33b0b)
)
   OUTPUT: nginx web page

![image](https://github.com/user-attachments/assets/52492ef3-5b93-4063-bc93-27fa7c8781ed)
)
