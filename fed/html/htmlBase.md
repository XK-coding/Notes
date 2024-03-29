# HTML基础
## 1.开发者文档
- W3C官网： www.w3c.org
- W3School： www.w3school.com.cn
- MDN： developer.mozilla.org —— 平时用的最多

## 2.排版标签
| 标签名 | 标签含义                                     | 单/双标签 |
| ------ | -------------------------------------------- | --------- |
| h1~h6  | 标题                                         | 双        |
| p      | 段落                                         | 双        |
| div    | 没有任何含义，用于整体布局（生活中的包装袋） | 双        |

1. h1 最好写一个， h2~h6 能适当多写
2. h1~h6 不能互相嵌套，例如： h1 标签中最好不要写 h2 标签了
3. p 标签很特殊！它里面不能有： h1~h6 、 p 、 div 标签

## 3.语义化标签
- 概念：用特定的标签，去表达特定的含义
- 原则：标签的默认效果不重要（后期可以通过 CSS 随便控制效果），语义最重要！
- 举例：对于 h1 标签，效果是文字很大（不重要），语义是网页主要内容（很重要）
- 优势：
	- 代码结构清晰可读性强。
	- 有利于 SEO（搜索引擎优化）
	- 方便设备解析（如屏幕阅读器、盲人阅读器等）

## 4. 块级元素 与 行内元素
1. 块级元素：独占一行（排版标签都是块级元素）
2. 行内元素：不独占一行（比如： input）
3. 使用原则：
> 1. 块级元素 中能写 行内元素 和 块级元素（简单记：块级元素中几乎什么都能写）。
> 2. 行内元素 中能写 行内元素，但不能写 块级元素。
> 3. 一些特殊的规则：
>  - h1~h6 不能互相嵌套。
> - p 中不要写块级元素。
> 备注： marquee 元素设计的初衷是：让文字有动画效果，但如今我们可以通过 CSS 来实现
> 了，而且还可以实现的更加炫酷，所以 marquee 标签已经：过时了（废弃了），不推荐使
> 用。

