## Запуск кубернетиса

Запуск minikube

```bash
minikube start --vm-driver=virtualbox --addons=metrics-server --no-vtx-check --memory=8192 --cpus=4 --authorization-mode=RBAC
```

Активация метрик

```bash
minikube addons enable metrics-server
```

Для запуска дашборда в другом терминале:

```bash
minikube dashboard
```

Создание неймспейсов для разных доменов

```bash
kubectl apply -f namespaces.yaml
```

Создание ролей и кластерный ролей

```bash
kubectl apply -f role.yaml
```

Биндин ролей и кластерных ролей

```bash
kubectl apply -f rolebinding.yaml
```

