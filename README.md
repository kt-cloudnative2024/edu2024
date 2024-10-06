# Cloud Native 역량 강화 교육


<br/>

본 교육 과정은 Cloud Native Evangelist 양성 과정으로 기본 개념과 실습 그리고 OJT 진행을 하며 직접 설치부터 설정 및 활용까지 수행한다.     

문의 :  이석환 ( seokhwan.lee@kt.com / shclub@gmail.com )

<br/>

0. Chapter 0 : 프로그램 설치  ( [가이드 문서보기](./install.md) )  

     - Docker / Docker Compose 설치
     - Openshift Console 설치 ( kubectl 같이 설치 됨 )
     - Git 설치
     - Helm 설치
     - Github 계정 생성
     - Docker Hub 계정 생성 

    <br/>

1. Chapter 1 : Docker  ( [가이드 문서보기](./chapter1.md) )  

     - Docker 소개
     - Docker 실습 ( Dockerfile 구성 및 빌드 , Tag , Push/Pull )
     - Github Action , workflow 사용 ( GoodBye Jenkins ) 
     - Docker Compose 설명 및 설치 , 활용 ( DB 연동 )    

     <br/>

2. Chapter 2 : kubernetes   ( [가이드 문서보기](./chapter2.md) )  

     - kubernetes 설치 (k3s) 및 설정 , k8s 이해 및 활용
     - kubernetes IDE 인 Lens 설치 및 사용법 실습   
     - Helm 설치 및 helm으로 prometheus 설치 활용
     - k8s hands-on Basic [ Hands-On 문서보기 ](./k8s_basic_hands_on.md)  

          - 실습 전체 개요
          - kubeconfig 설정 : kubectl 설치
          - kubectl 활용
          - kubernetes 리소스 ( Pod , Service , Deployment 생성 및 삭제)
          - 배포 ( Rolling Update / Rollback )
          - Serivce Expose ( Ingress )  
     
     <br/>

     - k8s hands-on Middle [ Hands-On 문서보기 ](./k8s_middle_hands_on_2023.md)  
          - Docker Hub Rate Limit
          - Helm
          - Kubernetes의 Node Scheduling
          - Storage Volume ( PV/PVC , DB 설치 + NFS )
          - MariaDB NFS 에 설치 ( /w Helm Chart )
          - Service - Headless, Endpoint, ExternalName
          - Daemonset , Job , CronJob
          - configMap , Secret
          - NFS 라이브러리 설치 ( Native Kubernetes ) 

     <br/>


3. Chapter 3 : k8s 보안   ( [가이드 문서보기](./k8s_security.md) ) 

    - 보안 component
    - K8S Security Overview  
    - Network Policy  
    - Route 에 SSL 인증서 설정     
    - User Account vs Service Account  
    - Krew 설명 및 설치  
    - Kubernetes 보안 Components  
    - Security Context
    - Pod Security Policy ( PSP )  
    
<br/>



