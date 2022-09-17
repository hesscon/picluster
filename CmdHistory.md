
# KUBERNETES DASHBOARD
```
kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.6.1/aio/deploy/recommended.yaml
kubectl -n kubernetes-dashboard create token dashadmin
```

# INGRESS NGINX
```
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
helm install ingress-nginx ingress-nginx/ingress-nginx
kubectl create ingress prometheus --class=nginx --rule="pimaster/prometheus/*=prometheus-kube-prometheus-prometheus:9090"
```

# PROMETHEUS
```
helm search repo prometheus-community
helm install prometheus prometheus-community/kube-prometheus-stack
```

# MQTT Exporter
```
docker buildx build --push --platform linux/arm64/v8 --tag hesscon/mqtt-exporter:buildx-lastest .
kubectl create configmap mqtt-exporter --from-file=conf
kubectl apply -f mqtt-exporter-deployment.yam 
```

# Sonstiges
```
```

 