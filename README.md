# 도커 정리

## 5. 도커 라이프 사이클 명령어

### 5.1 도커 이미지 다운로드와 삭제

```console
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
```

### 5.6 컨테이너 삭제

```	console
sudo docker rm [id or name]
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
