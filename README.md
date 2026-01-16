## 1. Run docker
eval $(minikube docker-env)

docker build -t nextjs:latest .

#### Install Helm chart
helm install nextjs helm/nextjs

#### verify the docker image
docker images | grep web-nextjs-mfe


### Access app (no ingress yet)
minikube service nextjs

## 2. Check Load balance by adding more load
*check the [commit](https://github.com/veeri/nextjs-docker-kubernate/commit/2678607127376cc5e67514c8f6d2dc00b1a8a212) for changes*

#### Generate CPU load inside pod
kubectl exec -it deploy/nextjs -- sh

###### Inside pod:
while true; do :; done

###### Then watch scaling:
kubectl get pods -w


###### You should see:
nextjs-xxxxx   Running
nextjs-yyyyy   Running
🎉 Horizontal scaling working!
