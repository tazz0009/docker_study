# 도커 정리

## 5. 도커 라이프 사이클 명령어

### 5.1 도커 이미지 다운로드와 삭제

```console
# Jenkins 검색
sudo docker search jenkins
sudo docker inspect jenkins

sudo docker pull console/tomcat-8.5
sudo docker rmi console/tomcat-8.5
```

### 5.2 톰캣 컨테이너 생성

```console
sudo docker run -d --name tc tomcat
```

### 5.3 실행중인 컨테이너 확인

```console
sudo docker ps 
```

### 5.4 모든 컨테이너 확인

```console
sudo docker ps -a
```

### 5.5 컨테이너 중지

```console
sudo docker stop [id or name]

# 모든 도커 중지
sudo docker stop `docker ps -a -q`
```

### 5.6 컨테이너 삭제

```console
sudo docker rm [id or name]

# 모든 도커 삭제
sudo docker rm `docker ps -a -q`
```

### 5.7 이미지 삭제

```console
sudo docker rmi nginx
sudo docker rmi nginx -f
```

## 6. 이미지 비밀: 레이어

### 6.2 도커 이미지 정보 확인

```console
sudo docker pull nginx
sudo docker inspect nginx
```

### 6.3 도커 이미지 저장소 위치 확인

```console
sudo docker info
sudo -i
cd /var/lib/docker/overlay2

# 용량 확인
/var/lib/docker#du -sh image
/var/lib/docker#du -sh overlay2

```

### 6.4 레이어 저장소 확인

```console

```

### 6.5 도커 히스토리 확인

```console
sudo docker history nginx
```

## 7. 도커의 유용한 명령어

### 7.1 포트포워딩으로 톰캣 실행하기

```console
sudo docker run -d --name tc -p 80:8080 tomcat
```

### 7.2 컨테이너 내부 셸 실행

```console
sudo docker exec -it tc /bin/bash
```

### 7.3 컨테이너 로그 확인

```console
sudo docker logs tc 
```

### 7.4 호스트 및 컨테이너 간 파일 복사

```console
sudo docker cp <path> <to container>:<path>
sudo docker cp <from container>:<path> <path>
sudo docker cp <from container>:<path> <to container>:<path>
```

### 7.5 임시 컨테이너 생성

```console
sudo docker run -d -p 80:8080 --rm --name tc tomcat
```

## 8. 실습

```console
# Jenkins 검색
sudo docker search jenkins

# Jenkins를 사용하여 설치
sudo docker pull jenkins
sudo docker inspect jenkins
sudo docker run -d -p 8080:8080 --name jk jenkins

# Jenkins의 초기 패스워드 찾아서 로그인하기
sudo docker exec -it jk cat /path/initPassword
sudo docker logs jk
```

