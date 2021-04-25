---
title: 'input에 아이콘 넣기'
date: 2021-04-25 12:37:00
category: 'Css'
draft: false
---
### 최종결과
![최종결과](./images/input에아이콘넣기_1.jpg)

### HTML
```html
  <div id="drop_the_text">
    <input type="text" placeholder="Add List" id="write_list">
  </div>
```
### CSS
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