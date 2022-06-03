# Kubernetes를

<img width="984" alt="image" src="https://user-images.githubusercontent.com/15190903/171772520-ce3c67fe-bc58-44f8-89fa-ddf31b119e90.png">

- 쿠버네티스를 배포하면 클러스터가 생성됨.
- 생성된 클러스터는 노드들의 집합. 
- 노드들은 크게 두 가지 유형으로 나눠지는데, 각각이 컨트롤 플레인과 데이터 플레으로 나뉨.
- 컨트롤 플레인(Control Plane)은 워커 노드와 클러스터 내 파드를 관리 및 제어
- 데이터 플레인(Data Plane)은 워커 노드들로 구성되어 있으며 컨테이너화된 애플리케이션의 구성 요소인 파드를 호스트함.


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
