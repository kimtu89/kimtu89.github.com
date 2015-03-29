---
layout: post
title: (기술) 오라클 rownum 사용 팁
---

rownum이란?
---

오라클에서 지원하는 가상컬럼으로 쿼리의 결과에 1부터 하나씩 증가하여 붙는 컬럼입니다.

사용 용도
---

주로 여러개의 결과를 출력하는 쿼리문을 실행 후 결과의 개수를 제한하여 가져오는데 쓰입니다.

ex) SELECT * FROM student WHERE grade=3 AND rownum<=10

단, rownum이 결과에서 1부터 순서대로 증가하여 붙기 때문에 rownum=2 나 rownum>1과 같은 방식으로는 원하는 결과를 얻을 수 없습니다.

유의점
---

문제는 order by와 함께 사용될 경우 발생합니다.

order by 절의 실행 순서가 where 절의 실행 후이기 때문에 order by와는 관계없이 rownum에 맞는 결과를 출력한 뒤 order by 절을 수행합니다.

따라서 순서를 바꾸기 위해 order by 절을 내부쿼리에서 실행하도록 합니다.

예를 들어 3학년 고득점자 10명을 뽑는 쿼리문을 원한다면 

SELECT * FROM student WHERE grade=3 AND rownum<=10 ORDER BY score DESC 의 경우에는 원하는 결과를 얻을 수 없고

SELECT * FROM (SELECT * FROM student WHERE grade=3 ORDER BY score DESC) WHERE rownum<=10 의 쿼리를 실행해야 합니다.
