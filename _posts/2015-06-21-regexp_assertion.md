---
layout: post
title: (기술) 정규표현식 Assertion
---

정규표현식을 사용하면서 가장 유용하게 사용하는 assertion에 대해서 정리해보려고 합니다.

 ---

assertion이라는 것은 실제로 다른 문자열을 매칭시키지 않으면서 그 자리에서 앞이나 뒤에 해당하는 패턴이 존재하는 지만 확인하는 것입니다. 
앞에 해당하는 패턴이 존재하는 지 확인하는 것을 look-behind assertion, 반대는 look-ahead assertion이라고 합니다. 
전자는 (?<=...)과 (?<!...)를 사용하고, 후자는 (?=...)과 (?!...)을 사용합니다. 
(=가 들어 가면 그 패턴에 맞을 때를 의미하고, !가 들어 가면 그 패턴에 안 맞을 때를 의미합니다.)

- regex1(?=(regex2)) : regex1 다음 regex2의 정규표현식이 일치할 경우 반환
- regex1(?!(regex2)) : regex1 다음 regex2의 정규표현식이 일치하지 않을 경우 반환
- (?<=(regex2))regex1 : regex2의 정규표현식이 일치하고 regex1가 나올 경우 반환
- (?<!(regex2))regex1 : regex2의 정규표현식이 일치하지 않고 regex1가 나올 경우 반환
- (?(condition)yes-regexp) : 조건이 참이면 yes-regexp를 매치함, 조건이 거짓이면 이 식을 무시하고 다음 정규식으로 진행
- (?(condition)yes-regexp|no-regexp) : 조건이 참이면 yes-regexp를, 거짓이면 no-regexp를 매치함

 ---

정규표현식 테스트 사이트 : http://regexr.com/
