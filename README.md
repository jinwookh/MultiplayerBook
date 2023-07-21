Multiplayer Book
================


Xcode에서 실행
-------------
이미 리포지토리에 Xcode 환경 설정 파일이 있다.   
설정이 잘 되는지 확인한다.   

### 1. Xcode를 실행
`MultiplayerBook/chapter\ 6/RoboCatAction`로 프로젝트를 만든 후 Xcode를 실행한다.

### 2. scheme을 확인
빌드한 후 scheme을 확인한다.
RoboCatActionServer, RoboCatActionClient 두 개의 scheme이 있어야 한다.

### 3. commandline argument 확인
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

linux 계열에서 실행 (MAC cmd)
------------
- 헤더 파일이 있는 디렉토리를 추가해주는 설정이 필요하다. (-l 설정)
- dynamic library가 있는 디렉토리가 추가해야 한다. (-L 설정)
- dynamic library를 하나씩 일일히 추가해야 한다. (-l 설정)
- 실행과 관련있는 모든 cpp 파일을 추가해야 한다. ( ex: MultiplayerBook/chapter\ 6/RoboCatAction/RoboCatServer/**/*.cpp)
- gcc에 c++ 11버전을 사용한다고 알려주어야 한다. (-std=c++11 -stdlib=libc++) 안 그러면 emplace_back 함수를 gcc가 인지하지 못한다.

1. 다음 명령어를 실행한다.
```
g++ -std=c++11 -stdlib=libc++ -w -v -o robocatserver -I/MultiplayerBook/chapter\ 6/RoboCatAction/RoboCat/Inc -I/MultiplayerBook/chapter\ 6/RoboCatAction/RoboCatServer/Inc -I/MultiplayerBook/chapter\ 6/RoboCatAction/SDL/include /MultiplayerBook/chapter\ 6/RoboCatAction/RoboCat/**/*.cpp /MultiplayerBook/chapter\ 6/RoboCatAction/RoboCatServer/**/*.cpp -L/MultiplayerBook/chapter\ 6/RoboCatAction/SDL/lib/mac -lSDL2-2.0.0 -lSDL2_image-2.0.0 -lSDL2_mixer-2.0.0 -lSDL2_ttf-2.0.0 -lfreetype.6 -lpng16.16
```
2. dynamic library 경로를 DYLD_LIBRARY_PATH에 추가한다.
```
export DYLD_LIBRARY_PATH=/MultiplayerBook/chapter\ 6/RoboCatAction/SDL/lib/mac
```
3. 실행 인자를 넣어서 실행한다.
```
./robocatserver 45000
```
경로는 개인 환경마다 다를 수 있다.
