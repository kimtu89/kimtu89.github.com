---
layout: post
title: (기술) Flex 에러 코드
---

flex 개발을 하면서 나타나는 에러코드가 어떤 의미를 갖는지에 대해서 정리해보려고 합니다.

 ---

<strong>1008 : Variable xxx에 형식 선언이 없습니다.</strong>

* 에러 레벨: Warning
* 발생 원인: xxx에 데이터 타입을 지정하지 않았을 경우 발생
* 해결 방법: xxx에 데이터 타입을 지정하여 해결
ex) private var xxx; -> private var xxx: String;

<strong>typeError : Error #1009 : null 객체 참조의 속성이나 메소드에 액세스 할 수 없습니다.</strong>

* 에러 레벨: Error (Runtime Exception)
* 발생 원인: 실행중에 참조하려는 객체 속성이나 메소드가 존재하지 않는 경우 발생
* 해결 방법: 참조하려는 객체의 정확한 속성명이나 메소드명으로 작성

<strong>1061 : 정의되지 않은 메소드 입니다.</strong>

* 에러 레벨: Error
* 발생 원인: 에러 라인의 객체에서 정의되어있지 않은 메소드를 호출하려는 경우 발생 
* 해결 방법: 참조하려는 객체의 정확한 속성명이나 메소드명으로 작성

<strong>ReferenceError : Error #1069 : String 에서 속성을 찾을 수 없습니다. 기본값이 없습니다.</strong>

* 에러 레벨: Error
* 발생 원인: 데이터 바인딩을 위해 데이터를 참조하려고 하는데 그 속성명이 없거나, 데이터 바인딩이 되지 않았을 때
* 코드 예시: \<mx:LineChart dataProvider = "myAC } " 또는 showDataTips = true"\> 혹은 데이터 정의가 \<apple\> 100 \</apple\> 식으로 되어 있을때

<strong>1071 : 속성 뒤에 주석 사용이 가능한 지시문이 있어야 합니다.</strong>

* 에러 레벨: Error
* 발생 원인: 에러라인의 변수 선언이 제대로 되지 않았을 때
* 코드 예시: private; private var myVar : String;
* 해결 방법: 해당라인 근처의 변수 선언을 정확히 해준다.

<strong>1084 : var 'xxx' 메소드에 namespace 속성이 없습니다. 이 속성은 'Package - private' namespace 의 기본값을 구성합니다.</strong>

* 에러 레벨: Warning
* 발생 원인: 변수나 메소드명에 접근제어자를 지정하지 않았을 때 발생
* 해결 방법: 접근제어자를 지정
ex) var xxx: String; -> private var xxx: String;

<strong>1084 : identifier 가 xxx 앞에 있어야 합니다.</strong>

* 에러 레벨: Error
* 발생 원인: xxx 근처에 변수 선언이 잘못되어있거나 예약어로 변수명을 선언했을 경우
* 코드 예시: var 1 myVar : string;
* 해결 방법: 변수명이 제한자 + var + 변수명의 식으로 정확히 선언되었는지, 변수명이 영문자나 $ 혹은 _ 로 시작하는지 확인

<strong>1084 : Rightbrace 가 end of program 앞에 있어야 한다.</strong>

* 에러 레벨: Error
* 발생 원인: 코드 블록 {와} 표시가 제대로 열고 닫히지 않았을때
* 해결 방법: 모든 괄호가 짝지어 있는지 확인한다.

<strong>1084 : rightparen 이 콜론 " : " 앞에 있어야 합니다.</strong>

* 에러 레벨: Error
* 발생 원인: " : " 근처에서 객체 관련 코드가 잘못 되었을 때 / var, function 등의 키워드를 설정하지 않았을 떄
* 코드 예시: \<mx : Button label = "확인 " click = "showMenu(event:Event) " /\>
* 해결 방법: 클래스 타입 선언을 제거한다.

<strong>1087 : 프로그램 종료 이후에 문자가 추가로 발견 되었습니다.</strong>

