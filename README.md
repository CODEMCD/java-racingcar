# 우아한테크코스 프리코스

## 2주차 미션 - 자동차 경주 게임
- 최신 업데이트 날짜: 2019-04-02

## 기능 요구사항
- 주어진 횟수 동안 **n대의 자동차는 전진 또는 멈출 수 있다.**
- 각 자동차에 **이름을 부여** 할 수 있다. 전진하는 자동차를 출력할 때 자동차 이름을 같이 출력한다.
- 자동차 이름은 쉼표(,)를 기준으로 구분하며 **이름은 5자 이하만** 가능하다.
- 사용자는 **몇 번의 이동을 할 것인지를 입력** 할 수 있어야 한다.
- 전진하는 조건은 0에서 9 사이에서 random 값을 구한 후 **random 값이 4 이상일 경우 전진** 하고, **3 이하의 값이면 멈춘다.**
- 자동차 경주 게임을 완료한 후 **누가 우승했는지를 알려준다.** 우승자는 한 명 이상일 수 있다.

![RacingCarExample](https://user-images.githubusercontent.com/34755287/55400712-94fd0080-5589-11e9-850d-5bd2a01c1881.png)

## 프로그래밍 요구사항
- 자바 코드 컨벤션 지키기
- indent(인덱트, 들여쓰기) depth는 2까지만 허용한다.
  - while문 + if문은 depth 2이다.
- 함수(메서드)의 길이가 15라인을 넘지 않는다.
- else 예약어를 쓰지 않는다.(switch/case문 금지)
- 제공하는 Car 객체 활용하기

## 기능 구현 목록
#### 1. 클래스 만들기
- Main 클래스: 게임을 진행시키는 클래스
- Car 클래스: 자동차의 데이터 저장과 동작을 수행하는 클래스
- GameProcess 클래스: 게임에 필요한 기능을 수행하는 클래스
- Input 클래스: 사용자의 입력을 받는 클래스
- Output 클래스: 게임 진행에 필요한 화면을 출력하는 클래스

#### 2. Car 클래스 구현하기
- 멤버 변수
  - MIN_MOVE_NUMBER: 자동차가 이동할 수 있는 최소 숫자(4)
  - name: 자동차 이름
  - position: 현재 자동차 위치
- 멤버 함수
  - ```Car(String name)```: Car 인스턴스를 생성할 생성자
  - ```goStraight()```: 자동차가 앞으로 한 칸 전진한다.
  - ```getName()```: 현재 자동차의 이름를 반환한다.
  - ```getPosition()```: 현재 자동차의 위치를 반환한다.

#### 3. GameProcess 클래스 구현하기
- 멤버 변수
  - MAX_NUMBER_SIZE: 사용할 수 있는 숫자의 최대 크기(9) + 1
- 멤버 함수
  - ```makeRandomNumber()```: 0 ~ 9 사이의 랜덤 숫자를 만든다.
  - ```getMaxPosition()```: 자동차 목록 중 현재 위치가 가장 큰 값을 반환한다.
  - ```getNumberOfWinner()```: 우승자가 몇 명인지 반환한다.
  - ```tellWinner()```: 우승자가 누구인지 알려준다.

#### 4. Input 클래스 구현하기
- 멤버 함수
  - ```inputCarName()```: 자동차의 이름을 입력하고 입력 결과를 반환한다.
  - ```inputHowManyMove()```: 자동차가 몇 번 움직일지 입력하고 입력 결과를 반환한다.

#### 5. Output 클래스 구현하기
- 멤버 함수
  - ```outputMoveResult()```: 각 자동차가 움직인 결과를 출력한다.
  - ```outputWhoIsWinners()```: 게임 우승자를 출력한다.

#### 6. Main 클래스 구현하기
- 멤버 함수
  - ```main()```: 자동차 이름과 이동 횟수를 입력받고 자동차를 생성한다. 그리고 레이싱 시작과 종료 매서드를 호출한다.
  - ```startRacing()```: 레이싱을 시작하고 이동할 때마다 결과를 출력한다.
  - ```endGameAndOutputWinner()```: 레이싱이 종료되고 최종 우승이 누구인지 출력한다.

#### 7. 유저 입력 오류 예외 처리하기
- InputError 클래스 구현: 입력 오류를 처리하기 위한 클래스
- 자동차가 몇 번 움직이는지 입력에서 예외
  - 숫자가 아닌 경우: 다시 입력
- 자동차 이름 입력에서 예외
  - 글자 수가 5자를 초과한 경우: 다시 입력
  - 쉼표를 두 개 이상 사용한 경우: 다시 입력
  - 입력의 가장 앞 또는 뒤에 쉼표가 한 개있는 경우: 내부에서 쉼표를 지워준다.

#### 8. 리팩토링
- 자바 코드 컨벤션에 부합하는지 확인하기
- 프로그래밍 요구사항에 부합하는지 확인하기

#### 9. 주석 달기
