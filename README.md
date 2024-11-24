# kotlin-lotto
## 문자열 덧셈 계산기

### 기능 요구사항
- 쉼표(,) 또는 콜론(:)을 구분자로 가지는 문자열을 전달하는 경우 구분자를 기준으로 분리한 각 숫자의 합을 반환 (예: “” => 0, "1,2" => 3, "1,2,3" => 6, “1,2:3” => 6)
- 앞의 기본 구분자(쉼표, 콜론) 외에 커스텀 구분자를 지정할 수 있다. 커스텀 구분자는 문자열 앞부분의 “//”와 “\n” 사이에 위치하는 문자를 커스텀 구분자로 사용한다. 예를 들어 “//;\n1;2;3”과 같이 값을 입력할 경우 커스텀 구분자는 세미콜론(;)이며, 결과 값은 6이 반환되어야 한다.
- 문자열 계산기에 숫자 이외의 값 또는 음수를 전달하는 경우 RuntimeException 예외를 throw 한다.

### 구현할 기능 정의
#### 기본 기능
- [x] 빈 문자열을 입력할 경우 0을 반환한다.
- [x] 쉼표(,) 또는 콜론(:)을 기준으로 문자열을 분리한다.
- [x] 분리된 문자열을 숫자로 변환한다.
- [x] 변환된 숫자 리스트를 더해서 합계를 반환한다.

#### 커스텀 구분자 지원
- [x] 문자열의 앞부분에서 "//"와 "\n" 사이에 커스텀 구분자가 있는지 확인한다.
- [x] 커스텀 구분자가 존재할 경우 해당 구분자를 기준으로 문자열을 분리한다.

#### 예외 처리
- [x] 숫자 이외의 값이 포함된 경우 `RuntimeException`을 throw 한다.
- [x] 음수가 포함된 경우 `RuntimeException`을 throw 한다.
- [x] 공백이 포함된 경우 이를 무시하거나 올바르게 처리한다.

## 로또(자동)
### 기능 요구사항
- 로또 구입 금액을 입력하면 구입 금액에 해당하는 로또를 발급해야 한다.
- 로또 1장의 가격은 1000원이다.

### 구현할 기능 정의
- [x] 구입 금액을 입력받는다.
- [x] 입력받은 금액에 해당하는 로또를 발급한다.
- [x] 로또 한 장에 포함될 6개의 숫자를 무작위로 생성
- [x] 생성된 번호는 정렬된 상태로 저장한다.
- [x] 발급된 로또를 출력한다.
- [x] 지난 주 당첨 번호를 입력받는다.
  - [x] 입력은 쉼표(,)로 구분된 숫자로 받는다.
    - [x] 입력된 번호의 유효성을 검증한다.
      - [x] 1~45 범위 내의 숫자여야 한다.
      - [x] 중복된 숫자가 없어야 한다.
      - [x] 정확히 6개의 숫자가 입력되어야 한다.
- 구매한 로또 번호들과 지난 주 당첨 번호를 비교하여 일치하는 숫자의 개수를 계산한다.
    - [x] 일치 개수에 따라 등수와 상금을 결정한다.
      3개 일치: 5000원
      4개 일치: 50000원
      5개 일치: 1500000원
      6개 일치: 2000000000원
- [x] 당첨 통계를 출력한다.
- [x] 수익률을 계산한다.
- [x] 당첨 번호와 로또 번호를 비교하여 당첨 통계를 계산한다.

## 🚀 3단계 - 로또(2등)
### 기능 요구사항
- 2등을 위해 추가 번호를 하나 더 추첨한다.
- 당첨 통계에 2등도 추가해야 한다.

### 구현할 기능 정의
- [x] 2등을 위해 추가 번호(보너스)를 하나 더 입력받는다.
- [x] 당첨 통계에 2등도 추가한다.
- [x] 당첨 번호와 보너스 번호를 비교하여 당첨 통계를 계산한다.
- [x] 수익률을 계산에 보너스도 추가한다.
