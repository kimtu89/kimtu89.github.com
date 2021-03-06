---
layout: post
title: (기술) List 인터페이스의 remove() 메소드 사용하기
---

티라미슈노트 서비스를 개발하면서 List 자료구조를 많이 사용하였는데 remove() 메소드를 사용하면서 발생했던 문제에 대해 정리해 보려고 합니다

두 가지 형태의 파라미터
---

<strong>remove(int index)</strong>

 - index 파라미터 위치에 존재하는 객체를 제거합니다.

<strong>remove(Object o)</strong>

 - 파라미터로 들어온 객체와 일치하는 객체 중 첫번째 객체를 제거합니다.

발생했던 문제점과 해결과정
---

제가 사용하려고 했던 remove 메소드는 remove(Object o) 형태의 메소드였는데 지우고 싶은 객체와 같은 값을 갖는 객체를 생성하여 파라미터로 넘겨주어도 해당 객체가 제거되지 않는 문제가 발생하였습니다.

remove(Object o) 형태의 메소드의 동작 과정에서 파라미터로 넘겨지는 Object에 구현된 equals 메소드를 활용하기 때문이었습니다. 

List에 존재하는 객체와 파라미터로 넘겨진 객체를 equals 메소드를 통해서 첫 번째로 일치하는 것을 찾아서 제거하도록 구현 되어있었습니다.

그렇기에 제가 활용하려고 했던 객체 클래스 내부에 equals 메소드를 구현하여 문제를 해결하였습니다.
