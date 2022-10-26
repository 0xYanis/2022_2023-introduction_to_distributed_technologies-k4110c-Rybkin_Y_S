University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)

Year: 2022/2023

Group: K4110c

Author: Rybkin Yan Sergeevich

Lab: Lab1

Date of create: 30.09.2022

Date of finished: 26.10.2022

---
## 1. Docker and minikube installed successfully.

## 2. Launch minikube
![Снимок экрана 2022-10-26 в 2 46 37 PM](https://user-images.githubusercontent.com/111576120/198018235-e220c30c-7649-4c2c-9005-28282290b6d8.png)

## 3. Launch manifest
![Снимок экрана 2022-10-26 в 3 58 21 PM](https://user-images.githubusercontent.com/111576120/198032865-1c0c2cfa-5876-4dd1-95c3-82c7e4a5ed86.png)

## 4. Checking logs 
```
minikube kubectl -- logs service/vault
```

## 5. Result
![Снимок экрана 2022-10-26 в 4 12 01 PM](https://user-images.githubusercontent.com/111576120/198034855-1512770d-72d2-468d-b55b-fa96e1c36c74.png)

# What happened?
Pod is a group of docker containers, a core kubernetes module that will always run together on the same host, like a separate logical machine with its own ip address, network name, process, etc.

In this work, docker and minicubes were installed, the 'voult' pod was deployed, a token was received from the logs to enter the service, the work was completed successfully.

Под это группа контейнеров докера, основной модуль кубернетс, которые всегда будут работать вместе на одном рабочем узле, подобный отдельной логической машине с собственным айпи адресом, сетевым именем, процессом и тд.

В данной работе были установлены докер и миникубс, развернут под 'vault', по логам был получен токен для входа на сервис, работа выполнена успешно.
