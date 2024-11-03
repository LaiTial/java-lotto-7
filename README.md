# 로또 발매기

## 소개

로또 발매기를 만든다

- 로또 구입 가격을 입력받아 당첨 번호와 비교, `당첨 내역`과 `수익률`을 구하는 문제.


## 기능 요구사항

간단한 로또 발매기를 구현한다.

- 숫자 범위는 `1`~`45`까지.
- 로또 발행 시 중복되지 않는 `6`개의 숫자를 뽑음.
- 당첨 번호 추첨 시 중복되지 않는 숫자 `6`개와 보너스 번호 `1`개를 뽑는다.

당첨은 1등부터 5등까지로, 당첨 기준과 금액은 아래와 같다.
- `1`등: `6`개 번호 일치 / `2,000,000,000원`
- `2`등: `5`개 번호 + 보너스 번호 일치 / `30,000,000원`
- `3`등: `5`개 번호 일치 / `1,500,000원`
- `4`등: `4`개 번호 일치 / `50,000원`
- `5`등: `3`개 번호 일치 / `5,000원`

로또 구입 금액을 입력하면 구입 금액에 해당하는 만큼 로또를 발행해야 한다.
- `1`장의 가격은 `1,000`원.
- 당첨 번호와 보너스 번호를 입력받는다.
- 구매한 로또 번호와 당첨 번호를 비교하여 `당첨 내역` 및 `수익률`을 출력하고 로또 게임을 종료.
- 사용자가 잘못된 값을 입력할 경우 `IllegalArgumentException` 발생, `"[ERROR]"`로 시작하는 에러 메시지를 출력 후 입력을 다시 받는다.
- `Exception`이 아닌 `IllegalArgumentException`, `IllegalStateException` 등과 같은 명확한 유형을 처리.

## 입출력 요구 사항

#### 입력

- 로또 구입 금액을 입력 받는다. (`1,000원` 단위로, 나누어 떨어지지 않을 시 예외 처리)
``` java
14000
```
- 당첨 번호(쉼표(`,`)를 기준으로)
``` java
1,2,3,4,5,6
```
- 보너스 번호
``` java
7
```

##### 출력

- 발행한 로또 수량 및 번호 (`오름차순`으로 정렬)
``` java
8개를 구매했습니다.
[8, 21, 23, 41, 42, 43] 
[3, 5, 11, 16, 32, 38] 
[7, 11, 16, 35, 36, 44] 
[1, 8, 11, 31, 41, 42] 
[13, 14, 16, 38, 42, 45] 
[7, 11, 30, 40, 42, 43] 
[2, 13, 22, 32, 38, 45] 
[1, 3, 5, 14, 22, 45]
```

- 당첨 내역을 출력
``` java
3개 일치 (5,000원) - 1개
4개 일치 (50,000원) - 0개
5개 일치 (1,500,000원) - 0개
5개 일치, 보너스 볼 일치 (30,000,000원) - 0개
6개 일치 (2,000,000,000원) - 0개
```

- 수익률 (소수점 둘째 자리에서 반올림)
``` java
총 수익률은 62.5%입니다.
```

- 예외 상황 시 에러 문구(단, 에러 문구는 `"[ERROR]"`로 시작)
``` java
[ERROR] 로또 번호는 1부터 45 사이의 숫자여야 합니다.
```

- 실행 결과 예시

``` java
구입금액을 입력해 주세요.
8000

8개를 구매했습니다.
[8, 21, 23, 41, 42, 43] 
[3, 5, 11, 16, 32, 38] 
[7, 11, 16, 35, 36, 44] 
[1, 8, 11, 31, 41, 42] 
[13, 14, 16, 38, 42, 45] 
[7, 11, 30, 40, 42, 43] 
[2, 13, 22, 32, 38, 45] 
[1, 3, 5, 14, 22, 45]

당첨 번호를 입력해 주세요.
1,2,3,4,5,6

보너스 번호를 입력해 주세요.
7

당첨 통계
---
3개 일치 (5,000원) - 1개
4개 일치 (50,000원) - 0개
5개 일치 (1,500,000원) - 0개
5개 일치, 보너스 볼 일치 (30,000,000원) - 0개
6개 일치 (2,000,000,000원) - 0개
총 수익률은 62.5%입니다.
```

## 기능 목록