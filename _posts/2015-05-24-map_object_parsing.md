---
layout: post
title: (기술) Object, map 변환
---

Map과 객체간의 변환 방법을 정리해 놓으려고 합니다.

 ---

Object -> Map
---

PropertyUtils class의 describe 메소드를 이용합니다.

```JAVA
map = PropertyUtils.describe(object);
```

 ---
 
Map -> Object
---

BeanUtils class의 populate 메소드를 이용합니다.

```JAVA
BeanUtils.populate(object, map);
```

<strong>※사용 중 이슈</strong>

변환할 Object 내에 Date, Timestamp, BigDecimal등의 변수 데이터가 있는 경우 No value specified for "Timestamp"와 같은 에러 메시지를 출력하면서 변환에 실패합니다.

이 경우 다음과 같이 컨버터를 등록하여 해결하였습니다.

```JAVA
beanUtilsBean.getConvertUtils().register(new SqlTimestampConverter(null), java.sql.Timestamp.class);
beanUtilsBean.getConvertUtils().register(new BigDecimalConverter(null), java.math.BigDecimal.class);
```
