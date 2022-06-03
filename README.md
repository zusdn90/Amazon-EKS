# Kubernetes

<img width="984" alt="image" src="https://user-images.githubusercontent.com/15190903/171772520-ce3c67fe-bc58-44f8-89fa-ddf31b119e90.png">

- 쿠버네티스를 배포하면 클러스터가 생성됨.
- 생성된 클러스터는 노드들의 집합. 
- 노드들은 크게 두 가지 유형으로 나눠지는데, 각각이 컨트롤 플레인과 데이터 플레으로 나뉨.
- 컨트롤 플레인(Control Plane)은 워커 노드와 클러스터 내 파드를 관리 및 제어
- 데이터 플레인(Data Plane)은 워커 노드들로 구성되어 있으며 컨테이너화된 애플리케이션의 구성 요소인 파드를 호스트함.

[인그레스(Ingress)]
- 주로 클러스터 외부에서 쿠버네티스 내부로 접근할 때, 요청들을 어떻게 처리할지 정의해놓은 규칙이자 리소스 오브젝트.
- 한마디로 외부의 요청이 내부로 접근하기 위한 관문 역할.
- 외부 요청에 대한 로드 밸런싱, TLS/SSL 인증서 처리, HTTP 경로에 대한 라우팅 등을 설정할 수 있다. 
- 인그레스는 L7 영역의 요청을 처리합니다.
- 인그레스는 외부 요청 처리에 대한 규칙들을 설정해놓은 것을 의미하며, 이런 설정이 동작하기 위해서 필요한 것이 인그레스 컨트롤러라고 한다. 
- kube-controller-manager의 일부로 실행되는 다른 컨트롤러와 달리 인그레스 컨트롤러는 클러스터와 함께 생성되진 않아서 직접 구현해야 한다.

<img width="331" alt="image" src="https://user-images.githubusercontent.com/15190903/171775325-397e4eba-c0e4-4d50-9412-5bf4ab73877c.png">



# Amazon-EKS
- Kubernetes를 쉽게 실행할 수 있는 관리형 서비스.
- Amazon EKS를 사용하시면 AWS 환경에서 Kubernetes 컨트롤 플레인 또는 노드를 직접 설치, 운영 및 유지할 필요가 없다.

<img width="504" alt="image" src="https://user-images.githubusercontent.com/15190903/171772464-13f26752-0846-4ab6-a509-72e76f963497.png">


# 작업순서
1. AWS Cloud9을 통한 실습 환경 구축
2. 도커를 이용하여 컨테이너 이미지 생성
3. 컨테이너 이미지를 ECR에 업로드
4. Amazon EKS 클러스터 구축 및 서비스 배포
5. Container Insights 사용해보기
6. 파드 및 클러스터 오토 스케일링
7. AWS Fargate로 서비스 올리기
8. CI/CD 파이프라인 구축

# 아키텍처
<img width="978" alt="image" src="https://user-images.githubusercontent.com/15190903/171774434-f79fc71c-d193-4389-ad59-8ea8b3a58b37.png">


# 배포 프로세스
<img width="785" alt="image" src="https://user-images.githubusercontent.com/15190903/171777815-ca5c2852-f3c4-4d5b-a4e2-c1c4f2c271d1.png">

1. 소스 코드 다운로드
2. Amazon ECR에 각 서비스에 대한 리포지토리 생성
3. Dockerfile을 포함한 소스 코드 위치에서 컨테이너 이미지 빌드 후, 리포지토리에 푸시
4. 각 서비스에 대한 Deployment, Service, Ingress 매니페스트 파일 생성 및 배포
5. 사용자가 실제 서비스에 접근하는 순서
<img width="596" alt="image" src="https://user-images.githubusercontent.com/15190903/171777891-e0499c5c-91cb-40a4-8ea7-7427d810526f.png">



[출처]
- https://catalog.us-east-1.prod.workshops.aws/workshops/9c0aa9ab-90a9-44a6-abe1-8dff360ae428/ko-KR
