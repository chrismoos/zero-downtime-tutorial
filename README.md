This repository is a sample application that accompanies the blog post here:

[https://www.chrismoos.com/2016/09/28/zero-downtime-deployments-kubernetes/](https://www.chrismoos.com/2016/09/28/zero-downtime-deployments-kubernetes/)


# Build the images

    docker build -t chrismoos/zero-downtime-tutorial:red -f Dockerfile-red .
    docker build -t chrismoos/zero-downtime-tutorial:blue -f Dockerfile-blue .
    docker build -t chrismoos/zero-downtime-tutorial-proxy -f Dockerfile-proxy .
    
# Create the application
    
    kubectl create -f myapp-service.yml
    kubectl create -f myapp-proxy-service.yml
    kubectl create -f myapp.yml
    kubectl create -f myapp-proxy.yml
    
# View it

    minikube service myapp-proxy
