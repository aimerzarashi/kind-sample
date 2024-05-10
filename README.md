
# install
```
kind create cluster --config kind/kind-config.yaml
kubectl label node kind-control-plane node.kubernetes.io/exclude-from-external-load-balancers-
cloud-provider-kind

istioctl install --set profile=demo -y

kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.21/samples/addons/kiali.yaml
kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.21/samples/addons/grafana.yaml
kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.21/samples/addons/jaeger.yaml
kubectl apply -f https://raw.githubusercontent.com/istio/istio/release-1.21/samples/addons/prometheus.yaml
kubectl rollout status deployment/kiali -n istio-system
kubectl rollout status deployment/grafana -n istio-system
kubectl rollout status deployment/jaeger -n istio-system
kubectl rollout status deployment/prometheus -n istio-system
istioctl dashboard kiali

kubectl create -n istio-system secret tls tls-credential-aimerzarashi.com --key=services/tls/aimerzarashi.com/privkey1.pem --cert=services/tls/aimerzarashi.com/fullchain1.pem 

kubectl create namespace services
kubectl label namespace services istio-injection=enabled --overwrite
kubectl apply -n=services -f services
```


# uninstall
```
kind delete cluster --name kind
```