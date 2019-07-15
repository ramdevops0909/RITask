# RITask

Nginx Dockerfile:
This repository contains Dockerfile of Nginx and serving the static content from Reverse Proxy web server and published to the public Docker Hub Registry.

Base Docker Image
nginx
Installation
Install Docker.

Download automated image from public Docker Hub Registry: docker pull ramdevops0909/staticpage

(alternatively, you can build an image from Dockerfile: docker build -t ramdevops0909/staticpage ." github.com/ramdevops0909/RITask

)

Usage
docker run -d -p 80:80 dockerfile/nginx
Attach persistent/shared directories


Created hello-staticpage-service.yaml file and which  contains following details
  - deployment.yaml
       I am performing rolling update on Kubernetes cluser ( its has 3 nodes ( kubemaster,kubenode-1,kubenode-2)
       Taking the image from docker hub (staticpage)
  - services.yaml
       Accesing above Staticpage using loadbancer Ip address with port "80"
