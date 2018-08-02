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
