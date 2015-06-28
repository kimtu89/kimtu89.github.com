---
layout: post
title: (기술) HTML 삽입 함수
---

HTML text를 제어할 수 있는 html(), val(), text() 함수와 삽입 함수인 prepend(), append(), before(), after() 등의 함수들의 사용 차이에 대해서 정리해두려고 합니다.

 ---

html, text, val의 차이
---

- html(): 요소의 내용을 HTML의 내용으로 가져온다.
- html(value): 요소에 value로 html 내용을 입력한다.
- text(): 요소의 내용을 텍스트 문자열로 가져온다.
- text(value): 요소에 내용을 지정한 텍스트 문자열로 입력한다.
- val(): Form Element의 value를 가져온다. (input, textarea)
- val(value): Form Element의 value를 입력한다.

삽입 함수
---

- A.prepend(B): A요소의 시작 부분에 B내용을 삽입
- A.prependTo(B): B요소의 시작 부분에 A요소를 삽입
- A.append(B): A 요소의 마지막 부분에 B내용을 삽입
- A.appendTo(B): B요소의 마지막 부분에 A요소를 삽입
- A.before(B): A요소의 앞에 B를 삽입
- A.insertBefore(B) – B의 앞에 A를 삽입
- A.after(B): A요소의 뒤에 B를 삽입
- A.insertAfter(B): B의 뒤에 A를 삽입

prepend, append와 before, after의 큰 차이점은 해당 요소의 내부에 삽입이 되는지 외부에 삽입이 되는지의 차이라고 할 수 있습니다.
