# install
```
kubectl apply -f _k8s/kube-system/dns.yaml
kubectl -n kube-system rollout restart deployment coredns
```