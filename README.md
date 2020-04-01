# k8-tomcat
Tomcat-on-k8-minikube <br>

To Run these Application in K8 please follow below Steps

## Pre-Requisites
* minikube 
* Docker
* kubectl 

### Deployment Guide
* predecting Minikube is up and running with Required Addon. 
* Enable Minikube docker env ```minikube docker-env```. Then run ```eval $(minikube -p minikube docker-env)```.
* open minikube dashboard with command ```minikube dashboard```.
* Create Namespace with ```kubectl apply -f namesapce.yaml```
* Create Services with ```kubectl apply -f services/```
* Create Ingress with ``` kubectl apply -f ingress/```
* Create docker images for deployment. Go to Directory "dockers", it has sample.war java application for demo. create the docker image with command ```docker build -t tomcat:1 .```
* Check Docker images buy command ```docker images | grep tomcat```
* Now apply the deployment by command ```kubectl apply -f deployment/```
* check kubernetes dashboard under Namespace "pmewada". Go to Pods and you would find "phm-tomcat-***"
* now go to Ingress and you should have Endpoints as IP address of you Kubernenets Cluster. Click on it and you would get 404 error page.
* Now add applicaiton name as root context for example ```<ENDPOINT_IP>/sample/```
