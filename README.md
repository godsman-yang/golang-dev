# golang 개발환경

- docker golang
  - https://hub.docker.com/_/golang

#### 개발환경으로 접속

```
# in wsl2
$ cd ~/work/docker-dev
$ pwd
/home/shyang/work/golang-dev

$ docker run -it --rm -v "$PWD":/go/src/app -w /go/src/app golang:1.14 bash
# pwd
/go/src/app

# go get -d -v ./...
# go run hello-world.go
```

#### 주요 명령어

```
$ docker build -t my-golang-app .
$ docker run -it --rm --name my-running-app my-golang-app

$ docker run --rm -v "$PWD":/usr/src/myapp -w /usr/src/myapp golang:1.14 go build -v
$ docker run --rm -v "$PWD":/usr/src/myapp -w /usr/src/myapp golang:1.14 make

# cross-compile for windows amd64
$ docker run --rm -v "$PWD":/usr/src/myapp -w /usr/src/myapp -e GOOS=windows -e GOARCH=amd64 golang:1.14 go build -v
```
