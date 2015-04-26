---
layout: post
title: (기술) struts interseptor
---

jsp에서 java로 데이터를 전송하면서 자동으로 매핑하도록 하는 방법을 알게 되어 정리합니다.

 ---

원하는 동작
---

form에서 input name을 object.attribute1, object.attribute2, object.attribute3 등으로 전송하면 java에서 액션을 처리하면서 해당 파라미터들을 object 객체 변수 하나로 받게 하려고 했습니다.

해결방법
---

액션에서는 해당 변수에 대한 세터를 만들고 액션을 설정하는 파일에서 "params" interceptor를 거치도록 설정하였습니다.

종류
---

그리고 이러한 인터셉터들을 struts interceptor로 찾아보니 여러가지 인터셉터가 존재하는 것을 알게 되었습니다.

- alias: 요청 사이에 서로 다른 이름을 가진 비슷한 파라미터들을 컨버팅한다.
- chain: 이전 액션의 프로퍼티를 사용할 수 있게 한다.
- checkbox: 체크되지 않은 체크박스 감지 코드를 추가하고 디폴트 값을 설정한다.
- cookie: 액션에 설정가능한 '이름/값'을 가지는 쿠키를 삽입한다.
- debugging: 디버깅 화면을 제공한다.
- fileUpload: 파일업로드를 지원한다.
- logger: 액션의 이름을 출력한다.
- params: 요청 파라미터들을 액션에 저장한다.
- prepare: 액션이 preparable 인터페이스 구현 시 prepare() 메소드를 호출한다.
- scope: 액션 상태 값을 세션 등에 저장한다.
- timer: 액션의 작업 처리 시간을 출력한다.
- token: 액션 내에 유효한 토큰이 존재하는지 검사하고 폼을 이중으로 서브밋하는 것을 방지한다.
