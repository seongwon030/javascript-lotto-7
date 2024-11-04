# javascript-lotto-precourse

## 기능목록

### 1. 구입금액 입력 클래스

**PurchaseAmountGeneraor**

```
기능 : 구입금액 입력과 유효성 검사
```

1. 구입금액을 입력받는다.

```
구입금액을 입력해 주세요.
8000
```

2. 빈문자열인지 검사한다.
3. 정규식을 통해 숫자로만 이루어진지 검사한다.
4. 1000으로 나누어지는지 검사한다.
5. 에러 시 재입력한다.

### 2. 로또번호 생성 클래스

**LottoTicketGenerator**

```
구입금액만큼 로또를 생성
```

1. <code>PurchaseAmountGeneraor</code>에서 구입금액을 매개변수로 받는다.
2. <code>구입금액 / 1000</code>만큼의 로또를 생성하고 출력한다.

```
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

- <code>generateRandomNumbers</code> : 1에서 45사이의 중복되지 않는 6개의 숫자 배열을 생성
- <code>generateRandomNumbers()</code> : generateRandomNumbers 를 오름차순 정렬하여 반환하는 메서드

### 3. 로또번호 입력 클래스

**Lotto**

```
로또번호 입력과 유효성 검사
```

[6개의 로또번호 배열검사]

1. 당첨 번호를 입력받는다.

```
당첨 번호를 입력해 주세요.
1,2,3,4,5,6
```

2. 빈문자열인지 검사한다.
3. 로또번호가 6개인지 검사한다.
4. 로또번호 중복여부를 검사한다.
5. 에러 시 재입력한다.

[로또 번호 하나당 검사]

1. 빈문자열인지 검사한다.
2. 숫자로만 이루어진지 검사한다.
3. 1에서 45사이인지 검사한다.
4. 에러 시 재입력한다.

- <code>validateLottoLength</code> : 로또 번호가 6개인지 검사하는 메서드
- <code>validateDuplicatedNumber</code> : 로또 번호 중복여부를 검사하는 메서드

### 4. 보너스 번호 입력 클래스

**BonusNumber**

```
보너스 번호 입력과 유효성 검사
```

1. 보너스 번호를 입력받는다.

```
보너스 번호를 입력해 주세요.
7
```

2. 빈문자열인지 검사한다.
3. 숫자로만 이루어진지 검사한다.
4. 1에서 45사이인지 검사한다.
5. <code>당첨번호에 포함되지 않는지</code>검사한다.

- <code>validateBonusInWinningNumber</code> : 당첨번호와 보너스 번호의 중복여부를 검사하는 메서드

### 5. 당첨 결과 출력 클래스

**LottoResults**

```
당첨 내역과 수익률을 출력
```

1. 당첨 내역을 관리할 딕셔너리를 생성한다.
2. 수익률 계산에 필요한 딕셔너리를 추가 생성한다.
3. 3개 일치 ~ 6개 일치 시 당첨내역 딕셔너리의 key에 해당하는 value에 1씩 더한다.
4. 당첨 내역에 해당하는 <code>key - value</code>값을 출력한다.

```
당첨 통계
---
3개 일치 (5,000원) - 1개
4개 일치 (50,000원) - 0개
5개 일치 (1,500,000원) - 0개
5개 일치, 보너스 볼 일치 (30,000,000원) - 0개
6개 일치 (2,000,000,000원) - 0개
```

5. 수익률 딕셔너리로 각 당첨금x당첨횟수의 총합을 구입금액으로 나눈 수익률을 출력한다.

```
총 수익률은 62.5%입니다.
```
