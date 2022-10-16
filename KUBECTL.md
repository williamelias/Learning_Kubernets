# Basic commands

- kubectl options
- kubectl help

## Cluster

- To see basic info of cluster: kubectl cluster-info
- To save all info in file: kubectl cluster-info dump > info.txt

## Node

- see all nodes and their status: 
    - kubectl get nodes --namespace=<choice>
    - kubectl get nodes -o --wide (with ip)
## Pod

- see all pods and their status:    
    - kubectl get pods --watch
    - kubectl get pods --namespace=<choice>
    - kubect get pods -o --wide (with ip)

- run docker container inside pode with docker hub image:
    - kubectl run <pod_name> --image=<dockerhub_image>

- see pod info and status : kubectl describe pod <pod_name>

- delete pod:  kubectl delete pod <pod_name>

## Deployment

- create deployment

    kubectl create deployment <name> --image=<dockerhub_image>

- describe deployment info

    kubectl describe deployment <name>

- scale deployment

    in creation:
        kubectl deployment <name> --replicas=<number>
    in scale:
        kubectl scale deployment <name>  --replicas=<number>

- push new version of the image from dockerhub

    kubectl set image deployment <name> <container_name>=<image_name>:<image_version>

- see rollout status:
    kubectl rollout status deployment nginx-deployment


## Service

This resources make your aplication available to external access.

- create clusterIp
    kubectl expose deployment <name> --port=<cluster_port> --target-port=<default_image_port>
- create NodePort
    kubect expose deployment <name> --type=NodePort --port=<cluster_port> --target-port=<default_image_port>
- see all services
    kubectl get svc
- acces service by minikube
    minikube 

## Namespace

This resource make group of resources to separete them.

- see all namespaces into cluster: kubectl get namespace

## Context

This resource switch between cluster configurations

- kubect config current-context

## Tips and tricks 

add kubectl as 'k' letter in the bash

    alias k=kubect

## Delete all resource in namespace

kubectl delete all --all