### 집합연산자 - 합집합

집합연산자란 오라클에서 특정 결과값들의 합집합을 출력하고자 할때 사용되는 연산자이다. UNION 과 UNION ALL 두 가지가 사용되는데, UNION은 중복을 제거하고 정렬이 되어 결과가 나오는 반면, UNION ALL은 그대로 출력한다. 따라서 UNION의 연산결과가 더 느리다. UNION에서 중복을 제거할때는 하나의 행의 값이 완전히 일치할때에만 중복으로 인지하고 제거한다.

UNION이나 UNION ALL을 사용하기 위해서는 합집합을 구하기 위한 결과값들이 아래와 같이 동일한 컬럼(컬럼 타입, 순서, 개수가 모두 동일)을 가져야 한다. 조회된 값의 컬럼 명은 첫번째 결과값에 명시되어 있는 컬럼명을 따라간다.

```sql
   SELECT USER_KEY, NAME, AGE FROM EX_USER_TBL
    UNION
   SELECT MEMBER_KEY, MEMBER_NAME, AGE FROM EX_MEMBER_TBL
 ORDER BY NAME
```

집합연산자를 사용하면서 명시적 정렬이 필요한 경우, 마지막에 첫번째 결과값의 컬럼명으로 명시해주면 된다. 