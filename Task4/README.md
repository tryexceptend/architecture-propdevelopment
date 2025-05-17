# Запуск кубернетиса

Запуск minikube

```bash
minikube start --vm-driver=virtualbox --addons=metrics-server --no-vtx-check --memory=8192 --cpus=4
```

Активация метрик

```bash
minikube addons enable metrics-server
```

Для запуска дашборда в другом терминале:

```bash
minikube dashboard
```

# Настройка неймспейсов и ролей

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

# Генерация пользователей

Пользователь из группы Разработчики домена Client

```bash
openssl genrsa -out developer.key 2048

openssl req -new -key developer.key -out developer.csr -subj "/CN=developer"

openssl x509 -req -in developer.csr -CA .minikube\ca.crt -CAkey .minikube\ca.key -CAcreateserial -out developer.crt -days 500

kubectl config set-credentials developer --client-certificate=developer.crt --client-key=developer.key

kubectl config set-context developer-context --cluster=minikube --user=developer --namespace=client
```

Пользователь из группы DevOps инжинеры

```bash
openssl genrsa -out devops-admin.key 2048

openssl req -new -key devops-admin.key -out devops-admin.csr -subj "/CN=devops-admin"

openssl x509 -req -in devops-admin.csr -CA .minikube\ca.crt -CAkey .minikube\ca.key -CAcreateserial -out devops-admin.crt -days 500

kubectl config set-credentials devops-admin --client-certificate=devops-admin.crt --client-key=devops-admin.key

kubectl config set-context devops-admin-context --cluster=minikube --user=devops-admin
```

