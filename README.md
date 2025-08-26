# Домашнее задание к занятию «Репликация и масштабирование. Часть 1»
---
### Задание 1
`На лекции рассматривались режимы репликации master-slave, master-master, опишите их различия`

При репликации master-slave существует один главный сервер (master), в который идет запись данных, и один или несколько вспомогательных (slave), с которых можно только читать данные. Slave - зеркало мастера.
При репликации master-master все сервера являются одновременно мастерами и слейвами. Запись и чтение данных возможны на любом сервере.

---
### Задание 2
`Выполните конфигурацию master-slave репликации. Приложите скриншоты конфигурации и выполнения работы: состояния и режимы работы серверов`

docker network create replication
docker run --name master --net replication -e  MYSQL_ROOT_PASSWORD=root -p 3307:3306 -d mysql:8.4
docker run --name slave --net replication -e  MYSQL_ROOT_PASSWORD=root -p 3308:3306 -d mysql:8.4

![image1](https://github.com/maninblack802/repo-302/blob/main/img1.png)
![image2](https://github.com/maninblack802/repo-302/blob/main/img2.png)
![image3](https://github.com/maninblack802/repo-302/blob/main/img3.png)
![image4](https://github.com/maninblack802/repo-302/blob/main/img4.png)
![image5](https://github.com/maninblack802/repo-302/blob/main/img5.png)
![image6](https://github.com/maninblack802/repo-302/blob/main/img6.png)