复制快捷键：alt + shift + 方向键（上or下），选中一行直接向上（下）复制
## 5.常用的文本标签
1. 用于包裹：词汇、短语等
2. 通常写在排版标签里面
3. 排版标签更宏观（大段的文字），文本标签更微观（词汇、短语）
4.  文本标签通常都是行内元素
![在这里插入图片描述](https://img-blog.csdnimg.cn/direct/41054f541724472ba5c7b096e48737e9.png)

## 6.不常用的文本标签
![在这里插入图片描述](https://img-blog.csdnimg.cn/direct/0e59318bf2724f188f008e17f2b7ca4c.png)
![在这里插入图片描述](https://img-blog.csdnimg.cn/direct/6c1384fd10174bdfb80d56b0a2e10ad1.png)
> 备注：
> 1. 这些不常用的文本标签，编码时不用过于纠结（酌情而定，不用也没毛病）。
> 2. blockquote 与 address 是块级元素，其他的文本标签，都是行内元素。
> 3. 有些语义感不强的标签，我们很少使用，例如：
> small 、 b 、 u 、 q 、 blockquote
> 4. HTML标签太多了！记住那些：重要的、语义感强的标签即可；截止目前，有这些：
> h1~h6 、 p 、 div 、 em 、 strong 、 span

## 7.图片标签
### 1.基本使用
![在这里插入图片描述](https://img-blog.csdnimg.cn/direct/81426021682941ed9a46adc598e6f840.png)
总结：
1. 像素（ px ）是一种单位
2. 尽量不同时修改图片的宽和高，可能会造成比例失调
3. 暂且认为 img 是行内元素
4. alt 属性的作用：
	- 搜索引擎通过 alt 属性，得知图片的内容。—— 最主要的作用
	- 当图片无法展示时候，有些浏览器会呈现 alt 属性的值
	- 盲人阅读器会朗读 alt 属性的值

### 2.路径的分类
#### 1.相对路径：以当前位置作为参考点，去建立路径
![在这里插入图片描述](https://img-blog.csdnimg.cn/direct/6f0d98d1ec114660b6521b708b025484.png)
注意点：
- 相对路径中的 ./（同级） 可以省略不写
- 相对路径依赖的是当前位置，后期若调整了文件位置，那么文件中的路径也要修改

#### 2.绝对路径：以根位置作为参考点，去建立路径
1. 本地绝对路径： E:/a/b/c/奥特曼.jpg （很少使用）
2. 网络绝对路径： http://www.atguigu.com/images/index_new/logo.png 

注意点：
使用本地绝对路径，一旦更换设备，路径处理起来比较麻烦，所以很少使用
使用网络绝对路径，确实方便，但要注意：若服务器开启了防盗链，会造成图片引入
失败

### 3.常见图片格式
#### 1.jpg格式：
概述：扩展名为 **.jpg** 或 **.jpeg** ，是一种有损的压缩格式（把肉眼不容易观察出来的细节
丢弃了）
主要特点：**支持的颜色丰富、占用空间较小**、不支持透明背景、不支持动态图
使用场景：对图片细节**没有极高要求**的场景，例如：网站的产品宣传图等 —— 该格式网
页中很常见
#### 2.png格式：
概述：扩展名为 **.png** ，是一种无损的压缩格式，能够更高质量的保存图片
主要特点：**支持的颜色丰富**、占用空间略大、**支持透明背景**、不支持动态图
使用场景：①想让图片有透明背景；②想更高质量的呈现图片；例如 ：公司logo图、重要配
图等
#### 3.bmp格式：
概述：扩展名为 **.bmp** ，不进行压缩的一种格式，在最大程度上保留图片更多的细节
主要特点：**支持的颜色丰富、保留的细节更多**、占用空间极大、不支持透明背景、不支持动
态图
使用场景：对图片细节**要求极高**的场景，例如：一些大型游戏中的图片 （网页中很少使
用）
#### 4.gif格式：
概述：扩展名为 **.gif** ，仅支持256种颜色，色彩呈现不是很完整
主要特点：支持的颜色较少、**支持简单透明背景、支持动态图**
使用场景：网页中的动态图片
#### 5.webp格式：
概述：扩展名为 **.webp** ，谷歌推出的一种格式，专门用来在网页中呈现图片
主要特点：具备上述几种格式的优点，但兼容性不太好，一旦使用务必要解决兼容性问题
使用场景：网页中的各种图片
#### 6.base64格式：
1. 本质：一串特殊的文本，要通过浏览器打开，传统看图应用通常无法打开
2. 原理：把图片进行 **base64** 编码，形成一串文本
3. 如何生成：靠一些工具或网站
4. 如何使用：直接作为 **img** 标签的 **src** 属性的值即可，并且不受文件位置的影响
5. 使用场景：一些较小的图片，或者需要和网页一起加载的图片

## 8.超链接
主要作用：从当前页面进行跳转。
可以实现：①跳转到指定页面、②跳转到指定文件（也可触发下载）、③跳转到锚点位置、④唤起指定应用
![在这里插入图片描述](https://img-blog.csdnimg.cn/direct/c5ac9f24eb804054b4b8f09ed5c0e3cd.png)
### 1.跳转到页面
```html
<!-- 跳转其他网页 -->
<a href="https://www.jd.com/" target="_blank">去京东</a>
<!-- 跳转本地网页 -->
<a href="./10_HTML排版标签.html" target="_self">去看排版标签</a>
```

> 注意点：
> 1. 代码中的多个空格、多个回车，都会被浏览器解析成一个空格！
> 2. 虽然 a 是行内元素，但 a 元素可以包裹除它自身外的任何元素！
### 2.跳转到文件
```html
<!-- 浏览器能直接打开的文件 -->
<a href="./resource/自拍.jpg">看自拍</a>
<a href="./resource/小电影.mp4">看小电影</a>
<a href="./resource/小姐姐.gif">看小姐姐</a>
<a href="./resource/如何一夜暴富.pdf">点我一夜暴富</a>
<!-- 浏览器不能打开的文件，会自动触发下载 -->
<a href="./resource/内部资源.zip">内部资源</a>
<!-- 强制触发下载 -->
<a href="./resource/小电影.mp4" download="电影片段.mp4">下载电影</a>
```

> 注意1：若浏览器无法打开文件，则会引导用户下载
> 注意2：若想强制触发下载，请使用 download 属性，属性值即为下载文件的名称
### 3.跳转到锚点
什么是锚点？—— 网页中的一个标记点
具体使用方式：
- 第一步：设置锚点
```html
<!-- 第一种方式：a标签配合name属性 -->
<a name="test1"></a>
<!-- 第二种方式：其他标签配合id属性 -->
<h2 id="test2">我是一个位置</h2>
```

> 注意点：
> 1. 具有 href 属性的 a 标签是超链接，具有 name 属性的 a 标签是锚点
> 2. name 和 id 都是区分大小写的，且 id 最好别是数字开头

- 第二步：跳转锚点
```html
<!-- 跳转到test1锚点-->
<a href="#test1">去test1锚点</a>
<!-- 跳到本页面顶部 -->
<a href="#">回到顶部</a>
<!-- 跳转到其他页面锚点 -->
<a href="demo.html#test1">去demo.html页面的test1锚点</a>
<!-- 刷新本页面 -->
<a href="">刷新本页面</a>
<!-- 执行一段js,如果还不知道执行什么，可以留空，javascript:; -->
<a href="javascript:alert(1);">点我弹窗</a>
```


### 4.唤起指定应用
通过 a 标签，可以唤起设备应用程序
```html
<!-- 唤起设备拨号 -->
<a href="tel:10010">电话联系</a>
<!-- 唤起设备发送邮件 -->
<a href="mailto:10010@qq.com">邮件联系</a>
<!-- 唤起设备发送短信 -->
<a href="sms:10086">短信联系</a>
```