// run on your local docker engine
```
docker build -t mingder78/devops-go-web-server .
```
```
docker run -d -p 1323:1323 -v `pwd`/download:/download mingder78/devops-go-web-server
```
// test your web page
```
wget -c localhost:1323
```
// push your docker image to docker hub
```
docker push mingder78/devops-go-web-server
```
// on mac os x
```
docker-machine ip
192.168.99.100
curl 192.168.99.100:1323
```
// test commands on kubernetes or minikube
```
kubectl run --image='docker.io/mingder78/devops-go-web-server' go-web-server --port=1323
 
kubectl expose deployment go-web-server --port=1323 --name=go-web-server --type=NodePort
 
kubectl get development
 
kubectl scale deployment/go-web-server --replicas=4
 
kubectl get deployment go-web-server -o yaml > rcp4.yaml
 
kubectl delete deployment go-web-server
```
// try to start and stop it again with yaml file
```
kubectl create -f rcp4.yaml

kubectl delete -f rcp4.yaml
```

