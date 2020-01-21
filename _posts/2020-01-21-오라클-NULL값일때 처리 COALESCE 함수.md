```mysql
COALESCE(case1, case2, case3, ... , caseN)
```

조건(컬럼)을 순차적으로 진행하면서 NULL이 아닌 값을 리턴한다.  모든 값이 NULL 일때에만 NULL 을 반환한다. caseN에 널일 경우에 대한 기본값을 입력해두면 널에 대한 연산을 처리할 수 있다. 

```mysql
SELECT USER_NAME, AGE, COALESCE(SALARY*0.1, -1) 
  FROM EX_USER_TBL 
```

SALARY 값이 널일때 -1 를 리턴한다. 

COALESCE 함수에 나열되는 조건(컬럼) 은 리턴되는 데이터 유형이 비슷해야 한다. 예를들어 위 쿼리에서 -1이 아닌 'N' 과 같은 문자형을 사영한다면  ORA-00932:inconsistent datatypes  유형 오류가 나게 된다.

