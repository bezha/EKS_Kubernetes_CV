EKS Simple stateless CV:

eksctl create cluster --name CV-Bezha
kubectl create namespace cv-bezha-app
kubectl create -f deployment.yml
kubectl get pods
kubectl apply -f service.yaml
kubectl get all -n cv-bezha-app

kubectl -n cv-bezha-app patch svc cv-bezha-app -p '{"spec": {"type": "LoadBalancer"}}'
kubectl -n cv-bezha-app get svc cv-bezha-app
