---
layout: post
title: (기술) json, map 변환
---

json 데이터를 입력받아 map객체에 옮기거나 map객체를 json 형식으로 보여주는 방법을 정리해 놓으려고 합니다.

JSONObject -> Map
---

ObjectMapper class의 readValue 메소드를 이용합니다.

```JAVA
Map<String, Object> map = new ObjectMapper().readValue(jsonData, HashMap.class);
```

 ---
 
Map -> JSONObject
---

ObjectMapper class의 writeValueAsString 메소드를 이용합니다.

```JAVA
String jsonData = new ObjectMapper().writeValueAsString(map);
```
