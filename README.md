# Домашнее задание к занятию "`Система мониторинга Zabbix`" - `Мешенин Андрей`
###  Задание 1. Установите Zabbix Server с веб-интерфейсом.  
wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-5+debian12_all.deb  
dpkg -i zabbix-release_6.0-5+debian12_all.deb  
apt update  
apt install zabbix-server-pgsql zabbix-frontend-php php8.2-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent  
sudo -u postgres createuser --pwprompt zabbix  
sudo -u postgres createdb -O zabbix zabbix  
zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix  
DBPassword=123  
systemctl restart zabbix-server zabbix-agent apache2  
systemctl enable zabbix-server zabbix-agent apache2  
![zab2](https://github.com/neo-13th/sys-hw-zabbix/assets/150372172/94973eae-7e9b-435e-bb5f-6740cd3f338e)


Задание 2. Установите Zabbix Agent на два хоста.
wget https://repo.zabbix.com/zabbix/6.0/debian/pool/main/z/zabbix-release/zabbix-release_6.0-5+debian12_all.deb
dpkg -i zabbix-release_6.0-5+debian12_all.deb
apt update
apt install zabbix-agent
systemctl restart zabbix-agent
systemctl enable zabbix-agent

![zabserv](https://github.com/neo-13th/sys-hw-zabbix/assets/150372172/12032c48-a782-41b7-afd5-e1e6bf148a95)
![latest 2](https://github.com/neo-13th/sys-hw-zabbix/assets/150372172/210d93ee-4ef4-475b-b1dc-7d737fce7e85)
![zabagent2](https://github.com/neo-13th/sys-hw-zabbix/assets/150372172/e2e9d29b-61b7-4b8d-9f32-76abfa178331)
![zabagent](https://github.com/neo-13th/sys-hw-zabbix/assets/150372172/114e86c9-c3cf-4932-bce0-c4dc93e1dfae)
