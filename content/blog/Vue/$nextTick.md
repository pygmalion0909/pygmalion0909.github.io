---
title: '$nextTick'
date: 2021-04-20 22:23:00
category: 'Vue'
draft: false
---
오디오 파일을 읽어 파형을 화면에 출력 하는 프로젝트를 맡았다.  
오디오 파일을 읽어 직접 파형을 그려주는 개발을 하고 싶지만 시간이 많이 부족해 라이브러리를 사용하게 되었다.

다양한 라이브러리가 있었지만 그 중 [wavesurfer.js](https://wavesurfer-js.org/)를 선택했다.  
선택한 이유는 그나마 공식문서가 잘되어 있고 다양한 예제가 많아서다.

호~오옥시나 했지만 역시나! wavesurfer.js를 사용하는게 쉽지 않았다.  
wavesurfer.js를 사용하기 위해서 `wavesurfer.create()`를 사용하여 wave객체를 생성해야 된다.  
"단순하게 create()메소드 사용해서 생성하면 되겠지?"라고 생각했지만. 큰 오산이였다.  
공식문서에서 `wavesurfer.create()`로 wave객체를 생성하고 Dom에(HTML태그)에 부착(삽입)하라고 하셔서 따라했다. 하지만 아래와 같은 에러가 발생하면서 wave객체가 Dom에 부착 되지 않았다.
```js
TypeError: Cannot read property 'getElementsByTagName' of undefined
```
vue의 가상돔 개념도 없었고 $nextTick도 전혀 알지 못 했기에 에러의 원인을 알지 못했다.  
"왜?? 안될 수가 없는데?"라는 생각만 계속하던 중 에러 구문을 그대로 복사하여 구글링하니 바로 원인을 알 수 있었다.(역시 구글형님❤️)

### 개념 
1. `Vue`에서 UI를 직접 건드리는 경우에 DOM을 찾지 못하는 경우 오류가 발생한다.
1. `data`에 값이 입력되면, `Vue`에서 데이터갱신을 감지하여 UI를 갱신하는데, UI가 갱신 되기 전에 Dom들을 탐색하는 상황이 발생한다.

### 에러 코드
```html
<div>
  <div class="wave"></div>
</div>
<script>
export default{
  data(){
    return{
      wave: '',
    }
  },
  create(){
    this.wave = Wavesurfer.create();
  }
}
</script>
```

### 수정 코드
```html
<div>
  <div class="wave"></div>
</div>
<script>
export default{
  data(){
    return{
      wave: '',
    }
  },
  create(){
    this.wave = Wavesurfer.create();
  }
}
</script>
```

### 참고자료
1. [$nextTick설명글](https://jinblog.kr/178) 