---
layout: post
title: (기술) static 함수
---

지난번 json 데이터와 Map 변환 방법을 정리한 후 해당 함수들이 왜 static이 아닌가에 대해서 생각해보게 되었습니다.

그러다보니 제가 아직까지 static 함수가 무엇인지에 대해서 정확히 알고있지 못했던 것 같아 정리해보고 해답을 찾아보려고 합니다.

기본적으로 스태틱 자체에 대한 개념은 스태틱 변수를 통해서 어느정도 인지하고 있기 때문에 스태틱 함수에 대해서 모르고 있었던 내용만을 정리해보겠습니다.

Static Method
---

스태틱 메소드는 클래스 메소드라고도 부르며 Static 키워드를 함수 앞에 붙여서 선언합니다.

일반 메소드와의 차이
---

<strong>사용의 차이</strong>

일반 메소드는 클래스의 인스턴스를 선언하여 함수를 호출합니다. 
```JAVA
new ObjectMapper().readValue(jsonData, HashMap.class);
```
스태틱메소드는 클래스 이름만으로 직접 호출할 수 있습니다.
```JAVA
PropertyUtils.describe(object);
```

<strong>구현의 차이</strong>

스태틱 메소드는 일반 인스턴스 변수를 사용할 수 없습니다. 

즉, 어떤 메소드를 스태틱 메소드로 구현하기 위해서는 해당 메소드에서 사용하는 메소드 외부 변수가 스태틱 변수로 선언 되어야 합니다.

 ---
 
ObjectMapper 클래스의 readValue 함수와 writeValueAsString 함수의 경우 

ObjectMapper 클래스 내의 _jsonFactory라는 인스턴스 변수를 사용하고 있었기 때문에 static 함수로 선언될 수 없었습니다.
