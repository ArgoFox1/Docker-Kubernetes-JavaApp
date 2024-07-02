# Deploying Java Applications with using Docker and Kubernetes
![kubectl-logo-medium](https://github.com/ArgoFox1/Docker-K8S-JavaApp/assets/105239243/ecc34f05-edc2-46ea-ba85-25a9558954dd)
![Docker-Logo_Horizontel_279x131 b](https://github.com/ArgoFox1/Docker-K8S-JavaApp/assets/105239243/2c3f991f-1066-4f3f-9221-9b4ae5a9e795)

# GUIDE FOR DEPLOYMENT
1-**Make sure you had git,kubernetes and docker**

>git -v(for git) , minikube(for kubernetes) , docker -v(for docker)

2-**Start kubernetes without using docker**

> minikube start --driver=none

3-**Clone Project**

>git clone https://github.com/ArgoFox1/Docker-K8S-JavaApp.git

4-**Install maven**

>sudo apt update(updating)
>>sudo apt install maven(installing maven)
>>>mvn --version(check mvn)

5-**ADD Maven environment variable**
>export MAVEN_HOME=/usr/share/maven

6-**Go to the project folder**
>cd /path/to/your/folder

7-**Go to the shopfront folder and run these codes**

>mvn clean install(building codes)
>>docker build -t shopfront . (creating image)

8-**Go to the stockmanager folder and run these codes**

>mvn clean install(building codes)
>>docker build -t stockmanager . (creating image)

9-**Go to the productcatalogue folder and run these codes**
>mvn clean install(building codes)
>>docker build -t productcatalogue . (creating image)

10-**After that go to the kubernetes folder and run these codes**
>kubectl apply -f shopfront-service.yaml(shopfront service and deployment object creating)
>>kubectl apply -f productcatalogue-service.yaml(productcatalogue service and deployment object creating)
>>>kubectl apply -f stockmanager-service.yaml(stockmanager service and deployment object creating)

11-**check status of the services and deployment object**
>kubectl get services(checking service objects)
>>kubectl get deployment(checking deployment objects)

12-**If all of them runs with successfully run these codes**
>minikube service shopfront
>>minikube service productcatalogue
>>>minikube service stockmanager

# IN APP PHOTOS
![SHOPFRONT](https://github.com/ArgoFox1/Docker-K8S-JavaApp/assets/105239243/a2da1e4c-29a0-47de-bc8e-1b6dbecffc93)

![PRODUCTCATALOGUE](https://github.com/ArgoFox1/Docker-K8S-JavaApp/assets/105239243/9788bce4-84f2-47b2-b401-995f2800f3d0)

![STOCKMANAGER](https://github.com/ArgoFox1/Docker-K8S-JavaApp/assets/105239243/81e034b9-973c-4025-bf72-dc69a1a34d4a)
