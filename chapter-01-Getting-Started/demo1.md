

### 绘制流程包括一下几步：

1. 从svg根元素开始：
    * 应舍弃来自 (X)HTML的doctype声明，因为基于SVG的DTD验证导致的问题比它能解决的问题更多。
    * 属性version和属性baseProfile属性是必不可少的，供其它类型的验证方式确定SVG版本。
    * 作为XML的一种方言，SVG必须正确的绑定命名空间 （在xmlns属性中绑定）。 请阅读[命名空间速成](https://developer.mozilla.org/en/docs/Web/SVG/Namespaces_Crash_Course) 页面获取更多信息。
2. 绘制一个完全覆盖图像区域的矩形 &lt;rect/&gt;，把背景颜色设为红色。
3. 一个半径80px的红色圆圈&lt;circle/&gt;绘制在红色矩形的正中央 （向右偏移150px，向下偏移100px）。
4. 绘制文字“SVG”。文字被填充为白色， 通过设置居中的锚点把文字定位到期望的位置：在这种情况下，中心点应该对应于绿色圆圈的中点。还可以精细调整字体大小和垂直位置，确保最后的样式是美观的。


### SVG文件的基本属性


* 最值得注意的一点是元素的渲染顺序。SVG文件全局有效的规则是“后来居上”，越后面的元素越可见。
* web上的svg文件可以直接在浏览器上展示，或者通过以下几种方法嵌入到HTML文件中：
    * 如果HTML是XHTML并且声明类型为application/xhtml+xml，可以直接把SVG嵌入到XML源码中。
    * 如果HTML是HTML5并且浏览器支持HTML5，同样可以直接嵌入SVG。然而为了符合HTML5标准，可能需要做一些语法调整。
    * 可以通过 object 元素引用SVG文件：
    
> &lt;object data="image.svg" type="image/svg+xml" /&gt;

    * 类似的也可以使用 iframe 元素引用SVG文件：
> &lt;iframe src="image.svg"&gt;&lt;/iframe&gt;

    * 理论上同样可以使用 img 元素，但是在低于4.0版本的Firefox 中不起作用。
    * 最后SVG可以通过JavaScript动态创建并注入到HTML DOM中。 这样具有一个优点，可以对浏览器使用替代技术，在不能解析SVG的情况下，可以替换创建的内容。


