# install
```
kubectl create -n istio-system secret tls tls-credential-aimerzarashi.com --key=tls/aimerzarashi.com/privkey1.pem --cert=tls/aimerzarashi.com/fullchain1.pem 

kubectl create namespace services
kubectl label namespace services istio-injection=enabled --overwrite
kubectl apply -n=services -f _k8s/
```

# uninstall
```
kubectl delete -n=services -f _k8s/
kubectl delete namespace services
 
kubectl delete -n istio-system secret tls-credential-aimerzarashi.com
```