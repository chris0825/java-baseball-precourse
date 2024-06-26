# 미니과제1 - 숫자 야구 게임

## 목차
[1. 코드 소개](#코드-소개)<br>
[2. 숫자야구 룰](#숫자야구-룰)<br>
[3. 구현 기능](#구현-기능)<br>
[4. 코드 제한조건](#코드-제한조건)<br>

## 코드 소개
- 숫자 야구를 java코드로 구현한 것이다.

## 숫자야구 룰
1. 게임 시작시 프로그램은 각 자리가 서로 다른 3자리 수 하나를 정한다.
2. 플레이어는 게임이 시작되면 3자리의 수를 맞춘다.
3. 프로그램은 플레이어가 예측한 3자리의 수를 다음 상황에 따라 스트라이크와 볼, 낫싱을 출력한다.
    - 같은 자리, 같은 수: 스트라이크
    - 다른 자리, 같은 수: 볼
    - 프로그램 출력 예시
        - 낫싱 (= 0볼 0스트라이크)
        - {ball_N}볼 {strike_N}스트라이크
4. 플레이어가 3스트라이크 즉, 정답을 맞출 때 까지 2~3번의 과정이 반복된다.

## 구현 기능
- 게임 시작시 상대방(컴퓨터)이 난수를 생성한다.
    - 상대방(컴퓨터)은 게임이 시작되면 각 자릿수가 다른 임의의 3자리 수를 생성한다.
- 플레이어(사용자)로부터 수를 입력받는다.
    - 콘솔창에 "숫자를 입력해 주세요 : "라는 문장을 출력하여 플레이어(사용자)에게 숫자를 입력받는다.
- 플레이어(사용자)의 입력이 잘못된 경우 해당 프로그램은 IllegalArgumentException을 발생시키며 애플리케이션을 종료한다. 이때, 잘못된 플레이어(사용자)의 입력은 다음과 같다.
    - int 자료형이 아닌 경우
    - 3자리수가 아닌 경우(100미만 999초과)
    - 각 자리의 숫자가 서로 다르지 않은 경우
- 플레이어(사용자)가 입력한 수와 상대방(컴퓨터)가 지정한 수를 비교하여 볼, 스트라이크, 낫싱을 판정하여 판정 결과를 콘솔창에 출력한다.
    - 두 수가 일치하는 경우: 3스트라이크
    - 두 수가 다른 경우 다음 경우에 따라 출력값을 결정
        - 같은 숫자가 같은 자리에 있는 경우: 스트라이크
        - 같은 숫자가 다른 자리에 있는 경우: 볼
    - 모든 숫자가 일치하지 않는 경우 "낫싱"을 출력한다.
- 플레이어(사용자)가 정답을 맞춘 경우(3스트라이크) 게임을 종료하고 게임을 다시 시작할지 애플리케이션을 종료 시킬지 결정한다.

## 코드 제한조건
- JDK 17 버전에서 실행이 가능해야 함
- 프로그램 실행의 시작점은 Application의 main()
- 프로그램 종료 시 System.exit()를 호출해서는 안됨
- 자바 코드 컨벤션을 지켜야 함
- indent depth는 max 2
- 3항 연산자 사용 불가
- 함수는 오직 한 가지 일만 수행할 수 있다
- JUnit 5와 AssertJ를 이용하여 정리한 기능 목록이 정상적으로 작동되는지 테스트 코드로 확인