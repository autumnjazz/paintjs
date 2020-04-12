## 노마드 코더 vanilla js 연습

---

### css 초기화 하기

reset.css

# 

### range bar 만들기

`<input type="range" min = "0.1" max="5.0" vaue="2.5" steps="0.1">`

```js
if(range){
    range.addEventListener("input", handleRangeChange);
}
```

항상 if 문으로 변수가 NULL 이 아닌지 확인한다.

range 는 input 이기 때문에 EventListener 가 "input" 이다.

# 

### canvas 안에 들어온 마우스의 움직임 감지하기

[https://developer.mozilla.org/ko/docs/Web/API/CanvasRenderingContext2D](https://developer.mozilla.org/ko/docs/Web/API/CanvasRenderingContext2D)

`<canvas width="700px" height="700px"></canvas>` 처럼 사용해야 한다.

`ctx.beginPath();` 는 경로 만들기를 시작하는 함수이다. 

`ctx.moveTo(x,y);` 로, 마우스가 움직일 때마다 경로의 시작 좌표를 옮겨주고

`ctx.lineTo(x, y);` 로 시작 좌표부터 현재 좌표까지 선을 그린다.


# 

### document.getElementsByClassName

`const colors = document.getElementsByClassName("jsColor");` 를 하면 HTTML Collection 이 반환된다.

Array 형식으로 변환하기 위해서는 `Array.from(colors)` 를 사용한다.

Array 에 있는 각각의 객체를 사용하기 위해서는 다음과 같이 작성한다.

```js 
Array.from(colors).forEach(color => 
    color.addEventListener("click", handleColorClick)
); 
```

`event.target.style` 을 하면 css 정보를 불러올 수 있다.

# 

### 오른쪽 마우스 클릭 방지

```js
canvas.addEventListener("contextmenu", handleCM);


function handleCM(event){
    event.preventDefault();
}
```

# 

### 이미지 저장

```js
const link = document.createElement("a"); //<a> 태그를 만든다
link.href = canvas.toDataURL("image/jpeg");
link.download = "paintJS.png"; //<a> 태그의 download 속성
link.click(); //link 를 클릭한 효과
```