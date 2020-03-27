```
docker --version
docker build .
docker run -p 3000:3000 -it <image-id>
curl localhost:3000
```

```
docker build .
docker login
docker tag <image-id> qingjiezhao/k8s-demo:latest
docker push qingjiezhao/k8s-demo
docker pull qingjiezhao/k8s-demo
docker run -p 3000:3000 -t <image-id>
curl localhost:3000
```

```
docker login
docker images
docker tag <image-id> your-login/docker-demo
docker tag <image-id> your-login/docker-demo:latest
docker push your-login/docker-demo


https://12factor.net/

# get information about all running pods
kubectl get pod
# descibe one pod
kubectl describe pod <pod>
# Expose the port of a pod(creates a new service)
kubectl expose pod <pod> --port=444 --name=frontend
# port forward the exposed pod port to your local machine
kubectl port-forward <pod> 8080
# attach to the pod
kubectl attach <podname> -i
# Execute a command on the pod
kubectl exec <pod> -- command
# add a new label to a pod
kubectl lable pods <pod> mylabel=awesome
# Run a shell in a pod -very useful for debugging
kubectl run -i --tty busybox --image=busybox --restart=Never --sh
```

```
git clone https://github.com/qingjie/kubernetes-course
cd kubernetes-course
kubectl get node
cat first-app/hello-world.yaml
kubectl -f first-app/hello-world.yaml
kubectl get pod
kubectl describe pod <pod>

kubectl port-foward <pod> 8081:3000
curl localhost:8081
or
kubectl expose pod <pod> --type=NodePortn --name <pod>-service
kubectl get service
```

* https://jimmysong.io/kubernetes-handbook/guide/docker-cli-to-kubectl.html

```
docker build -t auth0:v1 .

docker run -p 127.0.0.1:8111:80 -d --name auth0_test auth0:v1

docker run -it auth0:v1 /bin/sh
```

* https://hsk.oray.com/news/6438.html

```

docker build -t auth0:v1 .

docker tag auth0:v1 qingjiezhao/auth0:v1
docker run -d -p 3000:3000 -d --name auth0 qingjiezhao/auth0:v1

docker run -it auth0:v1 /bin/sh


docker login -u username -p passwd
docker push qingjiezhao/auth0:v1
```
