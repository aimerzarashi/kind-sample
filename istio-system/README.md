# install
```
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
```

# uninstall
```
kubectl delete -f https://raw.githubusercontent.com/istio/istio/release-1.21/samples/addons/kiali.yaml
kubectl delete -f https://raw.githubusercontent.com/istio/istio/release-1.21/samples/addons/grafana.yaml
kubectl delete -f https://raw.githubusercontent.com/istio/istio/release-1.21/samples/addons/jaeger.yaml
kubectl delete -f https://raw.githubusercontent.com/istio/istio/release-1.21/samples/addons/prometheus.yaml
kubectl delete namespace istio-system
```