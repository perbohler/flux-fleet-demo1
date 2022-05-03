
### create cluster
kind create cluster --config kind/create-cluster-config.yaml

### install fluxcd
kubectl apply -k resources/

create secret with key for git repo

create fluxcd gitrepository object 

### create fluxcd kustomization

 - ingress-controller
 - demo-deployment