* 에러 레벨: Error
* 발생 원인: 함수 선언 다음에 { 표시가 없을때
* 해결 방법: 모든 괄호가 짝지어 있는지 확인한다.

<strong>1120 : Access of undefined property myButton</strong>

* 에러 레벨: Error
* 발생 원인: 정의되지 않은 속성, 변수명이나 id 값을 참조하려고 할 때
* 코드 예시: \<mx : Button id = "myButn" label = "확인"\>\<mx : Label text = "{myButton.label}"/\>

<strong>1120 : Access of undefined property "클래스명"</strong>

* 에러 레벨: Error
* 발생 원인: 에러메시지에 나오는 클래스명을 import 하지 않았을 떄
* 코드 예시: ArrayUtil.toArray (myXML.result)
* 해결 방법: import mx.utils.ArrayUtil ; //문장을 스크립트 블록에 써줌

<strong>1180 : Call to a possibly undefined method check.</strong>

* 에러 레벨: Error
* 발생 원인: 정의되지 않은 메소드를 호출하려고 할 떄
* 해결 방법: 해당 함수를 호출하는 라인으로 가서 정확한 메소드명으로 고쳐준다.

<strong>The end - tag for element type "mx:Mode *" must end with a '\>' delimiter</strong>

* 에러 레벨: Error
* 발생 원인: 태그가 정확히 열고 닫히지 않았을때
* 해결 방법: 태그가 제대로 열고 닫혔는지 확인한다.

<strong>Encountered "\<mx:Model\>" at line 41, column5. Was expecting one of : /Model....</strong>

* 에러 레벨: Error
* 발생 원인: 태그가 정확히 열고 닫히지 않았을때
* 해결 방법: 태그가 제대로 열고 닫혔는지 확인한다 ( 특히 종료 태그를 빼먹지는 않았는지 확인)

<strong>The element type "mx:Model: must ne terminated by the matching end-tag "\</mx:Model\>"</strong>

* 에러 레벨: Error
* 발생 원인: 태그가 정확히 열고 닫히지 않았을때
* 해결 방법: 태그가 동일한 이름으로 열고 닫혔는지 확인한다.

<strong>invalid character or markup for found in script block. Try surrounding your code with a CDATA block.</strong>

* 에러 레벨: Error
* 발생 원인: 태그기호 " \< " 가 하나 더 있을떄
* 코드 예시: \<mx:Model\> .... \<\</mx:model\>
* 해결 방법: 추가된 " \< " 를 찾아서 제거 한다.

<strong>Encounterd " \> ＼n " at line41, column16.</strong>

* 에러 레벨: Error
* 발생 원인: xorm rlgh " \> " 가 하나 더 있을 때
* 코드 예시: \<mx:Model\> .... \</mx:model\>\>
* 해결 방법: 추가된 " \> "를 찾아서 제거 한다.

<strong>Cannot resolve attribute 'titles' for component type mx.containers.Panel.</strong>

* 에러 레벨: Error
* 발생 원인: 에러라인의 객체에서 정의도어있지 않은 속성을 사용하려고 할 때
* 코드 예시: \<mx : Panel titles = "Line Chart "\>
* 해결 방법: 코드 자동완성 기능이나 API 문서를 통해 그 클래스에서 사용가능한 정확한 속성명을 찾아서 정의함

<strong>Open quote is expected for attribute "title"</strong>

* 에러 레벨: Error
* 발생 원인: 에러라인의 태그에서 속성값의 시작 따옴표가 정의 되지 않았을 때
* 코드 예시: \<mx : panel titles = Line Chart"\> or \<mx : panel titles = 'Line Chart"\>
* 해결 방법: 속성값의 따옴표를 정확히 입력한다.

<strong>Data binding will not be able to detect assignments to :bindableVar"</strong>

* 에러 레벨: Warning
* 발생 원인: 변수가 바인딩 되어 있는데 [bindable] 표시를 하지 않아 발생
* 코드 예시: private var bindableVar : Number=0;
* 해결 방법: 바인딩하는 변수를 찾아서 [bindable] private var bindableVar : Number=0; 표시를 해준다.

<strong>다음 형식 주석이 컴파일 타입 상수가 아닙니다.</strong>

* 에러 레벨: Error
* 발생 원인: 컴파일 중에 참조하려는 객체나 속성이 없을때
* 코드 예시: 객체의 이름이나 속성이 잘못 되었거나 import 문을 써주지 않았을 때
* 해결 방법: 에러가 발생한 객체를 찾아서 import 문, 클래스명, 속성명 등이 정확한지 확인한다.

<strong>int가 관련없는 String 형식으로 암시적 강제 정의 되어있습니다.</strong>

* 에러 레벨: Error
* 발생 원인: 객체에 값을 설정하려고 하는데 타입이 맞지 않을 때
* 코드 예시: var test : String = "test"; test =1;
* 해결 방법: 에러가 발생한 코드를 찾아서 세팅되는 객체의 타입을 맞게 수정해 준다 / test = "1";

<strong>Definition sub : SubClass could not be found .</strong>

* 에러 레벨: Error
* 발생 원인: 특정 패키지에 있는 클래스를 찾을 수 없을 때
* 코드 예시: import sub.subclass
* 해결 방법: SubClass 에 대한 패키지명, 경로, 클래스명이 정확한지 확인한다.
