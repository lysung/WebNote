### 箭头函数
ES6开始支持  
使用箭头的方式定义函数，也就是通常所说的Lambda表达式

### 语法
```js
(x1, x2, ...) => { 函数体 }

如果函数体只有一行

(x1, x2, ...) => 表达式;


(x, y) => x + y;
//相当于
function(x, y) {
    return x + y;
}
```