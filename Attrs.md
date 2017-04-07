-------------------
    目录
    [TOC]
-------------------

<h3>1 浏览器私有属性</h3>
```css
**-ms**代表IE浏览器私有属性<br/>
**-webkit**代表chrome、safari私有属性<br/>
-moz代表firefox浏览器私有属性
```

------------------
<h3>2 Progressive enhancement (逐步增强)</h3>
```css
border-radius圆角
webkit-transform rotate(20deg)2D旋转
text-shadow文本阴影
box-shadow盒阴影
RGBA色彩空间
opacity透明度

多重背景图片
background:url(1.png) repeat-x top left,url(2.png) repeat-y bottom right;
```
----------------------

<h3>3 特殊属性</h3>
>堆叠顺序重要：浏览器私有属性写在公共属性前面。<br/>
>-ms-filter<br/>
>filter

- border-radius

- box-shadow

```css
box-shadow:[inset] x-offset y-offset blur-radius spread-radius color
外阴影会在对象背景之下，内阴影会在边框之下背景之上
整个层级是：边框>内阴影>背景图片>背景颜色>外阴影
```
- text-shadow

```css
3D text effect
.demo10 {
  color: #fff;
  text-shadow: 1px 1px rgba(197, 223, 248,0.8),2px 2px rgba(197, 223, 248,0.8),3px 3px rgba(197, 223, 248,0.8),4px 4px rgba(197, 223, 248,0.8),5px 5px rgba(197, 223, 248,0.8),6px 6px rgba(197, 223, 248,0.8);
}

Retro text effect复古
.demo11 {
  color: #eee;
  text-shadow: 5px 5px 0 #666, 7px 7px 0 #eee;
}
```

- gradient渐变

```css
线性渐变
{-webkit-linear-gradient(top,#ccc,#000);
-webkit-linear-gradient(45deg, #ace, #f96);}
角度表示逆时针，水平线和渐变线组成的角度

径向渐变
{background: -webkit-radial-gradient(bottom left, ellipse, #ace, #f96, #1E90FF);
background: -webkit-repeating-radial-gradient(#ace, #ace 5px, #f96 5px, #f96 10px);}

http://www.w3cplus.com/content/css3-gradient
```

- multiple background image

```
背景控制：
{background-size:100% auto;主体图像拉伸到浏览器窗口的宽度，并保持长宽比不变
background-attachment:fixed;}
图像不随滚动条而移动，一定要和background-image一起用才会有效。

```

- transform

```css
div{
transform: translate(50px, 100px);
-ms-transform: translate(50px,100px);
-webkit-transform: translate(50px,100px);
移动，translate(left,top)是transform的一个方法
http://www.cnblogs.com/mumu-web/p/5706779.html

transform:rotate(20deg);
-ms-transform:rotate(20deg); /* Internet Explorer */
-moz-transform:rotate(20deg); /* Firefox */
-webkit-transform:rotate(20deg); /* Safari 和 Chrome */
-o-transform:rotate(20deg); /* Opera */

transform:scale(1.2);
}
margin-left不如left流畅，left又比不上transform:translate的流畅度

```

- transition过渡

```css
{transition: property duration timing-function delay;}
属性名 all
持续时长 1s
过渡效果 ease
延迟（过渡开始的时间）0

.test{
    height: 100px;
    width: 100px;
    background-color: pink;
    transition: 3s all ease 0;
}    
.test:hover{
    width: 500px;
}
```

- animation

```css
img:hover{
  -webkit-animation:grow .5s 1;
  定义动画每0.5秒发生一次
}
@-webkit-keyframes grow{
  0%{-webkit-transform:scale(1)};
  30%{-webkit-transform:scale(1.2)};
  50%{-webkit-transform:scale(1.5)};
  60%{-webkit-transform:scale(1.2)};
  100%{-webkit-transform:scale(1)};
}
```

- border-image

```css
{
border-width:10px 20px 30px 10px;
border-image: url(2.jpg) 10 20 30 10 stretch;
-webkit-border-image:url(2.jpg) 10 20 30 10 stretch;}
图像一般中间透明，四周设计
chrome要写-webkit前缀

盒子和凸出
典型属性值：
{box-shadow: 0 0 5px rgba(0,0,0,0.5);}
无位移，隐约的模糊，使用rgba阴影更加的自然透明
```
