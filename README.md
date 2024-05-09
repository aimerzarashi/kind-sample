
# install
```
kind create cluster --config kind/kind-config.yaml

kubectl label node kind-control-plane node.kubernetes.io/exclude-from-external-load-balancers-

cloud-provider-kind

istioctl install --set profile=demo -y

kubectl create -n istio-system secret tls tls-credential-aimerzarashi.com --key=services/tls/aimerzarashi.com/privkey1.pem --cert=services/tls/aimerzarashi.com/fullchain1.pem 

kubectl create namespace services
kubectl label namespace services istio-injection=enabled --overwrite
kubectl apply -n=services -f services
```


# uninstall
```
kind delete cluster --name kind
```