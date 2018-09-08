# 启动一个mongo
docker pull mongo

linux: docker run -p 27017:27017 -v /root/data/mongo:/data/db -d --restart=always mongo 

windows: docker run -p 27017:27017 -v /f/mongo/data:/data/db -d mongo

# 启动一个swagger-editor 
docker pull swaggerapi/swagger-editor

docker run --rm -p 80:8080 swaggerapi/swagger-editor

# swagger-ui.html
docker pull swaggerapi/swagger-ui

docker run -p 80:8080 swaggerapi/swagger-ui

# 启动nginx
docker pull nginx

docker run --name nginx -d -p 8001:80 --restart=always -v /root/data/nginx/file:/home/userfile -v /root/data/nginx/conf:/etc/nginx/conf.d nginx

# mysql 主myqsl容器

sudo docker run -d -e MYSQL_ROOT_PASSWORD=123456 --name mysql-master  -v /Users/shen/Documents/docker-mysql-data/mysql-master:/var/lib/mysql -v /Users/shen/Documents/docker-mysql-data/my-master.cnf:/etc/mysql/my.cnf -p 3307:3306 mysql:5.7.23

# mysql 从myqsl容器
sudo docker run -d -e MYSQL_ROOT_PASSWORD=123456 --name mysql-slave1 -v /Users/shen/Documents/docker-mysql-data/mysql-slave1:/var/lib/mysql -v /Users/shen/Documents/docker-mysql-data/my-slave1.cnf:/etc/mysql/my.cnf -p 3308:3306 mysql:5.7.23


# 启动mysql

docker run --name mysql5.7.23 -p 3306:3306 -v /etc/localtime:/etc/localtime -v /data/mysql/datadir:/var/lib/mysql -v /data/mysql/conf.d:/etc/mysql/conf.d -e MYSQL_ROOT_PASSWORD=123456 -d --restart=always mysql:5.7.23

# 启动redis
docker run --name redis-test -p 6379:6379 -d --restart=always redis:latest redis-server --appendonly yes --requirepass "your passwd"
