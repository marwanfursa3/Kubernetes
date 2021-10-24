
# Kubernetes Ingress

## Create a new deployment with a name of your choice
     a. Image to use: yanivomc/spring-music:latest
### Once the service is deployed (verify)
### Expose the deploy using type = ClusterIP and with port 8090:8080
### Once Exposed and verified scale your pods to 2
### Create an Ingress to access the service using http://127.0.0.1/music 


### First Step - install docker ,kubernetes
### Install the nginx ingress-controller in your cluster, follow
### instructions in this link
https://kubernetes.github.io/ingress-nginx/deploy/#docker-desktop
### check if nginx controller is running
     
      Run kubectl get pods -n ingress-nginx
## Running The Application in git bash
### Create a new deployment 
       kubectl apply -f Kubernetes-ingress.yaml 
### check if the Deployment was created
         kubectl get deploy
### check if the server was created
         kubectl get svc
### check if the ingress was created
         kubectl get ingress
## Once Exposed and verified scale your pods to 2
       kubectl scale deployment --replicas=2 spring-deployment
### check if the Pods is 2
       kubectl get po
## Forward a local port to a port on the deployment's Pods.
       kubectl port-forward deployments/spring-deployment 8080

## Now you can go to  http://127.0.0.1/music 
