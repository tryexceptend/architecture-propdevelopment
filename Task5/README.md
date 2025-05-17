## Запуск кубернетиса

Запуск minikube

```bash
minikube start --vm-driver=virtualbox --addons=metrics-server --no-vtx-check --memory=8192 --cpus=4
```

Активация метрик

```bash
minikube addons enable metrics-server
```

Запуск сервисов

```bash
kubectl run front-end-app --image=nginx --labels role=front-end --expose --port 80
kubectl run back-end-api-app --image=nginx --labels role=back-end-api --expose --port 90
kubectl run admin-front-end-app --image=nginx --labels role=admin-front-end --expose --port 81
kubectl run admin-back-end-api-app --image=nginx --labels role=admin-back-end-api --expose --port 91
```

Применение политик

```bash
kubectl apply -f non-admin-api-allow.yaml
```
