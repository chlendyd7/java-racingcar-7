# java-racingcar-precourse

### 초간단 자동차 경주 게임

- 입력받은 자동차 이름으로 우승 자동차 이름을 출력하는 게임

### 기능 요구사항

- 경주할 자동차 이름을 , 로 구분한다
- 시도할 횟수가 input으로 들어온다
- 시도할 횟수를 0 ~ 9 사이 무작위 값을 구한 후 4 이상 일 시 전진한다
- 자동차 경주 게임을 완료 후 우승자를 출력
- 우승자가 여러 명 일 경우 ,를 이용해 구분
- 사용자가 잘못된 값을 입력할 경우 IllegalArgumentException 을 발생시킨 후 애플리케이션은 종료되어야 한다.


### 프로그래밍 요구 사항
- indent(인덴트, 들여쓰기) depth를 3이 넘지 않도록 구현한다. 2까지만 허용한다.
  - 예를 들어 while문 안에 if문이 있으면 들여쓰기는 2이다.
  - 힌트: indent(인덴트, 들여쓰기) depth를 줄이는 좋은 방법은 함수(또는 메서드)를 분리하면 된다.
- 3항 연산자를 쓰지 않는다.
- 함수(또는 메서드)가 한 가지 일만 하도록 최대한 작게 만들어라. 
- JUnit 5와 AssertJ를 이용하여 정리한 기능 목록이 정상적으로 작동하는지 테스트 코드로 확인한다.


### 구현할 기능 목록

**사용자 입력**

사용자가 입력하는 값은 camp.nextstep.edu.missionutils.Console의 readLine()을 활용한다.

- 경주할 자동차 이름을 입력하세요.
  - 여러개의 이름이 들어 올 수 있다
  - 이름은 쉼표(,) 기준으로 구분
  - 리스트로 자동차 이름을 관리한다
- 시도할 횟수를 받는다
  - 시도한 횟수만큼 기능을 구현해 수행한다

**기능 분류**
- 차수 별 실행 기능
  - 해당 차수에 입력 받는 자동차 이름 갯수 만큼 for문을 루프한다
    - random 기능을 통해 해당 자동차가 전진 할 수 있는지 확인한다
      - 0~9까지의 random 값을 구함
        - Random 값 추출은 camp.nextstep.edu.missionutils.Randoms의 pickNumberInRange()를 활용한다.
      - 4 이상 일 시 해당 자동차는 해당 차수에 전진
- 출력:
  - 차수 별 실행이 모두 완료 된 후 우승자를 출력한다
  - 가장 전진을 많이 한 자동차가 우승차량이다
  - 우승자가 여러 명일 경우 쉼표(,)를 이용해 구분한다

**에러 케이스**
- 사용자가 잘못된 값을 입력할 경우 IllegalArgumentException을 발생시킨 후 애플리케이션은 종료되어야 한다.
