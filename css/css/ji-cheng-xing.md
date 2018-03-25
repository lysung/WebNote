### 继承性
有一些属性，当给自己设置的时候，自己的后代都继承上了，这个就是继承性。

#### 那些属性能继承
color、 text-开头的、line-开头的、font-开头的。  
这些关于**文字样式**的，都能够继承； 所有**关于盒子的、定位的、布局的属性**都**不能继承**。  
继承性是从自己开始，直到最小的元素。  

如果所有的页面的文字都是红色，都是16px，可以利用继承性:  

```html
body {
    color: red;
    font-size: 16px;
}
```

### 层叠性
是css处理冲突的能力

#### 权重
当选择器，**选择上了**某个元素的时候，那么要这么统计权重：  
**id的数量，类的数量，标签的数量**  

```html
<style type="text/css">
    /*权重为 1,1,1 */
    #hezi1 .box2 p {
        color: red;
    }
    /*权重为 1,0,3*/
    div div #hezi3 p{
        color: blue;
    }
    /*权重为 0,3,4*/
    div.box1 div.box2 div.box3 p {
        color: green;
    }
</style>
......
<div id="hezi1" class="box1">
    <div id="hezi2" class="box2">
        <div id="hezi3" class="box3">
            <p>我是什么颜色</p> // 为红色
        </div>
    </div>
</div>
```

不进位，实际上能进位（255个标签，等于1个类名）但是没有实际意义！  

**如果权重一样**，谁写在后面谁起作用。

```html

......
<div id="hezi1" class="box1">
    <div id="hezi2" class="box2">
        <div id="hezi3" class="box3">
            <p class="pp">我是什么颜色</p>
        </div>
    </div>
</div>
```