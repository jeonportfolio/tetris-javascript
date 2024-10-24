# 자바스크립트로 테트리스 게임 만들기 <br/>

☞ HTML, CSS, Java Script 사용 <br/>

## 테이블 생성 <br/>

☞ for문을 활용하여 테이블 생성하기 (12X22)설정 <br/>
☞ 가로는 x축과 y축을 이용하여 좌표 표시  -> 각각의 테이블의 고유 번호를 부여함 <br/>
☞ NOW_BLOCK -> shape = 현재의 형태 current_blocks = 현재의 위치 <br/>
☞ x,y값을 받아 ID값을 정하고 기존 space 흰색 바탕에서 하늘색 바탕으로 변경 <br/>
☞ 첫번째 시작 테이블의 위치를 중앙으로 위치 (position) <br/>

## 테이블 방향별 정리<br/>

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


## 현재의 블록 상태 <br/>

☞ nowBlock -> 객체 형태 -> displayBlock을 통해 추출 (각블록의 배열에 따라서 제어)<br/>
☞ split 형태로 x와 y좌표를 구함 <br/>
☞ newBlock 함수를 사용하여 블록을 Random하게 추출 (Math.random과 Math.floor 함수 사용) -> 난수 값을 정수로 추출하고 min이상의 범위 <br/>
☞ 최솟값은 0 최대값은5로 5가지의 모양에 맞추어 설정 <br/>


## 랜덤 블록

☞ math.random 함수를 사용해서 숫자를 랜덤하게 가지고옴 

## 방향키 이벤트  <br/>

☞ Jquery의 마우스 이벤트 사용 e의 인수값을 받아 판단한다. <br/>
☞ moveBlock에서 gubun인자로 각 키의 움직임을 구분한다. <br/>
☞ 현재의 좌표를 알아서 x와 y축의 속성값을 변동하여 (숫자로 변환) 기존의 것을 투명색 새로반영된 값을 현재의 블록으로 만드는 형식 <br/>


## 블록 막기 & 블록 회전 <br/>

☞ html 개체가 없을 경우 is_stop으로 제어 사각틀에서 나가지 않도록 함<br/>
☞ 위 블록의 형태와 같이 2차 3차원까지 표현함  <br/>
☞ BLOCK_POSITION_SHAPE -> 동일한 도형이 각각의 각도에서의 변화<br/>
☞ up키를 누르면 변경이됨 (current_standard로 현재의 위치 유지) (블록변화 제어) <br/>
☞ 바꾸기전의 블록 배경색 흰색 바꾼 블록들은 하늘색으로 <br/>
☞ 사각형 모양은 바꿔도 모양바뀜이 없기 때문에 제외<br/>


## 1초마다 블록 내려오기  <br/>

☞ setInterval을 사용해서 1초 단위로 movedown함수를 이용해서 아래로 이동<br/>
☞ 새로운 블록도 계속적으로 내려옴 newBlock실행<br/>
☞ 다른 블록과의 구분 DOWN, RIGHT, LEFT에 모두 적용 block형태로 되어 있거나 isExistNowBlock을 활용<br/>


