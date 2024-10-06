# 실습 프로그램 설치 

교육에 앞서 실습에 필요한 프로그램을 설치합니다.   

<br/>

1. Docker 설치

2. Docker compose 설치

3. openshift console 설치

4. Git 설치

5. Helm 설치

6. GitHub 계정 생성

7. DockerHub 계정 생성

8. k3s 설치

<br/>


## Docker 설치

<br/>

> 도커 설치 (맥) : https://velog.io/@eunhye_/Docker-Mac-OS%EC%97%90-Docker-%EC%84%A4%EC%B9%98

<br/> 


### 도커 버전 확인

<br/>

```bash
docker --version
```
<img src="./assets/docker_version.png" style="width: 60%; height: auto;"/>

<br/>

### 도커 이미지 다운로드 및 실행하기

<br/>

```bash
docker run hello-world
```
 
<img src="./assets/docker_run_world.png" style="width: 80%; height: auto;"/>


<br/>

## Docker compose 설치.

<br/>

docker compose를 설치 합니다.  

<br/>

도커 컴포즈 버전을 확인하고 아래와 같이 나오면 정상적으로 설치가 된 것이다.

<br/>

```bash
docker-compose --version
```  

<br/>

<img src="./assets/docker_compose_version.png" style="width: 60%; height: auto;">  

<br/>

## openshift console 설치

<br/>

아래와 같이 openshift client를 설치 합니다.  

> 참고 :
https://docs.redhat.com/ko/documentation/openshift_container_platform/4.6/html/installing_on_gcp/cli-installing-cli-on-macos_installing-gcp-customizations

<br/>

oc 명령어를 입력해 봅니다.  

```bash
root@edu2:~# oc
OpenShift Client

This client helps you develop, build, deploy, and run your applications on any
OpenShift or Kubernetes cluster. It also includes the administrative
commands for managing a cluster under the 'adm' subcommand.

To familiarize yourself with OpenShift, login to your cluster and try creating a sample application:

    oc login mycluster.mycompany.com
    oc new-project my-example
    oc new-app django-psql-example
    oc logs -f bc/django-psql-example

To see what has been created, run:

    oc status

and get a command shell inside one of the created containers with:

    oc rsh dc/postgresql

To see the list of available toolchains for building applications, run:

    oc new-app -L

Since OpenShift runs on top of Kubernetes, your favorite kubectl commands are also present in oc,
allowing you to quickly switch between development and debugging. You can also run kubectl directly
against any OpenShift cluster using the kubeconfig file created by 'oc login'.

For more on OpenShift, see the documentation at https://docs.openshift.com.

To see the full list of commands supported, run 'oc --help'.
```  

<br/>

접속 테스트를 합니다.  
아이디는 `namespace 이름 - admin` 으로 구성이 되고 namespace 생성시에 자동 생성이 됩니다.  


<br/>

`oc login <API SERVER:포트> -u <아이디> -p <패스워드> --insecure-skip-tls-verify`

<br/>

```bash
root@edu2:~# oc login https://api.211-34-231-81.nip.io:6443 -u edu1-admin -p New1234! --insecure-skip-tls-verify
Login successful.

You have one project on this server: "edu1"

Using project "edu1".
Welcome! See 'oc help' to get started.
```  

<br/>


## Git 설치

<br/>

Git이란 소스코드를 효과적으로 관리하기 위해 개발된 '분산형 버전 관리 시스템'입니다. ( 이전 에는 SVN 많이 사용 )  

가장 대중적인 SaaS 형태는 Microsoft에서 제공하는 GitHub 이고
Private 형태로는 Gitlab을 많이 사용 함.  

<br/>

참고 사이트 :  https://backlog.com/git-tutorial/kr/intro/intro1_1.html    

<br/>


본인의 PC에 git을 설치하고 버전을 확인한다.  

```bash
git --version
``` 

<img src="./assets/git_version.png" style="width: 60%; height: auto;"/>

<br/>


## Helm 설치.

<br/>


helm 3.x 이상 버전을 설치한다.

<br/>


```bash
curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3
```  

<br/>


```bash
chmod 700 get_helm.sh
```

```bash
./get_helm.sh
```  

<img src="./assets/helm_install.png" style="width: 80%; height: auto;"/>  

버전을 확인한다.

```bash
helm version
```

<img src="./assets/helm_version.png" style="width: 80%; height: auto;"/>  

helm repository 목록을 조회합니다. 처음 설치 했을때는 아무것도 없습니다.

```bash
helm repo list
```

<br/>

## GitHub 계정 생성

<br/>

https://github.com/ 접속하고 계정 생성  

<br/>

계정 생성 후에 Repository를  생성한다.

<br/>

아래와 같이 이름 입력를 하고 README file check 를 한다

<br/>

<img src="./assets/repository_create.png" style="width: 80%; height: auto;"/>  

default 브랜치를 main에서 master로 변경한다. ( 맨 하단 setting 클릭하여 설정)

<br/>

<img src="./assets/default_branch_modify.png" style="width: 60%; height: auto;"/>

<br/>

교육용 repository인 https://github.com/shclub/edu1 폴더의 파일을 복사하여 본인이 생성한 Repository에 신규 화일을 생성한다. 

<br/>

총 4개 화일을 만들고 내용을 복사한다.  ( 향후 Git 사용법 교육 후 Git Clone 사용 )

<img src="./assets/shclub_edu_file.png" style="width: 60%; height: auto;"/>

   - 샘플은 pyhon flask 로 구성

<br/><br/>

##  Docker Hub 계정 생성 

<br/>

https://hub.docker.com/ 접속하고 계정 생성  
- 향후 사내에서 개발시는 private docker registry Nexus 사용  

<br/>

### Docker 연동 테스트를 한다.

```bash
docker tag hello-world (본인id)/hello-world
docker push (본인id)/hello-world  
```

- 권한 에러 발생시 docker login 한다
```bash
docker login 
```

<img src="./assets/docker_denied.png" style="width: 60%; height: auto;"/>

정상적으로 로그인후 push를 한다.

```bash
docker push (본인id)/hello-world  
```     

<br/>

<img src="./assets/docker_push.png" style="width: 60%; height: auto;"/>

도커허브 본인 계정에서 도커 이미지 생성 확인  

<img src="./assets/docker_hub_world.png" style="width: 60%; height: auto;"/>


도커 이미지가 Private으로 되어 있으면 Public 으로 변경한다. 
- 개인 계정은 1개의 private 만 가능

setting 으로 이동하여 Make public 클릭후 repository 이름을 입력후 Make Public 클릭  

<img src="./assets/docker_hub_make_public.png" style="width: 60%; height: auto;"/>


<br/>


