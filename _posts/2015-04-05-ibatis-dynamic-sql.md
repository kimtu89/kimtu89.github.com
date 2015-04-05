---
layout: post
title: (기술) iBatis 동적 SQL
---

 여러 업무를 하면서 isEqual이나 isEmpty등의 옵션을 통해서 쿼리문에 변화를 줄 수 있다는 것을 알게 되었고 이것이 iBatis에서 지원하는 요소들이란 것을 알게되어 정리해보려고 합니다.
 
 ---
 
<strong>단일 조건적인 요소</strong>
: 프로퍼티의 상태를 체크합니다.

속성
 - prepend – 앞에 추가적으로 붙는 부분("AND", "OR", "," 등)
 - property – 비교할 프로퍼티
 
요소들
 - isPropertyAvailable: 프로퍼티가 유효하다면 내부 쿼리문을 포함
 - isNotPropertyAvailable: 프로퍼티가 유효하지 않다면 내부 쿼리문을 포함
 - isNull: 프로퍼티가 null이라면 내부 쿼리문을 포함
 - isNotNull: 프로퍼티가 null이 아니라면 내부 쿼리문을 포함
 - isEmpty: 프로퍼티가 null이거나 empty(String의 경우 "" 등)라면 내부 쿼리문을 포함
 - isNotEmpty: 프로퍼티가 null이 아니고 empty가 아니라면 내부 쿼리문을 포함

 ---

<strong>바이너리 조건적인 요소</strong>
: 프로퍼티 값을 특정 값과 비교하거나 다른 프로퍼티와 비교합니다.

속성
 - prepend: 앞에 추가적으로 붙는 부분("AND", "OR", "," 등)
 - property: 비교할 프로퍼티
 - compareProperty: 비교될 다른 프로퍼티
 - compareValue: 비교될 특정 값
※ compareProperty와 compareValue 둘 중 하나 사용

요소들
 - isEqual: 프로퍼티 값이 다른 프로퍼티 값이나 특정 값과 같다면 내부 쿼리문을 포함
 - isNotEqual: 프로퍼티 값이 다른 프로퍼티 값이나 특정 값과 같지 않다면 내부 쿼리문을 포함
 - isGreaterThen: 프로퍼티 값이 다른 프로퍼티 값이나 특정 값 보다 크다면 내부 쿼리문을 포함
 - isGreaterEqual: 프로퍼티 값이 다른 프로퍼티 값이나 특정 값과 같거나 크다면 내부 쿼리문을 포함
 - isLessThen: 프로퍼티 값이 다른 프로퍼티 값이나 특정 값 보다 작다면 내부 쿼리문을 포함
 - isLessEqual: 프로퍼티 값이 다른 프로퍼티 값이나 특정 값과 같거나 작다면 내부 쿼리문을 포함
 
 ---

 그동안 각각의 경우에 대한 쿼리문을 일일히 작성해왔었는데 이런 요소들이 있다는 것을 알게되어 좀 더 효율적인 개발을 할 수 있게 된 것 같습니다.
 
 또한 이번 기회에 정리하게 되면서 iBatis 메뉴얼을 직접 읽어 보면서 더 많은 기능들도 알게 되어 메뉴얼의 중요성을 깨닫게 되었습니다.
