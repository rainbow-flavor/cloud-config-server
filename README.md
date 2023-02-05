# cloud-config-server
RainbowFlavor 전반에서 사용되는 spring 의 properties 소스를 중앙 관리하기 위한 애플리케이션입니다.  
Spring Cloud Config Server 의존성이 사용되었으며, 이 서버의 설정파일을 사용하는 애플리케이션은 Spring Cloud Config Client 의존성을 사용합니다. 실질적인 *.properties 는 private repository 에서 관리되고 있습니다.  

## Deploy
Github Action 에서 Docker Image 로 빌드 완료되면 cloud config server 가 위치한 K8S cluster 로 Action 에서 접근합니다.  
K8S 에서 작성된 Deployment 에 따라 업데이트 된 이미지를 pull 받으며 기존에 있던 Pod 를 파괴하고 재생성합니다.  

## Monitoring
WhaTap 의 cloud monitoring 을 사용하여 Pod 의 상태와 Application 의 상태를 모니터링합니다.  

## Client List
[roxy-api-server](https://github.com/rainbow-flavor/roxy-api-server)  
[gorakulist](https://github.com/rainbow-flavor/GorakuList)  
[irostub-webhook](https://github.com/rainbow-flavor/irostub-webhook)  
