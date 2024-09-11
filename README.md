# OTUS-MSA

## ДЗ-5. Прометей и Графана

1. Должен быть установлен [https://helm.sh/docs/intro/install/](helm)
2. Выполнить пункты 1-3,5 из ДЗ-3
3. Выполнить команду
   ```shell
     helm install stack prometheus-community/kube-prometheus-stack -f ./appChart/prometheus.yaml
   ``` 
4. Выполнить команду
   ```shell
     helm install myapp appChart
   ```
5. Выполнить команду 7 из ДЗ-3
6. Выполнить команду, после которой можно перейти в интерфейс Прометея по роуту http://localhost:9090 (в моем
   случае http://arch.homework:9090)
   ```shell
      kubectl port-forward service/prometheus-operated  9090
   ```
7. Выполнить команду, после которой можно перейти в интерфейс Графаны по роуту http://localhost:9009 (в моем
   случае http://arch.homework:9009), 9009 выбран, т.к. он свободен у меня на машине

   ```shell
      kubectlkubectl port-forward service/stack-grafana  9009:80
   ```
8. Инструкции есть в директории [docs](docs)
9. Звездочку не смог выполнить, (

## ДЗ-4. Приложение в кубер на локальной машине

1. Должен быть установлен [https://helm.sh/docs/intro/install/](helm)
2. Выполнить пункты 1-3,5 из ДЗ-3
3. Выполнить команду
   ```shell
     helm install myapp appChart
   ```
4. Выполнить команду 7 из ДЗ-3
5. Выполнить запросы через постман (файлы коллекции и
   среды
   находятся [тут](postman)).
6. Выполнить удаление приложения командой
   ```shell
     helm delete myapp
   ```

## ДЗ-3. Приложение в кубер на локальной машине

### Подготовка окружения для запуска.

#### Установка

1. Склонировать репозиторий в текущую директорию
    ```shell
    git clone https://github.com/Vanzhin/otus.git
    ```

2. Установить [minikube](https://kubernetes.io/ru/docs/tasks/tools/install-minikube/).

3. Запустить minikube
    ```shell
    minikube start
    ```
4. Перейти в папку [manifest](manifest).
   ```shell
   cd manifest/
   ```
5. Подключить аддон ingress.
   ```shell
   minikube addons enable ingress
   ```
6. Применить манифесты.
   ```shell
   kubectl apply -f.
   ```
7. Для работы на локальной машине, необходимо, чтобы в /etc/hosts был прописан "127.0.0.1 arch.homework", также
   выполнить команду
   ```shell
   minikube tunnel
   ```
8. Перейти в браузер и выполнить запрос [health](http://arch.homework/health/) или через постман (файлы коллекции и
   среды
   находятся [тут](postman)).
9. Для удаления приложения выполнить команду из папки [manifest](manifest).
   ```shell
    kubectl delete -f .
   ```

## ДЗ-2. Контейнер для приложения Симфони 7

Репозиторий содержит Докерфайл для создания образа приложения (docker/Dockerfile).

   