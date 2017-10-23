# 使用纯CSS实现移动菜单更改内容区功能

首先先放一张效果图

![效果图](../img\GIF.gif)

HTML主题

```html
<div>
	<div class="a">菜单1</div>
	<div class="a">菜单2</div>
	<div class="b">内容1</div>
	<div class="b">内容2</div>
</div>
```

css部分

```css
/*主体样式 */
.a
{
    float: left;
    width: 100px;
    height: 40px;
    margin: 2px;
    background-color: #29b6f6;
}
.b
{
    clear: both;
    width: 204px;
    height: 200px;
    margin: 2px;
    background-color: #8bc34a;
}
.b:nth-child(4)
{
    display: none;
    background-color: #ffeb3b;
}
/*内容切换*/
.a:nth-child(1):hover ~ .b:nth-child(3)
{
    display: block;
}
.a:nth-child(1):hover ~ .b:nth-child(4)
{
    display: none;
}
.a:nth-child(2):hover ~ .b:nth-child(3)
{
    display: none;
}
.a:nth-child(2):hover ~ .b:nth-child(4)
{
    display: block;
}
```
> | 选择器                                      | 例子             | 例子描述                       | CSS  |
> | ---------------------------------------- | -------------- | -------------------------- | ---- |
> | [:nth-child(*n*)](http://www.w3school.com.cn/cssref/selector_nth-child.asp) | p:nth-child(2) | 选择属于其父元素的第二个子元素的每个 <p> 元素。 | 3    |
> | [:hover](http://www.w3school.com.cn/cssref/selector_hover.asp) | a:hover        | 选择鼠标指针位于其上的链接。             | 1    |
> | [*element1*~*element2*](http://www.w3school.com.cn/cssref/selector_gen_sibling.asp) | p~ul           | 选择前面有 <p> 元素的每个 <ul> 元素。   | 3    |

- 首先，我们通过`:nth-child(n)`伪类定位到相应的元素（菜单）上；
- 然后，使用`:hover`选择器获取在鼠标移至菜单时的菜单元素，
- 接着使用`~`选择器获取在鼠标移至菜单时的菜单元素后跟着的内容元素。
- 这样我们就可以通过改变`display`属性来改变内容区的内容了。

这种方法只能在鼠标移至菜单项时改变内容区的内容和样式，在鼠标移开时，内容区恢复默认。

