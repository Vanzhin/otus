# OTUS-MSA

## ДЗ-2. Контейнер для приложения Симфони 7

Репозиторий содержит Докерфайл для создания образа приложения (docker/Dockerfile).

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
8. Перейти в браузер и выполнить запрос [health](http://arch.homework/health/) или через постман (файлы коллекции и среды
   находятся [тут](postman)).
9. Для удаления приложения выполнить команду из папки [manifest](manifest).
   ```shell
    kubectl delete -f .
   ```
   