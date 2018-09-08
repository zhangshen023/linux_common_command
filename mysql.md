# 启动mysql 

docker run --name mysql5.7.23 -p 3306:3306 -v /etc/localtime:/etc/localtime -v /data/mysql/datadir:/var/lib/mysql -v /data/mysql/conf.d:/etc/mysql/conf.d -e MYSQL_ROOT_PASSWORD=123456 -d --restart=always mysql:5.7.23

# mysql 主myqsl容器

sudo docker run -d -e MYSQL_ROOT_PASSWORD=123456 --name mysql-master  -v /Users/shen/Documents/docker-mysql-data/mysql-master:/var/lib/mysql -v /Users/shen/Documents/docker-mysql-data/my-master.cnf:/etc/mysql/my.cnf -p 3307:3306 mysql:5.7.23

# mysql 从myqsl容器
sudo docker run -d -e MYSQL_ROOT_PASSWORD=123456 --name mysql-slave1 -v /Users/shen/Documents/docker-mysql-data/mysql-slave1:/var/lib/mysql -v /Users/shen/Documents/docker-mysql-data/my-slave1.cnf:/etc/mysql/my.cnf -p 3308:3306 mysql:5.7.23

# mysql分配复制权限
grant replication slave on *.* to 'slave'@'%' identified by 'slave';
flush privileges;
show master status;

# 从mysql容器配置
change master to master_host='172.17.0.2',master_user='slave',master_password='slave',
master_log_file='mysql-bin.000004',master_log_pos=1160,master_port=3306;
start slave;
show slave status \G

