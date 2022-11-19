University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)

Year: 2022/2023

Group: K4110c

Author: Rybkin Yan Sergeevich

Lab: Lab4

Date of create: 30.09.2022

Date of finished: 18.11.2022

## Пояснение: ip различаются тк в течение работы возникало большое количество ошибок (вероятно из-за несостыковки версий и тп), поэтому приходилось переделывать, и в итоге работа выглядит как солянка из скриншотов и манифестов

## 1. Сначала используя оригинальное руководство добавим две ноды и установим плагин calico, и всё это при запуске minikube

```
minikube start --nodes 2 --cni calico --kubernetes-version=v1.25.2
```

## Проверим ноды и поды:

```
kubectl get nodes 
kubectl get pods -A
```

## Видим что вторая нода m02 создалась, как и поды.

![Снимок экрана 2022-11-18 в 2 40 31 PM](https://user-images.githubusercontent.com/111576120/202697654-97ca89fb-bd8e-4399-aba7-05bd511e9000.png)

## 2. Добавим манифест calico с подами

```
kubectl apply -f calicoctl.yaml
```

![Снимок экрана 2022-11-18 в 2 46 57 PM](https://user-images.githubusercontent.com/111576120/202698399-0975afb5-0815-453a-890d-6fab9436ef31.png)

## 3. Добавим манифест IPpool с двумя ip адрессами

```
kubectl apply -f ippool.yaml
```

## Чтобы проверить ip'шники, введем команду:

```
kubectl get ippools -o wide
```

![Снимок экрана 2022-11-18 в 3 00 47 PM](https://user-images.githubusercontent.com/111576120/202700685-389bacb6-e7c5-46db-a1d3-edeacfd1cdac.png)

## 4. Добавим манифесты с сервисом, конфигмапой и репликасетем (деплоймент)

![Снимок экрана 2022-11-18 в 2 59 45 PM](https://user-images.githubusercontent.com/111576120/202700804-b007c03b-00e9-46a4-ae49-c839e9430c09.png)

## 5. Проверим ссылку

## Для этого необходимо ввести следующую команду:

```
minikube service frontend 
```

## P.S. название сервиса брать указанное из манифеста с сервисом!

![198068655-2ae9a9c5-55fb-4a5d-b015-feb3bd2ec265](https://user-images.githubusercontent.com/111576120/202743541-4630cc07-e3e4-4a86-b121-f7c8691ecaf7.png)

## При перезагрузке страницы ip меняется, соответствуя ip pools, хеш контенернейма также изменяется

## 6. Прозвоним айпишники друг у друга

 ```
 kubectl get pods -o wide
 minikube kubectl -- exec <название пода из списка выше> -- sh
 ```

## Далее откроется строка "frontend", в ней мы введем ping и второй айпишник из списка с флагом -c и числом 5 (5 пакетов передать)

![Снимок экрана 2022-11-18 в 6 46 21 PM](https://user-images.githubusercontent.com/111576120/202744828-3e8d46aa-32f1-45bd-95ff-ba214eec9237.png)

## 5 пакетов передано, 5 получено - потерь (loss) нет

## Моя структура k8s

![123](https://user-images.githubusercontent.com/111576120/202751355-9040f536-b8a4-4856-9047-ab7d6136b71f.png)

