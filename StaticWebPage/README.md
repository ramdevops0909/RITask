# A Static Site using Docker and Nginx

This repo contains code for building a simple static website served using an Nginx container inside Docker. The code for the site is contained in `index.html`, and the Nginx config is in `default.conf`. The Dockerfile contains commands to build a Docker Image.

To build a Docker image from the Dockerfile, run the following command from inside this directory

```sh
$ docker build -t ramdevops0909/staticpage .
```
This will produce the following output

```
Sending build context to Docker daemon  95.23kB
Step 1/3 : FROM nginx:alpine
 ---> ea1193fd3dde
Step 2/3 : COPY default.conf /etc/nginx/conf.d/default.conf
 ---> Using cache
 ---> 3ef6dd0206db
Step 3/3 : COPY index.html /usr/share/nginx/html/index.html
 ---> Using cache
 ---> 12a0e026cd5f
Successfully built 12a0e026cd5f
```
```
Tag the Image:
docker tag ramdevops0909/staticpage ramdevops0909/staticpage:1
```
```
Push the image to docker  hub
docker push ramdevops0909/staticpage
The push refers to repository [docker.io/ramdevops0909/staticpage
```
```
To run the image in a Docker container, use the following command
```
$ docker run -itd --name mycontainer --publish 8080:80 ramdevops0909/staticpage:1
```

This will start serving the static site on port 8080. If you visit `http://localhost:8080` in your browser, you should be able to see our static site!
