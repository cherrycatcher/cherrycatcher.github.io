### 집합연산자 - 교집합

오라클에서 결과값들에 대한 교집합을 구하고자 할때 INTERSECT를 사용한다. INTERSECT는 여러 행 중에서 공통된 값을 출력해준다. 명시된 컬럼값의 값이 모두 같을때 교집합으로 인식한다. 컬럼값은 컬럼의  타입, 순서, 개수가 모두 동일해야 같은 것으로 본다.

```sql
   SELECT USER_KEY, NAME, AGE FROM EX_USER_TBL
    INTERSECT
   SELECT MEMBER_KEY, MEMBER_NAME, AGE FROM EX_MEMBER_TBL
 ORDER BY NAME
```

