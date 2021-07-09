# ?Docker?
![docker](img/docker-logo.png)
- **Docker(��Ŀ)�� : �����̳� ����� ���¼ҽ� ����ȭ �÷����̴�.**
<br>

![vm-docker](img/vm-vs-docker.png)<br>
���� ����ȭ����� ��ü OS�� �Ź� ���� ��ġ�ؾ� �ϰ� �ʿ��� ȯ���� �������־�� �ϴ� �������� �ְ�, ���� ������ ���� �ʿ�� �ϰ� ���ſ���. �ݸ� ��Ŀ�� �� �׸��� ���� ���ʿ��� ������带 ���̰� ��Ŀ �������� �� �ʿ��� ���μ���(���α׷�)���� ����ȭ��Ų��. �׷��� ��Ŀ�� ������ ����ȭ ������� ������ �� �ʿ��� �ý��� ���ҽ����� ����Ѵ�.<br>


![img](img/1_p8k1b2DZTQEW_yf0hYniXw.png)<br>
��Ŀ�� �̹����� ����� ���� `Dockerfile`�̶�� ���Ͽ� ��ü DSL(Domain-Specific-Language) �� �̿��Ͽ� �̹��� ���� ������ �����ϴ�. �̹����� �����̳� ���࿡ �ʿ��� ���ϰ� ������ ���� �����ϰ� �ִ� ���Դϴ�. �����̳ʴ� �ݸ��� �������� ���μ����� �����ϴ� ����Դϴ�. ����ڴ� �� �����̳ʸ� ��������ν� OS�� ����ȭ�Ͽ� ����� �� �ְ� �˴ϴ�.

## ��Ŀ ��ġ
> https://subicura.com/2017/01/19/docker-guide-for-beginners-2.html
> https://ccss17.github.io/ProgrammerBase/docker/

## ��Ŀ ���� ����

(1) �����̳� �����ϰ� �����ϱ�

```shell
$ docker run -it ccss17/ubuntu
```
`docker run` ��ɾ�� `ccss17/ubuntu` �̹����� ���ÿ� �ִ��� ã��, ������ ��Ŀ ��꿡�� ã�Ƽ� �ٿ�ε��� ���� ������� �����ִ� ��ɾ��Դϴ�.
- `docker run <OPTION> <IMAGE>` : �̹����� �ٿ�ε��ϰ� �����̳ʷ� �����Ѵ�
  - �ɼ� `-it` �� �͹̳η� �����̳ʿ� ������ �� �ְ� ���ִ� �ɼ�
  - �ɼ� `--rm`�� ������ �����̳ʸ� �������� �� �ڵ����� �������ִ� �ɼ� 

(2) �����̳ʿ� �̹��� ���� Ȯ���ϱ�

```shell
$ docker images
REPOSITORY      TAG       IMAGE ID       CREATED        SIZE
ccss17/ubuntu   latest    42f477a22c77   4 months ago   938MB
```
�� ��ɾ�� ���ÿ� �ٿ�ε�� ��Ŀ �̹����� ����� ������ݴϴ�.
- `docker images` : ���ÿ� �ٿ�ε�� ��Ŀ �̹��� ����� ����Ѵ�.
  
```shell
$ docker ps -a
CONTAINER ID   IMAGE           COMMAND       CREATED      STATUS                         PORTS     NAMES
986b4bff3239   ccss17/ubuntu   "/start.sh"   2 days ago   Exited (0) About an hour ago             affectionate_elion
```
`docker ps` �����̳��� ����� ����մϴ�. `-a` �ɼ��� ������ ����� �����̳ʱ��� ��µ˴ϴ�.
- `docker ps <OPTIIONS>` : ��Ŀ �����̳� ����� ����Ѵ�.

(3) �����̳� ������ϱ�
```shell
$ docker start -ai 986b4bff3239
```
�ڿ� `986b4bff3239`�� �����̳� ���̵�ν� ����ڸ��� �ٸ� �� �ֽ��ϴ�.
- `docker start <OPTIONS> <CONTAINER ID>` : �����̳ʸ� �ٽ� �����Ѵ�.
  - �����̳� ���̵� ������ �� �� ������ �ձ��ڸ� �Է��ص� �ǰ� ���� �ߺ��ȴٸ� �α��ڸ� �Է��ص� �˴ϴ�.
  - `-ai` �ɼ����� �����̳ʿ� �����Ͽ� �͹̳ο��� ����� �� �ְ� �˴ϴ�.

(4) �����̳ʿ� �̹��� �����ϱ�
```shell
$ docker rm 986b4bff3239
$ docker rmi ccss17/ubuntu
```
- `docker rm <OPTIONS> <CONTAINER ID>` : �ش� �����̳ʸ� �����Ѵ�.
- `docker rmi <OPTIONS> <CONTAINER>` : �ش� �̹����� �����Ѵ�.