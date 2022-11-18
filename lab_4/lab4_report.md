University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Introduction to distributed technologies](https://github.com/itmo-ict-faculty/introduction-to-distributed-technologies)

Year: 2022/2023

Group: K4110c

Author: Rybkin Yan Sergeevich

Lab: Lab4

Date of create: 30.09.2022

Date of finished: 18.11.2022

## 1. Сначала используя оригинальное руководство добавим две ноды в режиме MDC и установим плагин calico

![Снимок экрана 2022-11-18 в 2 40 31 PM](https://user-images.githubusercontent.com/111576120/202697654-97ca89fb-bd8e-4399-aba7-05bd511e9000.png)

## 2. Добавим манифест calico с подами

![Снимок экрана 2022-11-18 в 2 46 57 PM](https://user-images.githubusercontent.com/111576120/202698399-0975afb5-0815-453a-890d-6fab9436ef31.png)

## 3. Добавим манифест IPpool

![Снимок экрана 2022-11-18 в 3 00 47 PM](https://user-images.githubusercontent.com/111576120/202700685-389bacb6-e7c5-46db-a1d3-edeacfd1cdac.png)

## 4. Добавим манифесты с сервисом, конфигмапой и репликасетем (деплоймент)

![Снимок экрана 2022-11-18 в 2 59 45 PM](https://user-images.githubusercontent.com/111576120/202700804-b007c03b-00e9-46a4-ae49-c839e9430c09.png)

## 5. Проверим ссылку

![198068655-2ae9a9c5-55fb-4a5d-b015-feb3bd2ec265](https://user-images.githubusercontent.com/111576120/202743541-4630cc07-e3e4-4a86-b121-f7c8691ecaf7.png)

при перезагрузке страницы ip меняется, соответствуя ip pools, хеш контенернейма также изменяется

## 6. Прозвоним айпишники друг у друга

![Снимок экрана 2022-11-18 в 6 46 21 PM](https://user-images.githubusercontent.com/111576120/202744828-3e8d46aa-32f1-45bd-95ff-ba214eec9237.png)

Пояснение: ip различаются тк в течение работы возникало большое количество ошибок (вероятно из-за несостыковки версий и тп), поэтому приходилось переделывать

## Моя структура k8s

![202443182-68309218-69a6-4c6e-af87-82b52166bad2](https://user-images.githubusercontent.com/111576120/202751236-961408af-6c92-4186-b917-88366513e87b.png)
