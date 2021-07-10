                                                        Task_№5
                                                -----------------------

# 1. Minikube installation and nginx ingress controller 
minikube start --driver=hyperkit

          ( I was using minikube start --driver=hyperkit )
minikube status

          Check if all good with minikube
kubectl get pods -n ingress-nginx

          Check if all good with ingress

# 2. Using nodejs-deployment.yaml, create deployment with 2 replicas

kubectl apply -f nodejs-deployment.yaml

# 2. Using nodejs-service.yaml, create service :D

kubectl apply -f nodejs-service.yml

        In this service yaml we specify targetport: 3000 | our container port and - port: 80 | when we enter service

# 2. Using nodejs-ingress.yaml, create our ingress

kubectl apply -f nodejs-ingress.yml

        Here we route traffic from ingress to service and to pods

        Then we get ip

minikube ip

        And final step

curl $(minikube ip)
