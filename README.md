## 响应式网站概念
 * 弹性网格布局
 * 弹性图片
 * 媒体查询
 
## 响应式网站优点
 * 减少工作量
 
   > 网站、设计、代码、内容都只需要一份
   
   > 多出来的工作量只是在js脚本和css样式上做一点改动
   
 * 节省时间
 * 每个设备都能得到正确的设计
 * 搜索优化
 
## 缺点
 * 加载更多的样式和资源
 * 设计比较难精确定位和控制
 * 老版本浏览器兼容不好

## 浏览器相关网址
 * http://caniuse.com/
 * http://gs.statcounter.com/
 * http://x5.tencent.com/tbs/
 
## 媒体查询
 * 使用 @media 查询，可以针对不同的媒体类型、屏幕尺寸定义不同的样式。当重置浏览器大小的过程中，页面也会根据浏览器的宽度和高度重新渲染页面。
 * css语法
 ```
 @media mediatype and|not|only (media feature) {
    CSS-Code;
 }
 ```
 
   > and not only是逻辑操作符。其实媒体查询就是一段媒体表达式，对操作符所连接的表达式计算完返回布尔值，返回真，那么样式被应用。
   
   > 也有用逗号分隔，相当于or，任意条件匹配一个
   ```
   @media not screen and (color),print and (color)
   ```
   
   > not后面跟着这样一段是括起来的，上面等价于下面这段,只作用于逗号之前
   ```
   @media (not (screen and (color))),print and (color)
   ```
   
   > only“仅仅”的意思，在老的浏览器如果不支持媒体查询，加了only，它会解释为：media="only"。另外如果要考虑老的浏览器，可以加下面这段,表示如果有的用户电脑里面装了这个chrome的插件，就可以让电脑里面的IE不管是哪个版本的都可以使用Webkit引擎及V8引擎进行排版及运算，如果用户没装这个插件，那这段代码就会让IE以最高的文档模式展现效果
   ```
   <meta http-equiv="X-UA-Compatible" ;content="IE=edge, chrome=1">
   ```
   
 * 媒体类型
 
   > all 	用于所有设备
   
   > print 	用于打印机和打印预览
   
   > screen 	用于电脑屏幕，平板电脑，智能手机等
   
   > speech 	应用于屏幕阅读器等发声设备
   
 * 所有的媒体属性
 
   > aspect-ratio 	定义输出设备中的页面可见区域宽度与高度的比率
   
   > color 	定义输出设备每一组彩色原件的个数。如果不是彩色设备，则值等于0
   
   > color-index 	定义在输出设备的彩色查询表中的条目数。如果没有使用彩色查询表，则值等于0
   
   > device-aspect-ratio 	定义输出设备的屏幕可见宽度与高度的比率。
   
   > device-height 	定义输出设备的屏幕可见高度。
   
   > device-width 	定义输出设备的屏幕可见宽度。
   
   > grid 	用来查询输出设备是否使用栅格或点阵。
   
   > height 	定义输出设备中的页面可见区域高度。
   
   > max-aspect-ratio 	定义输出设备的屏幕可见宽度与高度的最大比率。
   
   > max-color 	定义输出设备每一组彩色原件的最大个数。
   
   > max-color-index 	定义在输出设备的彩色查询表中的最大条目数。
   
   > max-device-aspect-ratio 	定义输出设备的屏幕可见宽度与高度的最大比率。
   
   > max-device-height 	定义输出设备的屏幕可见的最大高度。
   
   > max-device-width 	定义输出设备的屏幕最大可见宽度。
   
   > max-height 	定义输出设备中的页面最大可见区域高度。
   
   > max-monochrome 	定义在一个单色框架缓冲区中每像素包含的最大单色原件个数。
   
   > max-resolution 	定义设备的最大分辨率。
   
   > max-width 	定义输出设备中的页面最大可见区域宽度。
   
   > min-aspect-ratio 	定义输出设备中的页面可见区域宽度与高度的最小比率。
   
   > min-color 	定义输出设备每一组彩色原件的最小个数。
   
   > min-color-index 	定义在输出设备的彩色查询表中的最小条目数。
   
   > min-device-aspect-ratio 	定义输出设备的屏幕可见宽度与高度的最小比率。
   
   > min-device-width 	定义输出设备的屏幕最小可见宽度。
   
   > min-device-height 	定义输出设备的屏幕的最小可见高度。
   
   > min-height 	定义输出设备中的页面最小可见区域高度。
   
   > min-monochrome 	定义在一个单色框架缓冲区中每像素包含的最小单色原件个数
   
   > min-resolution 	定义设备的最小分辨率。
   
   > min-width 	定义输出设备中的页面最小可见区域宽度。
   
   > monochrome 	定义在一个单色框架缓冲区中每像素包含的单色原件个数。如果不是单色设备，则值等于0
   
   > orientation 	定义输出设备中的页面可见区域高度是否大于或等于宽度。
   
   > resolution 	定义设备的分辨率。如：96dpi, 300dpi, 118dpcm
   
   > scan 	定义电视类设备的扫描工序。
   
   > width 	定义输出设备中的页面可见区域宽度。

 * 如何使用
   
   > 首先需要在html文档中添加以下代码，用来兼容移动设备的显示效果
   ```
   <meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1,minimun-scale=1,user-scalable=no"/>
   ```
   
   > 在css文件中写入媒体查询语法
   
 * 视口
 
   > 布局视口，一开始用一个虚拟的960px宽度，来把网页布局出来。用户缩放不会改变布局视口大小
   
   > 可视视口，网页在手机上呈现出来的区域的宽度，用户缩放可以改变可视视口大小
   
   > 理想视口，布局视口在一个设备上的最佳尺寸，不需要缩放可以很好的查看页面。理想视口为构建手机浏览器优化的页面而添加的。上面的width=device-width设置就是将布局视口设置为设备的可视视口宽度
   
