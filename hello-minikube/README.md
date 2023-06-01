# Hello minikube

kubectl create deployment hello-node --image=registry.k8s.io/echoserver:1.4
kubectl get deployments
kubectl get pods
kubectl expose deployment hello-node --type=LoadBalancer --port=8080
kubectl get service
minikube service hello-node
