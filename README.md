# ⚾ 미션 - 숫자 야구 게임

> 우아한테크코스 프리코스 1주차 미션
>
> **제출자: 강현영**

<br>

## 🎯 구현할 기능 목록

1. `컴퓨터의 랜덤값 생성 기능`

   * 서로 다른 세 개의 숫자로 구성
     * 겹치는 숫자가 있는지 확인하는 기능
2. `유저의 입력값 판별 기능`

   * 세 개의 숫자를 알맞게 입력했을 경우
     * 유저의 입력값 리턴
   * 잘못된 입력값을 작성한 경우
     *  `alert`을 이용해 메시지를 보여주고, 재입력할 수 있게 한다.
3. `컴퓨터의 랜덤값과 유저의 입력값 비교 기능`
   * 값이 모두 같다면
     * 게임 재시작 기능으로 이동
   * 같은 수가 전혀 없으면 `낫싱`
   * 같은 수가 다른 자리에 있으면 `볼`
   * 같은 수가 같은 자리에 있으면 `스트라이크`
   * 스트라이크와 볼이 같이 있는 경우 `볼`을 먼저 쓰고, `스트라이크` 를 쓴다.
   * 같은 수가 다른 자리에 있으면 `볼`
4. `게임 재시작 기능`
   * 결과값으로 정답을 맞추었다는 문구 띄우기
   * 게임 재시작 버튼 제공
     * id가 `game-restart-button` 인 버튼을 클릭함으로써, 게임을 다시 시작할 수 있다.
       * 이벤트리스너를 달아서 컴퓨터의 랜덤값 새로 생성, 유저의 입력값과 문구 초기화

<br>

## 💻 프로그래밍 구현 과정

1. `컴퓨터의 랜덤값 생성 기능`

   > 세 자리 숫자 생성을 위해 arrayLength 변수에 3 할당
   >
   > `컴퓨터의 랜덤값`의 길이를 확인하기 위해 빈 Array 선언
   >
   > while문의 변수 i = 0;
   >
   > while문을 돌며 i가 arrayLength보다 작은 동안 Array에 랜덤 숫자 담기

   * 랜덤 숫자 1개 생성
     * Array에 담긴 숫자들과 중복 여부 확인
       * 없으면 Array에 push
       * 있으면 다시 랜덤 숫자 생성
   
2. `유저의 입력값 판별 기능`

   > `id`가 `submit`인 확인 버튼에 이벤트리스너를 달아서,
   >
   > 유저의 입력값을 받는 `getUserInputNumbers` 함수 실행.
   >
   > 유저의 입력값은 split()을 통해 Array의 형태로 받는다.
   >
   > 유저의 입력값 Array에 Set을 사용하여, 중복값을 제거한 길이를 비교한다.

   * `유저의 입력값 Array`의 길이가 3이고 `유저의 입력값 Array` 의 길이와  `Set(유저의 입력값 Array)`  의 길이가 같다면
     *  ~~`컴퓨터의 랜덤값과 유저의 입력값 비교 기능`으로 연결~~
     * 유저의 입력값 리턴(판별 기능만 하게 한다 - **한 가지 함수 한 가지 기능**)
   * 예외인 경우
     *  `alert`을 이용해 메시지를 보여주고, 재입력할 수 있게 한다.

3. `컴퓨터의 랜덤값과 유저의 입력값 비교 기능`

   > 스트라이크 개수를 담을 변수 `strikeNumbers`
   >
   > 볼 개수를 담을 변수 `ballNumbers`
   >
   > 유저의 입력값을 for문으로 하나씩 돌면서
   >
   > 컴퓨터의 랜덤값에 있고 위치도 같다면 `strikeNumbers`++
   >
   > 컴퓨터의 랜덤값에 있고 위치가 다르다면 `ballNumbers`++
   >
   > for문 종료 후

   * `ballNumbers`가 0이고 `strikeNumbers` 3이면

     * 게임 재시작 기능으로 이동

   * `ballNumbers`가 0이고 `strikeNumbers`가 0이면

     * `낫싱` 출력

   * `ballNumbers`가 0이 아니고 `strikeNumbers`가 0이면

     * `볼` 출력

   * `ballNumbers`가 0이고 `strikeNumbers`가 0이 아니면

     * `스트라이크` 출력

   * `ballNumbers`와 `strikeNumbers` 둘 다 0이 아니면

     * `볼` + `스트라이크` 출력

     