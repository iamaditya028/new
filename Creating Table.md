#**From Scratch to Creating Table Process**
|S.No| Process to Follow|
|:--------:|:---------:|
|1| Install Docker |
|2| Install MariaDB and create Container |
|3| Create Database in Container|
|4| Run Commands on MariaDB to create Table|


|1||**Install Docker**|
|:------:|:------:|:--------:|
|**S.No**|**Comments**|  **Commands to Run**|
|1|To update |sudo apt-get update|
|2|Install Package|sudo apt-get install \ca-certificates \curl \gnupg \lsb-release|
|3|Add Docker’s official GPG key:|curl -fsSL https://download.docker.com/linux/ubuntu/gpg|
|4||sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg|
|5|Set Stable Repository|echo \"deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \$(lsb_release -cs) stable"|
|6||sudo tee /etc/apt/sources.list.d/docker.list > /dev/null|
|7| update apt package index|sudo apt-get update|
|8|Install Docker Engine|sudo apt-get install docker-ce docker-ce-cli containerd.io|
|9|check status 'active' Highlighted in Green|sudo systemctl status docker|
||Check Link for Commands|https://docs.docker.com/engine/install/ubuntu/|


|2,3||**Install MariaDB and create Container**|
|:--------:|:------:|:--------:|
|**S.No**|**Comments**|  **Commands to Run**|
|1| start dockerd dom. |sudo systemctl start docker|
|2|| sudo gpasswd -a "${USER}" docker|
|3|**If** Problem Occurs run this command, otherwise Skip this Step |sudo chmod 666 /var/run/docker.sock
|4|Image download| docker search mariadb|
|5|Container name & Password|docker run --name mariadbtest -e MYSQL_ROOT_PASSWORD=**ABC** -p 3306:3306 -d docker.io/library/mariadb:10.3|
|6|To Check Container name & Id |docker ps|
|7|To Restart a Container|docker restart your container name|
||For your Password refer row 5 & its highlighted in bold, change it according to self |ABC|



|4||**Run Commands on MariaDB to create Table**|
|:--------:|:------:|:--------:|
|**S.No**|**Comments**|  **Commands to Run**|
|1|Get Into Container **for container_id go table (2,3) and row 5**|docker exec -it **Your Container_id** /bin/bash|
|2|Enter Your Password **refer last Comment** and run this command|mysql -u root -p|
|3|Create Database|create database **database_name**;|
|4|To Enter Database|use **database_name**|
|5|Create Table|create table table_name(att,subatt,testcase etc);
|6|To Enter Data in Table|insert into table_name values( row wise values);
|7|to view table|select * from table_name;|
||Providing link to understand creating table in MariaDB|https://youtu.be/qAM6ElROwqQ| 



#**Hope it Helps**!
