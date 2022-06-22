### install flux
kubectl apply -k resources/fluxcd-v0.30.2

### Add secret for ssh keys
ssh-keyscan github.com > ./known_hosts
kubectl -n flux-system create secret generic github-token \
    --from-file=./identity \
    --from-file=./identity.pub \
    --from-file=./known_hosts

### Add source/gitrepository
k apply -f branch-github-source.yaml

### create 2 sample deployments
poc-git-tag/webserver-avocado-demo

### Add kustomization #1
k apply -f tags-kustomize.yaml

### Add kustomization #2
