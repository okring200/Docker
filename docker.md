# DOCKER




## 1. Docker 란

컨테이너 기반의 오픈소스 가상화 플랫폼

**컨테이너** 

격리된 공간에서 프로세스가 동작하는 기술. 가상화 기술의 하나지만 기존방식과의 차이가 존재. 기존의 방법은 주로 os를 가상화. -> 프로세스를 격리하는 방식으로 바뀜

**이미지** 

컨테이너 실행에 필요한 파일과 설정값등을 포함. 상태값을 가지지 않고 변하지 않음. docker 이미지는 [Docker hub](https://hub.docker.com) 에 등록하거나 [Docker Registry](https://docs.docker.com/registry/) 저장소를 만들어 관리 가능.

## 2. Docker 설치

맥에서의 설치 방법: [docker 홈페이지](https://docs.docker.com) 에서 설치 가능

Docker 실행시 

![docker-menubar](./images/docker-menubar.png)

메뉴바에 고래 모양이 나타나며, 실행 완료면 사라짐  <br/>

정상설치 되었는지 확인을 위한 명령어<br /> `docker version` 

아래와 같이 Client&Server 정보 출력되면 설치 완료

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

## 3. Docker 실행

docker를 실행하는 명령어는 다음과 같다.<br /> `docker run [OPTIONS] IMAGE[:TAG|@DIGEST] [COMMAND] [ARG..]`

### 3-1. Ubuntu 설치

 `docker run ubuntu:16.04`

`run` 명령어를 사용하면 사용할 이미지가 저장되어 있는지 확인하고 없다면 다운로드를 한 후 컨테이너를 생성하고 실행하게 됩니다.

```
Unable to find image 'ubuntu:16.04' locally
16.04: Pulling from library/ubuntu
34667c7e4631: Pull complete 
d18d76a881a4: Pull complete 
119c7358fbfc: Pull complete 
2aaf13f3eff0: Pull complete 
Digest: sha256:58d0da8bc2f434983c6ca4713b08be00ff5586eb5cdff47bcde4b2e88fd40f88
Status: Downloaded newer image for ubuntu:16.04
```

위 예제의 경우 우분투 이미지 저장 후 컨테이너를 정상적으로 실행하였습니다. 실행 후 명령어를 전달하지 않았기 때문에 자동으로 컨테이너 생성 직후 종료됩니다.

`bin/bash` 명령어를 통해 컨테이너를 실행해 보겠습니다.

```
naminje-ui-MacBookPro:docker 10058$ docker run --rm -it ubuntu:16.04 /bin/bash
root@3a737fb9f0da:/# cat /etc/issue
Ubuntu 16.04.6 LTS \n \l

root@3a737fb9f0da:/# ls
bin   dev  home  lib64  mnt  proc  run   srv  tmp  var
boot  etc  lib   media  opt  root  sbin  sys  usr
```

컨테이너 내부에서 bash shell을 실행하고 커맨드 입력을 위해 `-it` 옵션을 주었고, 프로세스 종료 시 자동 컨테이너 삭제를 위한 `--rm` 옵션을 주었습니다.

### 3-2. Redis 설치

redis는 메모리 기반 key/value store입니다.

```
naminje-ui-MacBookPro:docker 10058$ telnet localhost 1234
Trying ::1...
Connected to localhost.
Escape character is '^]'.
set mykey hello
+OK
get mykey
$5
hello
```

`-d` 옵션을 주어 컨테이너를 백그라운드 모드로 실행, `-p` 옵션을 통하여 호스트의 `1234포트` 를 컨테이너의 `6789포트` 로 연결합니다. 호스트 포트만 다르게 하면 하나의 서버에 여러개의 redis 서버를 띄울수 있습니다.

<details>
  <summary> Telnet Install for Mac</summary></br>
  <code>
    /usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)" </code></br>
  위의 명령어를 이용하여 brew 다운로드합니다.</br>
	<code>brew tap theeternalsw0rd/telnet</code></br>
	<code>brew install telnet</code></br>
	위 명령어를 이용하여 telnet 설치를 완료합니다.</br></br>
  *<code>/usr/local/share/man/man7 is not writable.</code>오류 시</br>
  <code>sudo chown -R $(whoami) /usr/local</code> 명령어를 이용하여 해결
</details>

## Docker 기본 명령어









