# sf-pract-12.5

Выполнение практикума 12.5

Пример запуска:

Требуется машина с установленным Docker.

git clone https://github.com/jkL-snk/sf-pract-12.5.git
cd ./sf-pract-12.5
docker build -t my-jenkins-image .
docker run --name my-jenkins-container --rm --detach --publish 8080:8080 --publish 50000:50000 my-jenkins-image:1
docker exec my-jenkins-container cat /var/jenkins_home/secrets/initialAdminPassword

Далее зайти в браузере по адресу <ip-адрес машины:8080>, для авторизации ввести полученный от последней команды пароль

Создать новый Item: задачу со свободной конфигурацией. Задайте выполнение скрипта sh: mysql --user rfamro --host mysql-rfam-public.ebi.ac.uk --port 4497 --database Rfam < /opt/sql/select-all-rats.sql
