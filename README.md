# OTUS-MSA

## ДЗ-6. API Gateway

1. Должен быть установлен [https://helm.sh/docs/intro/install/](helm)
2. Склонировать репозиторий в текущую директорию

 ```shell
 git clone https://github.com/Vanzhin/otus.git
 ```
3. Установить [minikube](https://kubernetes.io/ru/docs/tasks/tools/install-minikube/).
4. Запустить minikube
    ```shell
    minikube start
    ```
5. Подключить аддон ingress.
   ```shell
   minikube addons enable ingress
   ```
6. Выполнить команду
   ```shell
     helm install myapp appChart
   ```
8. Для работы на локальной машине, необходимо, чтобы в /etc/hosts был прописан "127.0.0.1 arch.homework", также
   выполнить команду
   ```shell
   minikube tunnel
   ```
9. После запуска приложения должны отрабатывать [роуты](postman/HW6.postman_collection.json)
10. Инструкции есть в директории [docs](docs)
   