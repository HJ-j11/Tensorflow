# Tensorflow

Getting Started
환경 설정
- Github에서 docker toolbox 다운로드 받아 사용.
- Windows 10 64-bit 

$ docker-machine ls 
가상 머신 목록을 볼 수 있음.

$ docker-machine create vdocker -d virtualbox로 이름이 vdocker인 새로운 가상머신 생성
마지막 문장에서 docker is up and running!이라는 표시가 나온다면 설치 성공한 것.

cmd prompt 창에 들어가 다음과 같이 입력하고

FOR /f "tokens=*" %i IN ('docker-machine env --shell cmd vdocker') DO %i

docker run -it tensorflow/tensorflow:latest-devel을 사용하여 container 실행.
( b.gcr.io가 앞에 붙으면 실행이 되질 않음. -> 이유 모름^^;) 




---- 
혹은 docker toolbox에서 
$ docker pull tensorflow/tensorflow를 통해 image pull 한 후,

$ docker run -it -p xxxx:xxxx --name xxx tensorflow/tensorflow를 하여 container 실행하기

$ docker exec -it xxx(name) bash를 통해 tensorflow 창에 진입하였다면 성공!



이후 jupyter notebook에 실행하고 싶어 tensorflow 화면에 진입하여 #표시가 나왔을 때 다음과 같이 입력해주었다.

#pip install jupyter notebook

설치하는 마지막 과정에서 upgrade를 하라고 함.

upgrade 후 jupyter notebook --ip= xxx.xxx.xx.xx --allow-root 를 덧붙여 실행이 되도록 함.

※ docker inspect (container name) | grep IPAddress 
확인하여 ip 주소 기억하기



