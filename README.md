```
docker --version
docker build .
docker run -p 3000:3000 -it <image-id>
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
