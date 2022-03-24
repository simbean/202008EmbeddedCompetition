# 1. Overview
![overview](https://user-images.githubusercontent.com/71861842/146942448-3a64f5d5-5a2b-4339-b524-a9864cfcf98f.gif)<br>
4차 산업혁명을 맞이하여 급박하게 변하고 있는 분야는 바로 자동차이다. 세계보건기구(WHO)의 발표에 따르면 전 세계에서 매일 수백만 명이 교통사고로 다치고 3500명 이상이 사망한다. 미래의 자동차에는 정교하고 검증받은 자율주행 기술이 필수적인 요소가 될 것이다.  
Python과 OpenCV을 사용하여 차선을 검출해내고 동시에 신호등의 상황을 인지하여 자율적으로 주행 의사결정을 하는 라즈베리파이 기반 자율주행 RC카를 제작했다. 또한 간단한 조작 UI를 제공하는 웹페이지를 통해 수동 제어가 가능하도록 구현하였고 라이다센서와 조도센서를 통한 거리조절 및 전조등 점등을 구현했다.

# 2. Structure
## 2.1. 프로그램 순서도
![자율주행차흐름도](https://user-images.githubusercontent.com/52540882/116738808-e2c8e900-aa2d-11eb-9172-7974a5c039d8.PNG)

# 3. Language/Tools
## 3.1. Language
* Python
* Html, Css, Javascript
## 3.2. Tools
* PC - PythonCharm IDE
* Raspberry Pi - Python IDLE
* OpenCV library
****

# 4. Result
## 4.1 차선검출을 통한 방향 제어

![차선검출](https://user-images.githubusercontent.com/71861842/146945182-a69b86f0-900a-4a1e-a393-04705fdce50d.gif)
* 차선검출/소실점 추출            

## 4.2 신호등 색 검출을 통한 주행/정지
![신호등검출](https://user-images.githubusercontent.com/71861842/146945135-392dfe56-d2cc-433c-bcf0-418e77e7c175.png)

* 파란불 신호를 인식하여 box표시
 
## 4.3 직관적인 UI를 사용한 수동조작
![조작 UI](https://user-images.githubusercontent.com/71861842/146945327-d7da3907-29b2-45f3-9fa1-05dc7f0caf2c.jpg)

* Python Bottle Framework를 통한 수동 조작 UI 웹페이지 배포

# 5. Problem/Improve
### 라즈베리파이의 연산량 한계 초과 이슈
* 한정된 자원을 가지고 있는 라즈베리파이를 사용하다보니, 해상도가 높은 고성능의 웹캠에서 입력되는 input image를 처리하는 시간이 오래걸리는 부분을 해소하고자, 차선검출 로직의 main loop문에서 걸리는 부하를 해결하기위해 딜레이 함수를 통해 초당 처리 횟수를 줄였고 어느정도 움직임을 개선할 수 있었다.
**GPU가 탑제된 영상처리 특화 MPU를 사용했다면 더욱 자연스러운 주행이 가능했을 것으로 예상된다.

### 자동차 스티어링의 부재
* 방향 전환을 함에 있어서 스티어링이 없었기에 모든 바퀴의 회전각을 통해 방향을 전환할 수 밖에 없었다.
* 스티어링이 구현된 자동차였다면 훨씬 간결한 코드로와 더욱 깔끔한 움직임이 가능할 것으로 예상된다.

