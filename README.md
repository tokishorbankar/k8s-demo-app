### Repository for the K8S-DEMO-APP

#### K8s manifest files inside of .k8s/templates
* mongo-config.yaml
* mongo-secret.yaml
* mongo-deployment.yaml
* mongo-service.yaml
* webapp-deployment.yaml
* webapp-service.yaml


#### K8s commands

##### start Minikube and check status
```
minikube start --driver docker 
minikube status
```


##### get minikube node's ip address
```
minikube ip
```

##### get basic info about k8s components
```
kubectl get node
kubectl get pod
kubectl get svc
kubectl get all
```


##### get extended info about components
```
kubectl get pod -o wide
kubectl get node -o wide
```
    

##### get detailed info about a specific component
```
kubectl describe svc {svc-name}
kubectl describe pod {pod-name}
```

##### get application logs
```
kubectl logs {pod-name}
```
    
##### stop your Minikube cluster
```
minikube stop
```

<br />

> :warning: **Known issue - Minikube IP not accessible** 

If you can't access the NodePort service webapp with `MinikubeIP:NodePort`, execute the following command:
    
    minikube service webapp-service

<br />



#### To start as K8s pod insie app folder
```
docker build -t tokishorbankar/k8s-demo-app:v1.0 .
docker push tokishorbankar/k8s-demo-app:v1.0
```


#### Links
* [mongodb image on Docker Hub](https://hub.docker.com/_/mongo)
* [K8s manifest files](https://github.com/tokishorbankar/k8s-demo-app/tree/main/.k8s/templates)
* [webapp image on Docker Hub](https://hub.docker.com/repository/docker/tokishorbankar/k8s-demo-app)
* [k8s official documentation](https://kubernetes.io/docs/home/)
* [Kubectl Plugin](https://github.com/ohmyzsh/ohmyzsh/tree/master/plugins/kubectl)