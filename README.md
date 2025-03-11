# Домашнее задание к занятию "`Базы данных в облаке`" - `Татаринцев Алексей`
---

### Задание 1

`Приведите ответ в свободной форме........`

1. `Создаю кластер по заданию`
```
Создание кластера
Перейдите на главную страницу сервиса Managed Service for PostgreSQL.
Создайте кластер PostgreSQL со следующими параметрами:
класс хоста: s2.micro, диск network-ssd любого размера;
хосты: нужно создать два хоста в двух разных зонах доступности и указать необходимость публичного доступа, то есть публичного IP адреса, для них;
установите учётную запись для пользователя и базы.
Остальные параметры оставьте по умолчанию либо измените по своему усмотрению.

Нажмите кнопку «Создать кластер» и дождитесь окончания процесса создания, статус кластера = RUNNING. Кластер создаётся от 5 до 10 минут.
```
![1](https://github.com/Foxbeerxxx/database_in_cloud/blob/main/img/img1.png)`

![2](https://github.com/Foxbeerxxx/database_in_cloud/blob/main/img/img2.png)`

![3](https://github.com/Foxbeerxxx/database_in_cloud/blob/main/img/img3.png)`


---

### Задание 2

`Приведите ответ в свободной форме........`

1. `Устанавливаем сертификат`
```
mkdir -p ~/.postgresql && \
wget "https://storage.yandexcloud.net/cloud-certs/CA.pem" \
    --output-document ~/.postgresql/root.crt && \
chmod 0600 ~/.postgresql/root.crt
```
2. `Установите зависимости:`

```
sudo apt update && sudo apt install --yes postgresql-client
```

3. `Подключитесь к базе данных:`

```
psql "host=rc1a-w9cqe6tbs1dg70cb.mdb.yandexcloud.net,rc1b-ikzm2sopaxqbavza.mdb.yandexcloud.net \
    port=6432 \
    sslmode=verify-full \
    dbname=db1 \
    user=user1 \
    target_session_attrs=read-write"

```
![4](https://github.com/Foxbeerxxx/database_in_cloud/blob/main/img/img4.png)`

![5](https://github.com/Foxbeerxxx/database_in_cloud/blob/main/img/img5.png)`

![6](https://github.com/Foxbeerxxx/database_in_cloud/blob/main/img/img6.png)`