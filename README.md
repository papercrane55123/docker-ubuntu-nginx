# create Ubuntu-nginx image


# How to
1) ubuntu 이미지를 설치한다.
https://hub.docker.com/_/ubuntu
```sh
$ sudo docker pull ubuntu:latest
Using default tag: latest
latest: Pulling from library/ubuntu
57c139bbda7e: Pull complete
Digest: sha256:e9569c25505f33ff72e88b2990887c9dcf230f23259da296eb814fc2b41af999
Status: Downloaded newer image for ubuntu:latest
docker.io/library/ubuntu:latest
```

2) 컨테이너 만들기
```sh
$ sudo docker run -d -it --name ubuntu-nginx ubuntu
```
중요한 점은 -it 옵션을 넣어 터미널 작업되도록 만들어야 한다는 점이다. 우분투로 서버를 띄울 것이 아니기 때문에 포트번호는 필요없다.

3) 컨테이너 접속
```sh
$ sudo docker exec -it ubuntu-nginx bash
```
4) 우분투 컨테이너 터미널에서 nginx 설치
https://nginx.org/en/linux_packages.html#Ubuntu
download와 install은 차이가 있다. 터미널에서 적용시키려면 install 가이드를 살펴봐야 한다(물론 download로도 가능하다).
```sh
$ sudo apt install curl gnupg2 ca-certificates lsb-release ubuntu-keyring
$ sudo apt update
$ sudo apt install nginx
```



