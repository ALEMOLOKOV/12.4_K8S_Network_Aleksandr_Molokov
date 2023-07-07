# 12.4_K8S_Network_Aleksandr_Molokov

### Задание 1. Создать Deployment и обеспечить доступ к контейнерам приложения по разным портам из другого Pod внутри кластера

1. Создать Deployment приложения, состоящего из двух контейнеров (nginx и multitool), с количеством реплик 3 шт.
2. Создать Service, который обеспечит доступ внутри кластера до контейнеров приложения из п.1 по порту 9001 — nginx 80, по 9002 — multitool 8080.
3. Создать отдельный Pod с приложением multitool и убедиться с помощью `curl`, что из пода есть доступ до приложения из п.1 по разным портам в разные контейнеры.
4. Продемонстрировать доступ с помощью `curl` по доменному имени сервиса.
5. Предоставить манифесты Deployment и Service в решении, а также скриншоты или вывод команды п.4.

## Ответ

#### Deployment - ![Deployment](https://github.com/ALEMOLOKOV/12.4_K8S_Network_Aleksandr_Molokov/blob/bbf1fe9c87c4e4358a9faf2151f9a062db1ae73d/deployment.yaml)

#### Service - ![Service](https://github.com/ALEMOLOKOV/12.4_K8S_Network_Aleksandr_Molokov/blob/bbf1fe9c87c4e4358a9faf2151f9a062db1ae73d/service.yaml)

![1 2 service](https://github.com/ALEMOLOKOV/12.4_K8S_Network_Aleksandr_Molokov/assets/109212419/5dfb9913-10b5-4c33-be76-bb33cac56a9a)

#### Pod - ![Pod](https://github.com/ALEMOLOKOV/12.4_K8S_Network_Aleksandr_Molokov/blob/bbf1fe9c87c4e4358a9faf2151f9a062db1ae73d/pod.yaml)

![1 1 pods and curl](https://github.com/ALEMOLOKOV/12.4_K8S_Network_Aleksandr_Molokov/assets/109212419/022a3b15-c142-42fc-be9c-785ebfc3cd79)

### Curl

#### Между подами

![1 1 pods and curl](https://github.com/ALEMOLOKOV/12.4_K8S_Network_Aleksandr_Molokov/assets/109212419/aec2be7b-3453-421b-9a80-c8f120191bcf)

#### Service порты 9001 и 9002

![1 2 service port 9001](https://github.com/ALEMOLOKOV/12.4_K8S_Network_Aleksandr_Molokov/assets/109212419/9f7e9945-291b-46ca-b097-051172de6274)

![1 2 service port 9002](https://github.com/ALEMOLOKOV/12.4_K8S_Network_Aleksandr_Molokov/assets/109212419/8079da0c-a4ca-4b0f-a1e7-ed24cb8db986)


### Проверка доступа по доменому имени сервиса

![1 4 service dns name](https://github.com/ALEMOLOKOV/12.4_K8S_Network_Aleksandr_Molokov/assets/109212419/4f51d0ac-9ce5-4f02-958e-82916cb8a557)

![1 4 curl service dns](https://github.com/ALEMOLOKOV/12.4_K8S_Network_Aleksandr_Molokov/assets/109212419/94d1c1b9-de40-498e-a628-13cc6b6567f8)

------

### Задание 2. Создать Service и обеспечить доступ к приложениям снаружи кластера

1. Создать отдельный Service приложения из Задания 1 с возможностью доступа снаружи кластера к nginx, используя тип NodePort.
2. Продемонстрировать доступ с помощью браузера или `curl` с локального компьютера.
3. Предоставить манифест и Service в решении, а также скриншоты или вывод команды п.2.

## Ответ

