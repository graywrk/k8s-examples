# PHP Guestbook with Redis

kubectl apply -f redis-leader-deployment.yaml
kubectl get pods
kubectl logs -f deployment/redis-leader
kubectl apply -f redis-leader-service.yaml
kubectl get service
kubectl apply -f redis-follower-deployment.yaml
kubectl get pods
kubectl apply -f redis-follower-service.yaml
kubectl get service
kubectl apply -f guestbook.yaml
kubectl get pods -l app=guestbook -l tier=frontend
kubectl apply -f guestbook-frontend.yaml
kubectl get pods -l app=guestbook -l tier=frontend
kubectl apply -f guestbook-frontend-service.yaml
kubect get services
kubectl port-forward svc/frontend 8080:80

kubectl scale deployment frontend --replicas=5
kubectl get pods
kubectl scale deployment frontend --replicas=2
kubectl get pods