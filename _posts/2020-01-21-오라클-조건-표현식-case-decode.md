### 조건 표현식

오라클에서 조건문을 지정하는 방법은 크게 CASE 와 DECODE 문이 있다. 

#### CASE 문

```sql
CASE '컬럼 혹은 표현식' WHEN '비교값1' THEN '리턴값1'
(WHEN '비교값2' THEN '리턴값2'
 WHEN '비교값 n' THEN '리턴값n'
 ELSE '기본값')
  END ('별명')
```

컬럼 혹은 표현식과 WHEN 절의 비교값이 일치하면 리턴값을 반환한다. WHEN 절에 같은 값이 없으면 기본값을 반환한다. 만약 ELSE 값으로 기본값을 지정하지 않을 경우 NULL 값을 반환한다.

컬럼 혹은 표현식을 WHEN 구문에 넣어 표현할 수 도 있으나, 동일한 값을 반복하게 되어 쿼리가 길어지므로 CASE 문 뒤에 사용하는 것이 편하다.

```sql
SELECT CASE USER_CODE WHEN 'MA' THEN 1
                      WHEN 'CA' THEN 2
                      WHEN 'XX' THEN 3
                      ELSE 0 END AS CODE 
 FROM EX_USER_TBL
```



#### DECODE 함수

```sql
DECODE ('컬럼 혹은 표현식', '찾을값1', '결과1' [,'찾을값', '결과2', …][, '기본값']) ['별명']
```

DECODE 함수는 기준이 되는 컬럼 혹은 표현식의 값이 찾을 값1과 일치할 경우 결과1을 리턴하고, 매치하지 않을 경우 그 뒤 구문을 실행해 준다. CASE 문과 같은 기능을 사용하며, 동일하게 어떤 조건과도 일치하지 않을 경우 NULL 값을 리턴한다.

```sql
SELECT DECODE(USER_CODE, 'MA', 1, 'CA', 2, 'XX', 3, 0) AS CODE
  FROM EX_USER_TBL
```

CASE 문의 경우 크기 비교 구문 등 다양한 표현식을 이용할 수 있어 DECODE문 보다 편하고 가독성이 좋다.