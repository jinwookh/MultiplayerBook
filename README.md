Multiplayer Book
================


Xcode에서 실행
------------
이미 리포지토리에 Xcode 환경 설정 파일이 있다.   
설정이 잘 되는지 확인한다.   

## 1. Xcode를 실행
`MultiplayerBook/chapter\ 6/RoboCatAction`로 프로젝트를 만든 후 Xcode를 실행한다.

## 2. scheme을 확인
빌드한 후 scheme을 확인한다.
RoboCatActionServer, RoboCatActionClient 두 개의 scheme이 있어야 한다.

## 3. commandline argument 확인
client를 구동할 때는 commandline argument가 2개 필요하다. (서버주소, 이름)
```
ex) 
localhost:8080 jinwookh
```

서버를 구동할 때는 commandline argument가 1개 필요하다. (포트번호)
```
ex)
45000
```
