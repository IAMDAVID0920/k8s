```

minikube start --driver=docker
kubectl apply -f mongo-config.yaml
kubectl apply -f mongo-secret.yaml
kubectl apply -f mongo.yaml
kubectl apply -f webapp.yaml

  879  kubectl get pod
  880  kubectl get all
  881  kubectl get configmap
  882  kubectl get secret
  883  kubectl get pod
  884  kubectl get deployment
  885  kubectl --help
  886  kubectl get --help
  887  kubectl describe service
  888  kubectl describe service webapp-service
  889  kubectl describe pod mongo-deployment-65ffdd9df6-gn262
  890  clear
  891  kubectl get pod
  892  kubectl logs webapp-deployment-65d4754f9d-nkj46
  893  kubectl logs webapp-deployment-65d4754f9d-nkj46 -f
  894  kubectl logs webapp-deployment-65d4754f9d-nkj46 -v
  895  kubectl logs --help
  896  clear
  897  kubectl get svc
  898  minikube ip
  899  kubectl get node -o wide

minikube status
minikube ip
minikube service webapp-service

minikube stop

```