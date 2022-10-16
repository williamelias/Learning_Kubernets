
## Minikube starting

After install minikube and kubectl you must execute this command:

- minikube start --drive=<chosed_drive>

other useful commands: execute minikube help and see these.

### Connect to minikube cluster by ssh

getting the cluster ip: minikube ip
connect to the cluser: ssh docker@ip

complement: the default passaword of minikube cluster is 'tcuser'

## Connect to service 

- acces service by minikube
    minikube service <service_name>
- access service url only
    minikube service <service_name> --url

## Access kubernets dashboard

- minikube dashboard