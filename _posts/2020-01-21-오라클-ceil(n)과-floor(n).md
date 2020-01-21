**CEIL**(n)  함수는 **n 보다 같거나 가장 큰 정수**를 반환한다.

```sql
SELECT CEIL(11.321), CEIL(12.901), CEIL(21.001)
  FROM DUAL
```

위와 같은 쿼리는 각각 12, 13, 22 이 된다.

**FLOOR**(n) 함수는 CEIL 함수와는 반대로 **n 보다 작거나 가장 큰 정수**를 반환한다.

```sql
SELECT FLOOR(11.321), FLOOR(12.901), FLOOR(21.001)
  FROM DUAL
```

위 쿼리를 실행하면 각각 11, 12, 21 의 결과값을 받는다.

