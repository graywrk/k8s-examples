# Apache Cassandra

kubectl apply -f cassandra-service.yaml
kubectl get svc cassandra
kubectl apply -f cassandra-statefulset.yaml
kubectl get statefulset cassandra
kubectl get pods -l="app=cassandra"
kubectl exec -it cassandra-0 -- nodetool status

grace=$(kubectl get pod cassandra-0 -o=jsonpath='{.spec.terminationGracePeriodSeconds}') \
  && kubectl delete statefulset -l app=cassandra \
  && echo "Sleeping ${grace} seconds" 1>&2 \
  && sleep $grace \
  && kubectl delete persistentvolumeclaim -l app=cassandra
kubectl delete service -l app=cassandra