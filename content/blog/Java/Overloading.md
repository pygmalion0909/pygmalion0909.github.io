---
title: 'Overloading - 오버로딩'
date: 2021-04-25 13:15:00
category: 'Java'
draft: false
---
Overload의 사전적 의미는 "초과 적재", "과부하"이다.  
전혀 느낌이 오지 않는다. 무엇을 쌓는다는 건가?!  
<br>
Overloading을 한마디로 정의하자면!  
할 수 없다. 어휘력 부족......😿  
<br>
그러니까. 그. 뭐냐. Um... Java에 class가 있다. 
class에 메소드를 만드는데 메소드 이름을 중복으로 여러 개 만든다.  
원래 메소드 이름이 중복되면 에러가 발생하지만 약간의 규칙을 준수하여 만들면 에러가 발생하지 않고 만들 수 있다. 이것을 Overloading이라 한다.  
<br>
여기서 의문이 든다.  
왜 같은 이름의 메소드를 굳이! 여러 개 만들까?!

## Overloading 예제
Overloading에는 메소드 Overloading, 생성자 Overloading 2가지가 있다.  
먼제 메소드 Overloading부터 보자.

### 메소드 Overloading
```java
  public class Overloading {

  public int sumMethod(int a, int b) {
  	return a + b;
  }

  public int sumMethod(int a, int b, int c) {
  	return a + b + c;
  }

  public double OverloadingMethod(int a, double b) {
  	return a + b;
  }

  public double OverloadingMethod(double a, int b) {
  	return a + b;
  }

   public void UseMethod() {
     int resultA = OverloadingMethod(1, 2);
     int resultB = OverloadingMethod(1, 2, 3);
     double resultC = OverloadingMethod(1, 1.6);
     double resultD = OverloadingMethod(1.6, 1);

    System.out.println("===resultA===" + resultA); //3
    System.out.println("===resultB===" + resultB); //6
    System.out.println("===resultC===" + resultC); //2.6
    System.out.println("===resultD===" + resultD); //2.6
   }

}
```
**👉 public class Overloading { .. }**  
Overloading class를 만들었다. class내부에 sum 하는 기능을 가진 메소드를 만들어 보자.  
<br>

**👉 public int sumMethod(int a, int b) { .. }**  
첫 번째 메소드는 int타입 a, b를 받아 덧셈하는 기능이다.  
<br>

**👉 public int sumMethod(int a, int b, int c) { .. }**  
두 번째 메소드는 int타입 3개를 받아 덧셈하는 기능이다.  
<br>

**👉 public int sumMethod(int a, double b) { .. }**  
세 번째 메소드는 int, double타입 각각 한 개씩 받아 덧셈하는 기능이다.  
<br>

**👉 public int sumMethod(double a, int b) { .. }**  
네 번째 메소드는 세 번째 메소드의 파라미터 순서만 바꿨다.  
<br>

**👉 public void UseMethod() { .. }**  
위에서 만든 3개의 메소드들의 호출하여 실제로 사용하는 메소드다.  

위 코드를 살짝만! 봐도 4개의 메소드의 공통점과 차이점을 쉽게 파악할 수 있다.  
공통점은 덧셈하는 기능이다.  
차이점은 덧셈의 개수 또는 타입, 순서가 다르다.
<br>

Overloading은 같은 기능을 가진 메소드들을 이름으로 분리하지 않고 파라미터 타입, 개수, 순서로 구분 지어 사용할 수 있게 한다. 만약, Overloading을 하지 않는다면 어떻게 될까?  
Overloading을 하지 않을 경우 아래 코드와 같이 이름으로 구분 지어야 한다.  
sumMethodTwoInt, sumMethodThreeInt, sumMethodString......  
만약, 동일한 기능에 다른 타입의 메소드가 더 필요하다면?!  

### 생성자 Overloading
```css
#drop_the_text input{
  background: #343a40;
  background-image: url(list.png);
  background-position: 5px center;
  padding-left: 40px;
  border: 1px solid #2e3238;
  width: 100%;
  height: 30px;
  box-sizing: border-box;
  outline: none;
  border-radius: 3px;
}
```
👉 **background-image: url(list.png)**  
배경 이미지로 아이콘 이미지를 넣는다.
<br/>
<br/>

👉 **background-repeat: no-repeat**  
이미지가 작아서 반복이 된다. no-repeat을 사용하여 반복 없이 이미지 한 개만 나오게 한다.
<br/>
<br/>

👉 **background-position: 5px center**  
input영역 안에서 이미지를 원하는 위치를 정한다. 5px은 x축 위치 값, center은 y축 위치값
단위는 px, %, top, center, left, right 가 있다.
<br/>
<br/>

👉 **padding-left: 40px**  
padding값이 없으면 HTML에서 설정한 placeholder="Add List"와 겹쳐진다. 그래서 padding값을 줘서 겹침 현상을 없앤다. input을 클릭했을 때 padding값만큼
<br/>
<br/>
 

👉 **box-sizing: border-box**  
inputd에 width: 100% 가 있어서 box-sizing코드가 없으면 input의 넓이가 부모 넓이보다 넘는 현상이 발생한다.  
box-sizing: border-box을 사용하여 input 넓이를 부모 넓이와 같게 한다. input의 width를 부모보다 작게 줄 경우 box-sizi코드는 필요 없다. 
<br/>
<br/>