# Домашнее задание

## Инфраструктурные паттерны

ссылки для выполнения задания
https://github.com/evgnep/msa/tree/master/prometheus

https://kubernetes.github.io/ingress-nginx/user-guide/monitoring/

Описание/Пошаговая инструкция выполнения домашнего задания:
Инструментировать сервис из прошлого задания метриками в формате Prometheus с помощью библиотеки для вашего фреймворка и ЯП.

Сделать дашборд в Графане, в котором были бы метрики с разбивкой по API методам:

Latency (response time) с квантилями по 0.5, 0.95, 0.99, max
RPS
Error Rate - количество 500ых ответов

Добавить в дашборд графики с метрикам в целом по сервису, взятые с nginx-ingress-controller:
Latency (response time) с квантилями по 0.5, 0.95, 0.99, max
RPS
Error Rate - количество 500ых ответов

Настроить алертинг в графане на Error Rate и Latency.

На выходе должно быть:

0) скриншоты дашборды с графиками в момент стресс-тестирования сервиса. Например, после 5-10 минут нагрузки.

1) json-дашборды.

Задание со звездочкой

Используя существующие системные метрики из кубернетеса, добавить на дашборд графики с метриками:
Потребление подами приложения памяти
Потребление подами приолжения CPU

Инструментировать базу данных с помощью экспортера для prometheus для этой БД.
Добавить в общий дашборд графики с метриками работы БД.