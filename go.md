## mac上交叉编译linux可执行文件
CGO_ENABLED=0 GOOS=linux GOARCH=amd64 go build -o main.go