FORMAT: 1A
HOST: http://jenkins.golfzoncounty.com/

# **Jenkins CI/CD**
>   - Version 2.436

Jenkins를 통한 CI/CD 구축한 과정을 정리 공유 해보고자 합니다.
우선 이번 프로젝트에서 구축하려는 CI/CD 구조는 다음과 같습니다.

1. Git Lab 배포 브런치에 Push/Merge
2. Jenkins(docker container)에서 빌드 및 배포
    + git checkout
    + 프로젝트 빌드
    + war, jar 파일 이미지 빌드
    + ssh을 통한 도커 이미지 파일 전송
    + 배포 서버에서 도커 컨테이너 생성 및 실행
    + 젠킨스 리소스 정리

Jenkins의 환경 설정부터 시작하여 CI/CD 구축 과정을 살펴보겠습니다.
1
