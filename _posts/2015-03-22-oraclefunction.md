---
layout: post
title: (기술) 오라클 내장함수
---

간단한 업무를 몇 개 맡게 되면서 여러 쿼리문도 접하게 되었습니다.
그러면서 nvl, decode 등의 함수들을 처음으로 접하게 되어 이 오라클 내장함수들을 정리해 보려고 합니다.

 ---

오라클 내장함수 사용위치
---

 - SELECT 절
 - WHERE 절
 - START WITH 절
 - HAVING 절
 - INSERT 문의 INTO 절
 - UPDATE 문의 SET 절

오라클 내장함수 종류
---

숫자형 함수

 - ABS(n): n의 절대값을 반환합니다. ( ABS(-10) = 10 )
 - CEIL(n): n과 같거나 큰 자연수 중 가장 작은 수를 반환합니다. ( CEIL(2.1) = 3 )
 - FLOOR(n): n과 같거나 작은 자연수 중 가장 큰 수를 반환합니다. ( FLOOR(2.9) = 2 )
 - MOD(n, m): n을 m으로 나눈 나머지 값을 반환합니다. ( MOD(8,3) = 2 )
 - POWER(n, m): n의 m제곱 값을 반환합니다. ( POWER(3,2) = 9 )
 - ROUND(n, i): n을 소수점 이하 i번째 자리까지 반올림하여 반환합니다. ( ROUND(3.16,1) = 3.2 )
 - SQRT(n): n의 제곱근 값을 반환합니다. ( SQRT(4) = 2 )

문자형 함수

 - CONCAT(char1, char2): char1 문자열 뒤에 char2 문자열을 이어붙여 반환합니다. ( CONCAT('abc','def') = 'abcdef' )
 - LENGTH(char): 문자열의 길이를 반환합니다. ( LENGTH('abc') = 3 )
 - LOWER(char): 문자열을 모두 소문자로 변환하여 반환합니다. ( LOWER('ABC') = 'abc' )
 - REPLACE(char, search_string, replace_string): char 문자열 안의 search_string을 replace_string으로 변환합니다. ( REPLACE('a-b','-','_') = 'a_b' )
 - SUBSTR(char, position, length): char 문자열의 position 위치부터 length 개수 만큼의 문자열을 반환합니다. ( SUBSTR('abcd',2,2) = 'bc' )
 - UPPER(char): 문자열을 모두 대문자로 변환하여 반환합니다. ( UPPER('abc') = 'ABC' )
 
조건 함수

 - DECODE(exp,case1,then1,case2,then2,…,default): exp와 맞는 case가 있으면 해당하는 then을 반환, 그외의 경우 default를 반환합니다. ( DECODE('y','y','Y','n') = 'Y' )
 - NULLIF(exp1,exp2): exp1과 exp2이 같으면 null을 반환, 같지 않으면 exp1을 반환합니다. ( NULLIF(1,1) = null )
 - NVL(exp1,exp2): exp1가 null이 아니라면 exp1를 반환하고 null이라면 exp2을 반환합니다. ( NVL(null,2) = 2 )
 - NVL2(exp1,exp2,exp3): exp1가 null이 아니라면 exp2를 반환하고 null이라면 exp3을 반환합니다. ( NVL(null,1,2) = 2 )
 
변환 함수

 - TO_CHAR(number, format) or TO_CHAR(datetime, format): 날짜형 데이터나 숫자형 데이터를 format에 맞춰 문자열로 변환합니다.
 - TO_DATE(char, format): char 문자열을 format에 맞춰 날짜형 데이터로 변환합니다.
