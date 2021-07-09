# 🐳Docker🐳
![docker](img/docker-logo.png)
- **Docker(도커)는 : 컨데이너 기반의 오픈소스 가상화 플랫폼이다.**
<br><br>

![vm-docker](img/vm-vs-docker.png)<br>
기존 가상화기술이 전체 OS를 매번 새로 설치해야 하고 필요한 환경을 설정해주어야 하는 불편함이 있고, 저장 공간을 많이 필요로 하고 무거웠다. 반면 도커는 위 그림과 같이 불필요한 오버헤드를 줄이고 도커 엔진으로 꼭 필요한 프로세스(프로그램)만을 가상화시킨다. 그래서 도커는 기존의 가상화 기술보다 빠르고 꼭 필요한 시스템 리소스만을 사용한다.<br>


![img](img/1_p8k1b2DZTQEW_yf0hYniXw.png)<br>
도커는 이미지를 만들기 위해 `Dockerfile`이라는 파일에 자체 DSL(Domain-Specific-Language) 언어를 이용하여 이미지 생성 과정을 적습니다. 이미지는 컨테이너 실행에 필요한 파일과 설정값 등을 포함하고 있는 것입니다. 컨테이너는 격리된 공간에서 프로세스가 동작하는 기술입니다. 사용자는 이 컨테이너를 사용함으로써 OS를 가상화하여 사용할 수 있게 됩니다.
<br><br> 
## 도커 설치
> https://subicura.com/2017/01/19/docker-guide-for-beginners-2.html
> https://ccss17.github.io/ProgrammerBase/docker/

<br> 
## 도커 간단 사용법

(1) 컨테이너 실행하고 종료하기

```shell
$ docker run -it ccss17/ubuntu
```
`docker run` 명령어는 `ccss17/ubuntu` 이미지가 로컬에 있는지 찾고, 없으면 도커 허브에서 찾아서 다운로드한 다음 실행까지 시켜주는 명령어입니다.
- `docker run <OPTION> <IMAGE>` : 이미지를 다운로드하고 컨테이너로 실행한다
  - 옵션 `-it` 는 터미널로 컨테이너에 접속할 수 있게 해주는 옵션
  - 옵션 `--rm`은 생성된 컨테이너를 종료했을 때 자동으로 삭제해주는 옵션 
<br><br>

(2) 컨테이너와 이미지 상태 확인하기

```shell
$ docker images
REPOSITORY      TAG       IMAGE ID       CREATED        SIZE
ccss17/ubuntu   latest    42f477a22c77   4 months ago   938MB
```
이 명령어는 로컬에 다운로드된 도커 이미지의 목록을 출력해줍니다.
- `docker images` : 로컬에 다운로드된 도커 이미지 목록을 출력한다.
  
```shell
$ docker ps -a
CONTAINER ID   IMAGE           COMMAND       CREATED      STATUS                         PORTS     NAMES
986b4bff3239   ccss17/ubuntu   "/start.sh"   2 days ago   Exited (0) About an hour ago             affectionate_elion
```
`docker ps` 컨테이너의 목록을 출렵합니다. `-a` 옵션을 붙히면 종료된 컨테이너까지 출력됩니다.
- `docker ps <OPTIIONS>` : 도커 컨테이너 목록을 출력한다.

<br><br> 
(3) 컨테이너 재실행하기
```shell
$ docker start -ai 986b4bff3239
```
뒤에 `986b4bff3239`은 컨테이너 아이디로써 사용자마다 다를 수 있습니다.
- `docker start <OPTIONS> <CONTAINER ID>` : 컨테이너를 다시 실행한다.
  - 컨테이너 아이디가 구별이 될 수 있으면 앞글자만 입력해도 되고 만약 중복된다면 두글자를 입력해도 됩니다.
  - `-ai` 옵션으로 컨테이너에 접속하여 터미널에서 사용할 수 있게 됩니다.


<br><br> 
(4) 컨테이너와 이미지 삭제하기
```shell
$ docker rm 986b4bff3239
$ docker rmi ccss17/ubuntu
```
- `docker rm <OPTIONS> <CONTAINER ID>` : 해당 컨테이너를 삭제한다.
- `docker rmi <OPTIONS> <CONTAINER>` : 해당 이미지를 삭제한다.
