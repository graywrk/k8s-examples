# Redis

kubectl apply -f example-redis-config.yaml
kubectl apply -f redis-pod.yaml
kubectl get pod/redis configmap/example-redis-config
kubectl exec -it redis -- redis-cli
CONFIG GET maxmemory
kubectl delete pod/redis configmap/example-redis-config