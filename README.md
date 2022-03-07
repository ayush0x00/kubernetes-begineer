# Using Kubectl to deploy the application

0. Make sure you have minikube up and running 😉
1. In the project directory run `kubectl apply -f .`

## The container structure

If you do `docker ps`, you can see that you have a minikube container running. The NodePort opens a PORT on the node, which is running inside the container. Here the node name is `minikube` which is master as well as worker. To access the PORT opened by NodePort in `blue-green.yaml`, you have to get inside the container `minikube`.
In `docker ps` you can see that the PORT opened by NodePort is not mapped with the container. It is the reason, why you get time out when accessing the PORT from outside the container using `minikube ip`.

## Setting up Ingress controller

1. `minikube addons enable ingress`
2. `kubectl get pods -n ingress-nginx` to verify ingress controller is up
3. Create ingress.yaml file and apply
4. `kubectl get ingress` to get ip of domain and ingress controller info