## 分析设计图
 * 拿到设计图，首先与产品经理、设计师沟通交互及规范等，然后进行结构和布局分析
 
## 实践原则
 * 渐进增强与优雅降级：参考此文 http://www.jianshu.com/p/d313f1108862
 * 优先针对大屏幕设计还是小屏幕，与习惯和网站性质有关，可以对受众比较多的先设计
 * 先对最新版的Chrome浏览器调试，调试方便，用户占比高
 * 断点的选择，媒体查询中的临界点，如最大宽度最小宽度等，按照屏幕的大小来设置断点
 
## 学习笔记
 * 一般使用class定义样式，id一般用于js快速区别和获取元素，class一般用中横线分隔，id用驼峰式命名
 * 必不可少的图片使用`<img>`引入，可有可无的装饰性图片用标签的style引入
 * 重置css，用normalize.css:保护了有价值的默认值;修复了浏览器的bug;不会让你的调试工具变的杂乱;是模块化的;拥有详细的文档。参考 http://jerryzou.com/posts/aboutNormalizeCss/
 * 任意浏览器的默认字体高都是16px。所有未经调整的浏览器都符合: 1rem=16px。那么12px=0.75rem,10px=0.625rem。为了简化font-size的换算，需要在css中的body选择器中声明font-size=62.5%，这就使rem值变为 16px*62.5%=10px, 这样12px=1.2rem, 10px=1rem, 也就是说只需要将你的原来的px数值除以10，然后换上rem作为单位就行了。所以我们在写CSS的时候，需要注意两点：
    * body选择器中声明font-size=62.5%；
    * 将你的原来的px数值除以10，然后换上rem作为单位；
    * 重新计算那些被放大的字体的rem数值。避免字体大小的重复声明。
 * 清除浮动：
 ```
 .clearfix:after {
     content:'';
     display:table;
     clear:noth
 }
 ```
 
 * 
   
