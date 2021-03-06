---
layout: post
title: (기술) Hibernate
---

Hibernate에 대해서 정리해보겠습니다.

ORM
---

Hibernate가 대표적인 ORM이라고 들었기 때문에 ORM에 대한 개념정리부터 하겠습니다. 

ORM(Object-relational mapping: 객체 관계 매핑)은 데이터베이스와 객체 지향 프로그래밍 언어 간의 호환되지 않는 데이터를 변환하는 프로그래밍 기법입니다.

개체 관계 매핑 라고도 부르며 객체 지향 언어에서 사용할 수 있는 "가상" 객체 데이터베이스를 구축하는 방법입니다. 

<strong>ORM 도구들의 장점</strong>

- 단순히 SQL을 자동 생성하는 것보다 더 많은 일을 한다.
- 전체 애플리케이션의 개발 생산성을 향상시키는 완전한 퍼시스턴스 계층 아키텍처를 제공해준다.
- ORM들은 모두 트랜잭션 관리 기능을 제공한다.
- 로컬과 분산 트랜잭션 모두를 제어하는 간단한 API를 포함하고 있다.
- 불요한 데이터베이스 접근을 피할 수 있도록 여러 종류의 데이터를 다루는 다양한 캐시 전략을 제공한다.
- 데이터베이스 접근을 줄이는 다른 방법으로 데이터의 적재지연 기법이 있다. 적재 지연은 데이터 사용이 꼭 필요한 바로 그 순간까지 데이터 가져오기를 미룬다.

Hibernate
---

Hibernate는 대표적인 ORM으로 VO클래스들을 통해서 select, insert, update, delete등의 쿼리문을 자동생성해서 사용할 수 있도록 제공해주는 프레임워크라고 합니다.

기존에 제가 주로 사용하던 iBatis와 비교해본다면 쿼리문을 직접 작성하지 않기 때문에 맵퍼로 활용하는 xml의 문제점이 제거 되는 장점이 있지만, 복잡한 쿼리문을 활용하고자 할 때에는 코드상의 로직을 이용하여 데이터베이스 IO가 증가할 수 있는 단점도 있습니다.
