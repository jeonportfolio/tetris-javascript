# 자바스크립트로 테트리스 게임 만들기 

- HTML, CSS, Java Script 사용

## 테이블 생성

- for문을 활용하여 테이블 생성하기 (12X22)설정
- 가로는 x축과 y축을 이용하여 좌표 표시  -> 각각의 테이블의 고유 번호를 부여함
- NOW_BLOCK -> shape = 현재의 형태 current_blocks = 현재의 위치
- x,y값을 받아 ID값을 정하고 기존 space 흰색 바탕에서 하늘색 바탕으로 변경
- 첫번째 시작 테이블의 위치를 중앙으로 위치 (position)

## 테이블 방향별 정리

-       □□□□   :  "0:0", "1:0", "2:0", "3:0"        "0:0", "0:1", "0:2", "0:3"

-       □        
        □□     :  "0:0", "1:0", "-1:0"          "0:1", "0:0", "1:0"          "0:0", "1:0", "1:1"          "0:1", "1:1", "1:0"

-        □        "0:1", "1:1", "1:0"           "0:0", "0:1", "1:1"          "0:1", "0:0", "1:0"          "0:0", "1:0", "1:1"
        □□     :  

 -      □         
        □□□    :   "0:1", "1:1", "2:1", "0:0"            "0:2", "0:1", "0:0", "1:0"            "0:0", "1:0", "2:0", "2:1"            "0:2", "1:2", "1:1", "1:0"

-         □        
        □□□    :   "0:1", "1:1", "2:1", "2:0"            "1:-1", "1:0", "1:1", "2:1"            "-1:1", "-1:0", "0:0", "1:0"            "0:-1", "1:-1", "1:0", "1:1"

-       □□         
        □□     :   "0:1", "1:1", "0:0", "1:0"


## 현재의 블록 상태

- newBlock 함수를 사용하여 블록을 Random하게 추출 (Math.random과 Math.floor 함수 사용) -> 난수 값을 정수로 추출하고 min이상의 범위
- 최솟값은 0 최대값은5로 5가지의 모양에 맞추어 설정


## 방향키 이벤트 

- Jquery의 마우스 이벤트 사용 e의 인수값을 받아 판단한다.
- moveBlock에서 gubun인자로 각 키의 움직임을 구분한다.
- 현재의 좌표를 알아서 x와 y축의 속성값을 변동하여 (숫자로 변환) 기존의 것을 투명색 새로반영된 값을 현재의 블록으로 만드는 형식
