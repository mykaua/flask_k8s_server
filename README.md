# Simple Python flask with nginx

## Description

Flask as backend, nginx as frontend via revers proxy

## Requirments 

* Python 3.10
* Flask lib 
* Docker 
* k8s 

## build

Clone the repository and build Dockers:
```
git Clone
cd src 
docker build -t your_repo/app_name:version 
docker push your_repo/app_name:version

cd ../nginx
docker build -t your_repo/nginx_name:version
docker push -t your_repo/nginx_name:version
```

## Run 

Version of image has to be updated, it can be done in kustomization.yaml for backend and fronetend , please add the line:

Backend(```k8s/backend/kustomization```):

```
newName: your_repo/app_name
newTag: version
```

Frontend(```k8s/fronetend/kustomization```):


```
newName: your_repo/nginx_name
newTag: version
```


To deploy app to k8s:
```
cd k8s
kubeclt apply -k ./ 
```


## Usage

To check the website is up and running, will be used Kube Port Forwarding:

```
kubeclt port-forward svc/flask-nginx 8080
```

Open browser and check website:

[main page](http://localhost:8080)
[backend page](http://localhost:8080)


## Additional info:

* [Example](https://earthly.dev/blog/setup-reverse-proxy-kubernetes-nginx/)

```
```
```
```
```
```

