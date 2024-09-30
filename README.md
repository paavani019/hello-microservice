# Microservices Assignment : 
Setup & Deployment
This project involves setting up 2 microservices using Visual Studio Code, Spring Tool Suite, Docker and Kubernetes. The services were built, containerized, and deployed on a local Kubernetes cluster using Minikube.

**Setup and Installations**
Programming Language & Framework: Java with Spring Boot.
Tools: JDK, Maven, Spring Tool Suite 4 IDE.
Version Control: Git repository for source code management.

**Microservices Creation**
- Generated starter projects for Hello and World services using Spring Initializr.
_Hello Service Implementation:_
Endpoint: /hello
Functionality: Returns the string "Hello."
Implementation: Created HelloController.java with a hello() method using @GetMapping("/hello").
Testing: Added JUnit tests in CheckHTTPResponse.java.

_World Service Implementation:_
Endpoint: /world
Functionality: Returns the string "World."
Implementation: Created WorldController.java with a world() method using @GetMapping("/world").
Testing: Implemented JUnit tests similar to the Hello Service.

_Local Testing_
Compiled and ran both services locally on ports 9095 (Hello) and 8095 (World).
Verified the output through local testing.
Containerization with Docker

_Docker Setup_
Created Dockerfiles for Hello and World services, exposing ports 9095 and 8095, respectively.
Built the Docker images using:
bash
Copy code
docker build -t hello .
docker build -t world .
Ran the Docker images locally:
bash

_Push to Docker Hub_
Pushed the images to Docker Hub using:
bash
Copy code
docker tag hello:latest <dockerhub-username>/hello
docker tag world:latest <dockerhub-username>/world
docker push <dockerhub-username>/hello
docker push <dockerhub-username>/world
Deployment on Kubernetes
Google Kubernetes Engine (GKE) Setup
Acquired a free Google Cloud subscription and created Kubernetes clusters for Hello and World services.
Created k8s-hello.yaml and k8s-world.yaml for deployment and service configuration.
Deployed both services to GKE using:
bash
Copy code
kubectl apply -f k8s-hello.yaml
kubectl apply -f k8s-world.yaml
Verified the services were externally accessible:
Hello Service: http://34.172.139.242:8080/hello
<img width="1440" alt="Hello local host" src="https://github.com/user-attachments/assets/1afcfca3-fcc4-4fe8-9fed-911ed0b7ef1e">

World Service: http://34.134.15.68:8080/world
<img width="1440" alt="World local host" src="https://github.com/user-attachments/assets/a26868a1-f606-4100-99c9-a76bdc9e292b">

Creation of HelloWorld Service, Integration, and Testing

**Service Integration**
Integrated Hello and World services into a single service within the Hello microservice.
Created HelloWorldService with a /helloworld endpoint that returns "Hello World."
Configuration

Added a RestTemplate bean in AppConfig class to facilitate REST calls.
Defined external service URLs in application.properties for the Hello microservice.
Deployment

Rebuilt and pushed the updated Docker image to Docker Hub.
Redeployed the Hello service on GKE.

**Conclusion**
This project demonstrates a microservices architecture using Spring Boot, Docker, and Kubernetes.
Both Hello and World services were successfully containerized and deployed on GKE, showcasing microservices communication and cloud deployment.
Repository and Docker Hub Links

## Docker Images
are available in Docker Hub at : -
Hello Microservice: https://hub.docker.com/repository/docker/paavanikaruturi9/hello-service/general

World Microservice: https://hub.docker.com/repository/docker/paavanikaruturi9/world-service/general

<img width="1440" alt="Hello" src="https://github.com/user-attachments/assets/ff3be293-3c64-4305-941f-4b4b23f072f2">

<img width="1440" alt="World" src="https://github.com/user-attachments/assets/18a2ed17-1fc9-48e6-836d-5cbfbb04e6df">




# Docker images
<img width="1130" alt="Screenshot 2024-09-30 at 2 16 35 PM" src="https://github.com/user-attachments/assets/a180a52f-747b-4588-9e82-baa7d2a0d03b">


