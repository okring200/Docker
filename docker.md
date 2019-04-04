# DOCKER




## Docker란

컨테이너 기반의 오픈소스 가상화 플랫폼

컨테이너 : 격리된 공간에서 프로세스가 동작하는 기술. 가상화 기술의 하나지만 기존방식과의 차이가 존재. 기존의 방법은 주로 os를 가상화. -> 프로세스를 격리하는 방식으로 바뀜

이미지: 컨테이너 실행에 필요한 파일과 설정값등을 포함. 상태값을 가지지 않고 변하지 않음. docker 이미지는 [Docker hub](https://hub.docker.com) 에 등록하거나 [Docker Registry](https://docs.docker.com/registry/) 저장소를 만들어 관리 가능.

## Docker 설치

맥에서의 설치 방법: [docker 홈페이지](https://docs.docker.com) 에서 설치 가능

Docker 실행시 

![docker-menubar](./images/docker-menubar.png)

메뉴바에 고래 모양이 나타나며, 실행 완료면 사라짐  <br/>

정상설치 되었는지 확인을 위한 명령어<br /> `docker version`<br/ > 아래와 같이 Client&Server 정보 출력되면 설치 완료

```
Client: Docker Engine - Community
 Version:           18.09.2
 API version:       1.39
 Go version:        go1.10.8
 Git commit:        6247962
 Built:             Sun Feb 10 04:12:39 2019
 OS/Arch:           darwin/amd64
 Experimental:      false

Server: Docker Engine - Community
 Engine:
  Version:          18.09.2
  API version:      1.39 (minimum version 1.12)
  Go version:       go1.10.6
  Git commit:       6247962
  Built:            Sun Feb 10 04:13:06 2019
  OS/Arch:          linux/amd64
  Experimental:     false
```

> Client: Docker Engine - Community<br />Version:           18.09.2<br/>API version:       1.39<br/>Go version:        go1.10.8<br/>Git commit:        6247962<br/>Built:             Sun Feb 10 04:12:39 2019<br/> OS/Arch:           darwin/amd64<br/> Experimental:      false
>
> Server: Docker Engine - Community<br/> Engine:<br/>  Version:          18.09.2<br/>  API version:      1.39 (minimum version 1.12)<br/>  Go version:       go1.10.6<br/>  Git commit:       6247962<br/>  Built:            Sun Feb 10 04:13:06 2019<br/>  OS/Arch:          linux/amd64<br/>  Experimental:     false







