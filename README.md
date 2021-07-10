# CURLING 3D

#### 팀원 : 서영재, 서원진 (콘텐츠IT 전공)

---------------------------
## 프로젝트 주제

### ● 게임 설명
실제 컬링을 모티브하여 Stone ,Broom 사용하여 네 개의 동심원으로 분할된 목표 지점에 위치시키는 스포츠입니다.

본 게임은 컬링과 다른 점수계산 방법을 사용합니다.

4번의 엔드가 끝나면 동심원 위에 있는 자신의 팀 STONE의 점수를 계산합니다. 

각 동심원마다 점수가 다릅니다.  [아래 사진 참고] 

<img src = https://user-images.githubusercontent.com/52689953/123447735-264a6880-d615-11eb-9174-44fc39f09c03.png width=300 height=300>

 
  


### ● 게임 조작 방법
<img src = https://user-images.githubusercontent.com/52689953/123449582-c8b71b80-d616-11eb-9ecd-35d5360154b4.png width=800 height=500>



*********
## 프로젝트 내용

### 구현 설명
- 시작화면에서 버튼 클릭 – HOW : 게임 목적과 방법 설명  START : main Scene으로 이동

<img src = https://user-images.githubusercontent.com/52689953/123449603-ce146600-d616-11eb-8810-a7e20bb117f1.png width=800 height=500>
[사진. 시작화면]

![image](https://user-images.githubusercontent.com/52689953/123449872-0a47c680-d617-11eb-92ae-0e76601590dc.png)
![image](https://user-images.githubusercontent.com/52689953/123449916-1469c500-d617-11eb-8ed4-29d7117c5574.png)

[사진. 버튼설정 및 구현코드]

- STONE_MOVE 구현
<img src = https://user-images.githubusercontent.com/52689953/123450114-52ff7f80-d617-11eb-99a0-a8fbbf3c67d8.png width=800 height=300>
<img src = https://user-images.githubusercontent.com/52689953/124733591-4cde9c80-df4f-11eb-9efa-8b1fc5acd93a.png width=800 height=300>
<img src = https://user-images.githubusercontent.com/52689953/124733682-641d8a00-df4f-11eb-8311-9cd53d32a6ae.png width=800 height=300>


- POWER SIDER
<img src = https://user-images.githubusercontent.com/52689953/123450770-06687400-d618-11eb-8367-10d77a373be7.png width=600 height=300>
<img src = https://user-images.githubusercontent.com/52689953/123450555-d3be7b80-d617-11eb-9c8a-1eaf83d06715.png width=400 height=300> 


- BOXCHECK
<img src = https://user-images.githubusercontent.com/52689953/124733775-7ac3e100-df4f-11eb-9c58-b3634d679f2d.png width=600 height=300>

> 아래와 같이 BoxCollider 설정
<img src = https://user-images.githubusercontent.com/52689953/124733818-86170c80-df4f-11eb-8917-c8ce7916bb9b.png width=800 height=300>

> Red 차례일 경우 : red차례 UI 활성화
> Yellow 차례일 경우 : yellow 차례 UI 활성화
![image](https://user-images.githubusercontent.com/52689953/124916357-8b4a8900-e02d-11eb-8aa7-f3fde972f67e.png)


- SCORE_CAL
![image](https://user-images.githubusercontent.com/52689953/124916432-a2897680-e02d-11eb-85f3-1c0a6e53bd44.png)

![image](https://user-images.githubusercontent.com/52689953/124916485-b3d28300-e02d-11eb-8761-145fdbd5bd65.png)




- IMAGE_CUT
![image](https://user-images.githubusercontent.com/52689953/124916567-c6e55300-e02d-11eb-9996-3c9ff989e413.png)





- CAMERA_MOVE
![image](https://user-images.githubusercontent.com/52689953/124916621-d369ab80-e02d-11eb-8ae1-45882f747461.png)


- BROOM_MOVE
![image](https://user-images.githubusercontent.com/52689953/124916664-e11f3100-e02d-11eb-9d49-9675f2dd205f.png)


- BROOM_GENERATE
![image](https://user-images.githubusercontent.com/52689953/124916706-ebd9c600-e02d-11eb-9575-48edfbc0ecda.png)


### 구현 영상
## 프로젝트 일지
- 역할분담
![image](https://user-images.githubusercontent.com/52689953/124916736-f5632e00-e02d-11eb-977e-9f62f8c3d035.png)

- 텀 프로젝트 구현시 어려웠던 점
1. 싱글톤 : 유니티로 게임을 개발하다 보니여러 게임 오브젝트가 접근해야 하는 스크립트가 있을 수 있습니다.그래서 싱글 턴을 사용하면 정말 좋다 생각했습니다.Google에 싱글 톤을 만드는 방법을 검색해봤지만코드가 전반적으로 어렵게 느껴져서 시도하지 못했습니다.

2. 점수계산 : 처음에 각 동심원 오브젝트에 Collider를 추가하고 isTrigger 모드로 통과도 되고 충돌도 감지하게 했습니다.
OnTriggerStay를 사용하여 stone이 각 동심원에 충돌이 유지될 때 점수를 합하는 식으로 알고리즘을 작성했습니다.
하지만 문제점은 각 stone의 broom이 상속되어 있어 충돌 체크가 잘 안 맞았습니다.

3. 게임 매니저, 코루틴 사용 : 카메라의 player를 바꿔주기 위해 지정한 상황이 끝날 때까지 기다리는 코루틴 WaitUntil을 사용했을 때 yield 문에 오류가 자꾸 떠서 시도하지 못했습니다.
코루틴에 대해 더 공부해야겠습니다.

4. 효과음 : Stone과 Stone이 부딪혔을 때 리얼함을 주고 싶어서 무료 타격음을
다운해서 적용하였는데 소리가 잘 들리지않았습니다.











