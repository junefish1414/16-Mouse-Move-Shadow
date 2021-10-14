
# DAY 16 - Mouse Move Shadow  筆記與心得

這次要製作的效果，主要是當滑鼠移動的時候，目標會產生影子偏移效果的物件。


![](https://i.imgur.com/UqsCp53.gif)


[DEMO](https://junefish1414.github.io/16-Mouse-Move-Shadow/)  |  [Code](https://github.com/junefish1414/16-Mouse-Move-Shadow)

## HTML / CSS 筆記摘要：
1. [(HTML5)可編輯的Table，contenteditable屬性](#一contenteditable屬性)
2. [(CSS) text-shadow的設定](#二text-shadow的設定)


## JavaScript 筆記摘要：
1. [Math.round()的用法](#一Mathround)
2. [ES6的解構賦值](#二ES6陣列和物件的解構賦值)
3. [JavaScript的offset家族](#三JavaScript的offset家族)

## CSS / HTMLm語法
### 一、contenteditable屬性
即使不靠vue的雙向綁定，只需要加上一個`contenteditable`屬性就可以直接讓HTML元件具備編輯的功能。
```htmlmixed
<div class="hero">
    <h1 contenteditable>🔥WOAH!</h1>
</div>
<!-- 直接在標籤裏面撰寫contenteditable就可以了 -->
```

</br>

### 二、text-shadow的設定

> text-shadow: X 軸方向的陰影 Y 軸方向的陰影 模糊範圍 陰影顏色;

```css
/* offset-x | offset-y | blur-radius | color */
text-shadow: 1px 1px 2px black;
```
> 1. 程式裏寫到下面這段，其實就是為 JavaScript 那邊綁定為 text 的 h1，動態加上文字陰影的 style。
> 2. text-shadow 可以設定為多重陰影，所以如下方程式碼，就設定了四個陰影。
```javascript
text.style.textShadow = `
	${xWalk}px ${yWalk}px 0px rgba(255, 255, 0,0.7),
	${xWalk * -1}px ${yWalk}px 0px rgba(255, 0, 255,0.7),
	${yWalk}px ${xWalk * -1}px 0px rgba(0, 255, 255,0.7),
	${yWalk * -1}px ${xWalk}px 0px rgba(0, 255,0 ,0.7)`
```







</br>

## JavaScript 語法

### 一、Math.round()
`Math.round()` 函數回傳四捨五入後的近似值.

> 如果小數位的部分值大於 0.5, 這個值將會進位. 如果小數位的部分值小於 0.5, 這個值將不會進位.


```javascript
// Returns the value 20
x = Math.round(20.49);

// Returns the value 21
x = Math.round(20.5);

// Returns the value -20
x = Math.round(-20.5);
```
</br>

### 二、ES6陣列和物件的解構賦值

神奇的解構賦值(Array and Object Destructuring Assignment )，在練習撰寫 JavaScript 30 的時候無意間看到其它人的寫法，好奇之下查了一下，不查沒事，一查不得了阿~ 彷彿又發現了一個新世界，沒有想到 array 跟 Object 也可以這樣寫！

所謂的`Destructuring`，就如其字面意思，把東西解構再賦值，相信到這裡可能還是有點抽象，沒關係我們來看個例子。
</br>


>**正式定義**：ES6 的 destructuring assignment，可以用來從陣列或物件中抽取 (destructuring) 值出來指定 (assignment) 給變數。






### Array Destructuring 陣列的解構賦值
* 在 ES6 之前，賦值給一個變量，只能用指定的方式：
```javascript
const a = "apple";
const b = "banana";
const c = "orange";
```

* ES6之後，你可以用Destructuring這樣寫：
```javascript
const array = ["apple","banana","orange"];
const [a, b, c] = array;

console.log(a); // apple
console.log(b); // banana
console.log(c); // orange

```

* [更多ES6解構賦值文章參考](https://www.fooish.com/javascript/ES6/array-and-object-destructuring.html)


</br>

### 三、JavaScript的offset家族
* [offset功能文章參考](https://www.gushiciku.cn/pl/pD8z/zh-tw)
