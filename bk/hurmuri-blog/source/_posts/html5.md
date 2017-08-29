---
title: HTML5
date: 2015-07-10 13:08:51
tags: [HTML5, JavaScript]
categories: 学习资料
---

## 关于HTML5

### 起步

HTML5 是 **W3C** 与 **WHATWG** 合作的结果,WHATWG 指 Web Hypertext Application Technology Working Group。  
WHATWG 致力于 web 表单和应用程序，而 W3C 专注于 XHTML 2.0。  
在 2006 年，双方决定进行合作，来创建一个新版本的 HTML。  

### 简介

HTML5 是HTML最新的修订版本，2014年10月由万维网联盟（W3C）完成标准制定。

HTML5 的设计目的是为了在移动设备上支持多媒体。

HTML5 简单易学。
<!--more-->
### 理解  

对比之前的html版本html到底有那些增强？  
什么是html5？

我们日常讨论的H5其实指的是一个范称，它是由HTML5 + CSS3 + Javascript等技术组合而成的一个应用开发平台。

## html 提升

### 文档声明

<!doctype> 声明必须位于 HTML5 文档中的第一行,使用非常简单:
```html
    <!DOCTYPE html>
```

### 文档骨架

```html
    <!DOCTYPE html>
    <html lang="en">
        <head>
        <meta charset="utf-8">
        <title>文档标题</title>
        </head>
        <body>
        文档内容......
        </body>
    </html>
```

注意：
<html lang="en"> 申明文档语言
<meta charset="utf-8"> 声明编码，中文否则会出现乱码。

特点： 
结构简洁，语法宽松。

W3C验证地址 https://validator.w3.org/


### 标签

#### 语义标签
|标签|解释|
|----|----|
|header|	定义了文档的头部区域
|nav|	定义导航链接的部分。
|section|	定义文档中的节（section、区段）。
|article|	定义页面独立的内容区域。
|aside|	定义页面的侧边栏内容。
|figure|	规定独立的流内容（图像、图表、照片、代码等等）。
|figcaption|	定义 figure 元素的标题
|dialog|	定义对话框，比如提示框
|footer|	定义 section 或 document 的页脚。
|----|----|
|bdi|	允许您设置一段文本，使其脱离其父元素的文本方向设置。
|command|	定义命令按钮，比如单选按钮、复选框或按钮
|details|	用于描述文档或文档某个部分的细节
|summary|	标签包含 details 元素的标题
|mark|	定义带有记号的文本。
|meter|	定义度量衡。仅用于已知最大和最小值的度量。
|progress|	定义任何类型的任务的进度。
|ruby|	定义 ruby 注释（中文注音或字符）。
|rt|	定义字符（中文注音或字符）的解释或发音。
|rp|	在 ruby 注释中使用，定义不支持 ruby 元素的浏览器所显示的内容。
|time|	定义日期或时间。
|wbr|	规定在文本中的何处适合添加换行符。

经典网页布局传统版
```html
    <body>
        <!-- 头部 -->
        <div class="header">
            <ul class="nav"></ul>
        </div>
        <!-- 主体部分 -->
        <div class="main">
            <!-- 文章 -->
            <div class="article"></div>
            <!-- 侧边栏 -->
            <div class="aside"></div>
        </div>
        <!-- 底部 -->
        <div class="footer"></div>
    </body>
```
经典网页布局HTML5版
```html
    <body>
    	<!-- 头部 -->
    	<header>
    		<nav class="nav"></nav>
    	</header>
    	<!-- 主体部分 -->
    	<main class="main">
    		<!-- 文章 -->
    		<article></article>
    		<!-- 侧边栏 -->
    		<aside></aside>
    	</main>
    	<!-- 底部 -->
    	<footer></footer>
    </body>
```

本质上新语义标签与div、span没有区别，只是其具有表意性。  
使用时除了在HTML结构上需要注意外，其它和普通标签的使用无任何差别。         
可以理解成&lt;div class="nav"&gt; 相当于 &lt;nav&gt;,**不要好奇，它只是一个标签！**  
**注意：**尽量避免全局使用header、footer、aside等语义标签。


#### 兼容处理

越来越多的站点开始使用 HTML5 标签。但情况是还有很多人在使用IE6，IE7，IE8。

在不支持HTML5新标签的浏览器里，会将这些新的标签解析成行内元素(inline)对待，

所以我们只需要将其转换成块元素(block)即可使用，

但是在IE9版本以下，并不能正常解析这些新标签，

但是却可以识别通过document.createElement('tagName')创建的自定义标签，

于是我们的解决方案就是将HTML5的新标签全部通过document.createElement('tagName')来创建一遍，

这样IE低版本也能正常解析HTML5新标签了，

在实际开发中我们更多采用的是通过检测IE浏览器的版本来加载第三方的一个JS库来解决兼容问题。

**html5shiv** 
```html
    <!--[if lt IE 9]>
    <script type="text/javascript" src="js/html5shiv.js"></script>
    <![endif]-->    
```
下载地址 http://www.bootcdn.cn/html5shiv/

#### 案例练习

博客文章


### 表单

#### 输入类型

HTML5 拥有多个新的表单输入类型。这些新特性提供了更好的输入控制和验证。  
本章全面介绍这些新的输入类型：
  
|类型|说明|
|----|----|
|email|  在提交表单时，会自动验证 email 域的值是否合法有效
|url|  定义输入URL字段,在提交表单时，会自动验证 url 域的值
|tel|  定义输入电话号码字段
|number|  定义一个数值输入域(限定):<br>max- 规定允许的最大值<br>min - 规定允许的最小值<br>step - 规定合法的数字间隔（如果 step="3"，则合法的数是 -3,0,3,6 等）<br>value - 规定默认值
|search| 定义一个搜索字段 (类似站点搜索或者Google搜索) 
|----|----|
|range|  定义一个不需要非常精确的数值（类似于滑块控制）:<br>max- 规定允许的最大值<br>min - 规定允许的最小值<br>step - 规定合法的数字间隔（如果 step="3"，则合法的数是 -3,0,3,6 等）<br>value - 规定默认值
|color|  从拾色器中选择一个颜色
|time|  定义可输入时间控制器
|date| 定义一个时间控制器
|week|  定义周和年
|month|  定义月与年 
|datetime|  定义一个日期和时间控制器 兼容性差
|datetime-local|  定义一个日期和时间


注意:并不是所有的主流浏览器都支持新的input类型，不过您已经可以在所有主流的浏览器中使用它们了。即使不被支持，仍然可以显示为常规的文本域。 
部分类型是针对移动设备生效的，且具有一定的兼容性，在实际应用当中可选择性的使用。

**虚拟键盘调用**
```html
    <input type="text" name="txt_text" id="txt_text">
    <input type="number" name="txt_number" id="txt_number">
    <input type="email" name="txt_email" id="txt_email">
    <input type="tel" name="txt_tel" id="txt_tel">
    <input type="url" name="txt_url" id="txt_url">
    <input type="search" name="txt_search" id="txt_search"> 在移动端虚拟键盘会有搜索按钮
```

#### 表单标签

datalist  元素规定输入域的选项列表。

```html
<input list="browsers">

<datalist id="browsers">
  <option value="Internet Explorer">
  <option value="Firefox">
  <option value="Chrome">
  <option value="Opera">
  <option value="Safari">
</datalist>
```
 
keygen 生成加密字符串  

当提交表单时，会生成两个键，一个是私钥，一个公钥。
私钥（private key）存储于客户端，公钥（public key）则被发送到服务器。

```html
<form action="keygen.do" method="get">
用户名: <input type="text" name="usr_name">
加密: <keygen name="security">
<input type="submit">
</form>
```
output 元素用于不同类型的输出,不可当做数据提交  
   
```html
<form oninput="x.value=parseInt(a.value)+parseInt(b.value)">0
<input type="range" id="a" value="50">100 +
<input type="number" id="b" value="50">=
<output name="x" for="a b"></output>
</form>
```


#### 表单属性

- form
    + autocomplete 设置整个表单是否开启自动完成 on|off
    + novalidate 设置H5的表单校验是否工作 true 不工作  不加该属性代表校验

- input:
    + autocomplete 单独设置每个文本框的自动完成
    + autofocus 设置当前文本域页面加载完了过后自动得到焦点
    + list 作用就是指定当前文本框的自动完成列表的数据 datalist 在界面上是看不见的，只是用于定义数据列表的
    + multiple 文本域的多选 
    + pattern 设置文本框的匹配格式（正则）
    + placeholder 文本框占位符
    + required 限制当前input为必须的
    + form 属性是让表单外的表单元素也可以跟随表单一起提交
- submit:
    + form 在submit上重写表单的特定属性，当点击当前submit时会以当前值使用
        * formaction, 
        * formenctype,
        * formmethod,
        * formnovalidate,
        * formtarget

#### 表单事件

 -  oninput 用户输入内容时触发，可用于移动端输入字数统计
 -  oninvalid 验证不通过时触发，
    + setCustomValidity 设置自定义提示 (验证通过需要本身合法并且没有提示信息)

#### 案例练习

学生档案
```html
    <form action="">
        <fieldset>
            <legend>学生档案</legend>
            <label>
                姓名: <input type="text" pattern="{6,10}" name="username" placeholder="请输入姓名" id="username" required autofocus >
            </label>
            <label>
                手机号码: <input type="text" name="mobile" placeholder="请输入手机号" required pattern="^1\d{10}$"  >
            </label>
            <label>
                邮箱地址: <input type="email" name="email" placeholder="请输入邮箱地址" required  >
            </label>
            <label>
                所属学院: <input type="text" name="course" list="course" placeholder="请输入所属学院"  >
                <datalist id="course">
                    <option value="前端与移动开发"></option>
                    <option value="PHP"></option>
                    <option value="JAVA"></option>
                    <option value="Android"></option>
                    <option value="IOS"></option>
                    <option value="UI设计"></option>
                    <option value="C++"></option>
                </datalist>
            </label>
            <label>
                入学成绩: <input id="score" name="score" type="number" min="0" max="100" step="10" value="60"/>
            </label>
            <label>
                基础水平: <meter id="level" name="level" min="0" max="100" low="60" high="80" value="70"></meter>
            </label>
            <label>
                入学日期: <input type="date" value="2016-07-03">
            </label>
            <label>
                毕业时间: <input type="date" value="2016-11-03">
            </label>
            <label>
                课程进度: <progress max="100" value="30"></progress>
            </label>
            <input type="submit" value="保存"/>
        </fieldset>
    </form>
    <script>
        /*获取到姓名元素*/
        var username = document.getElementById("username");
        /*如果有提示内容 也会触发这个事件*/
        username.oninvalid = function(){
            console.log('oninvalid');
        };
    
        /*动态的展示入学成绩的水平*/
        /*获取到入学成绩这个元素*/
        var scoreInput = document.getElementById('score');
        /*水平元素*/
        var levelMeter = document.getElementById('level');
    
        /*监听score的值的改变*/
        scoreInput.oninput = function(){
            /*怎么样让水平状态改变*/
            levelMeter.value = this.value;
        }
    
    </script>
```

### 多媒体

#### 音频

- 定义音频播放组件

```html
<audio src="要播放的音频文件"></audio>
```

#### 视频

- 定义播放视频组件

```html
<video src="要播放的视频文件"></video>
```

#### 旧版本浏览器提示

- 如果HTML中遇到不能识别的标签，就会将该标签当做DIV(块级元素) 
- 那么video中的innerHTML也就会直接显示在界面上
- 利用这个特点我们可以实现不支持video标签的浏览器提示

```html
<video src="demo.mp4">
  <!-- 如果浏览器不识别video标签，以下内容可以直接显示在浏览器上 -->
  <p>抱歉，您的浏览器不支持视频播放！</p>
</video>
```

#### 格式兼容

- 每个浏览器的音视频格式支持不同（版权问题）
- 需要兼容更多的浏览器，可以通过定义多个`<source>`的方式实现
- html解析过程中会找其中第一个能认识的格式播放，一旦找到认识的视频格式，就不会再往后找了

```html
    <!-- 分析第一个source格式是否支持，如果支持则加载该文件，不支持继续往下解析 -->
    <source src="See You Again.mp3"/>
    <source src="See You Again.wav"/>
    <source src="See You Again.ogg"/>
    <p>抱歉，您的浏览器不支持音频播放！</p>
    
    <!-- 分析第一个source格式是否支持，如果支持则加载该文件，不支持继续往下解析 -->
    <source src="chrome.mp4">
    <source src="chrome.ogv">
    <source src="chrome.webm">
    <p>抱歉，您的浏览器不支持视频播放！</p>
```

- 因此不管是audio还是video都不要直接设置标签的src

#### 多媒体属性

|属性           | 含义                                          |
|---------------|----------------------------------------------|
|controls       | 决定是否显示控制菜单                            |
|autoplay       | 自动播放                                      |
|loop           | 循环播放                                      |
|height/width   | 定义播放器的宽高，只会在视频标签中生效             |
|preload        | 预加载 是否在页面加载完成并且没有开始播放时就开始加载文件，如果有自动播放属性则该属性无意义  |

#### 自定义控制栏

1. 隐藏原生的控制菜单，也就是删除标签中的controls属性
2. 自己设计一套界面控制元素，比如播放按钮，音量控制开关之类
3. 为每个不同的控制元素注册对应的事件
4. 在事件中通过视频元素的API实现自定义播放器的效果
5. 具体的多媒体元素API表：

##### 方法

|方法              |描述                                |
|-----------------|-----------------------------------|
|addTextTrack()   |向音频/视频添加新的文本轨道             |
|canPlayType()    |检测浏览器是否能播放指定的音频/视频类型   |
|load()           |重新加载音频/视频元素                  |
|play()           |开始播放音频/视频                     |
|pause()          |暂停当前播放的音频/视频                |

##### 属性

|属性                 |描述
|---------------------|---------------------------------------
|audioTracks          |返回表示可用音轨的 AudioTrackList 对象                 
|autoplay             |设置或返回是否在加载完成后随即播放音频/视频
|buffered             |返回表示音频/视频已缓冲部分的 TimeRanges 对象 
|controller           |返回表示音频/视频当前媒体控制器的 MediaController 对象
|controls             |设置或返回音频/视频是否显示控件（比如播放/暂停等）
|crossOrigin          |设置或返回音频/视频的 CORS 设置 
|currentSrc           |返回当前音频/视频的 URL
|currentTime          |设置或返回音频/视频中的当前播放位置（以秒计）
|defaultMuted         |设置或返回音频/视频默认是否静音
|defaultPlaybackRate  |设置或返回音频/视频的默认播放速度
|duration             |返回当前音频/视频的长度（以秒计）
|ended                |返回音频/视频的播放是否已结束
|error                |返回表示音频/视频错误状态的 MediaError 对象
|loop                 |设置或返回音频/视频是否应在结束时重新播放
|mediaGroup           |设置或返回音频/视频所属的组合（用于连接多个音频/视频元素）
|muted                |设置或返回音频/视频是否静音
|networkState         |返回音频/视频的当前网络状态
|paused               |设置或返回音频/视频是否暂停
|playbackRate         |设置或返回音频/视频播放的速度
|played               |返回表示音频/视频已播放部分的 TimeRanges 对象
|preload              |设置或返回音频/视频是否应该在页面加载后进行加载
|readyState           |返回音频/视频当前的就绪状态
|seekable             |返回表示音频/视频可寻址部分的 TimeRanges 对象
|seeking              |返回用户是否正在音频/视频中进行查找
|src                  |设置或返回音频/视频元素的当前来源
|startDate            |返回表示当前时间偏移的 Date 对象
|textTracks           |返回表示可用文本轨道的 TextTrackList 对象
|videoTracks          |返回表示可用视频轨道的 VideoTrackList 对象
|volume               |设置或返回音频/视频的音量

##### 事件

|事件             |描述
|-----------------|------------------------------------------
|abort            |当音频/视频的加载已放弃时
|canplay	        |当浏览器可以播放音频/视频时
|canplaythrough	  |当浏览器可在不因缓冲而停顿的情况下进行播放时
|durationchange	  |当音频/视频的时长已更改时
|emptied	        |当目前的播放列表为空时
|ended	          |当目前的播放列表已结束时
|error	          |当在音频/视频加载期间发生错误时
|loadeddata	      |当浏览器已加载音频/视频的当前帧时
|loadedmetadata	  |当浏览器已加载音频/视频的元数据时
|loadstart	      |当浏览器开始查找音频/视频时
|pause	          |当音频/视频已暂停时
|play	            |当音频/视频已开始或不再暂停时
|playing	        |当音频/视频在已因缓冲而暂停或停止后已就绪时
|progress	        |当浏览器正在下载音频/视频时
|ratechange	      |当音频/视频的播放速度已更改时
|seeked	          |当用户已移动/跳跃到音频/视频中的新位置时
|seeking	        |当用户开始移动/跳跃到音频/视频中的新位置时
|stalled	        |当浏览器尝试获取媒体数据，但数据不可用时
|suspend	        |当浏览器刻意不获取媒体数据时
|timeupdate	      |当目前的播放位置已更改时
|volumechange	    |当音量已更改时
|waiting	        |当视频由于需要缓冲下一帧而停止
    
    
### DOM扩展

#### 获取元素

1、document.getElementsByClassName ('class') 通过类名获取元素，以类数组形式存在。

2、document.querySelector('selector') 通过CSS选择器获取元素，符合匹配条件的第1个元素。

3、document.querySelectorAll('selector') 通过CSS选择器获取元素，以类数组形式存在。

#### 类名操作

1、Node.classList.add('class') 添加class

2、Node.classList.remove('class') 移除class

3、Node.classList.toggle('class') 切换class，有则移除，无则添加

4、Node.classList.contains('class') 检测是否存在class

Node指一个有效的DOM节点，是一个通称。

#### 自定义属性

在HTML5中我们可以自定义属性，其格式如下data-*=""，例如

data-info="我是自定义属性"，通过Node.dataset['info'] 我们便可以获取到自定义的属性值。

Node.dataset是以类数组形式存在的

当我们如下格式设置时，则需要以驼峰格式才能正确获取

data-my-name="itcast"，获取Node.dataset['myName']

#### 案例练习

Tab切换

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Tab 标签</title>
    <style>
		body {
			margin: 0;
			padding: 0;
			background-color: #F7F7F7;
		}
	
		.tabs {
			width: 400px;
			margin: 30px auto;
			background-color: #FFF;
			border: 1px solid #C0DCC0;
			box-sizing: border-box;
		}

		.tabs nav {
			height: 40px;
			text-align: center;
			line-height: 40px;
			overflow: hidden;
			background-color: #C0DCC0;
			display: flex;
		}

		nav a {
			display: block;
			width: 100px;
			border-right: 1px solid #FFF;
			color: #000;
			text-decoration: none;
		}

		nav a:last-child {
			border-right: 0 none;
		}

		nav a.active {
			background-color: #9BAF9B;
		}

		.cont {
			overflow: hidden;
			display: none;
		}

		.cont ol {
			line-height: 30px;
		}

    </style>
</head>
<body>
	<div class="tabs">
		<nav>
			<a href="javascript:;" data-cont="local">国内新闻</a>
			<a href="javascript:;" data-cont="global">国际新闻</a>
			<a href="javascript:;" data-cont="sports">体育新闻</a>
			<a href="javascript:;" data-cont="funny">娱乐新闻</a>
		</nav>
		<section class="cont" id="local">
			<ol>
				<li>河感在生矿难，死伤在全10</li>
				<li>禽流感在感在广1处继续蔓延，温家宝指示</li>
				<li>南方大旱，农作物减产绝收面积上亩</li>
				<li>猪流感在广在全国暴发</li>
				<li>禽流感在全国多处继续蔓延，温家宝指示</li>
				<li>南方大旱，农作物减产绝收面积上亩</li>
				<li>猪流感在广东群体性暴发</li>
			</ol>
		</section>
		<section class="cont" id="global">
			<ol>
				<li>河南再次发生矿难，死伤人数超过100</li>
				<li>禽流感次发生蔓延，温家宝指示</li>
				<li>南方大旱，农作物减产绝收面积上亩</li>
				<li>猪流感在广减产绝收发</li>
				<li>禽流感在全国多作物减产绝收面积上亩</li>
				<li>猪流感在广东群体性暴发</li>
			</ol>
		</section>
		<section class="cont" id="sports">
			<ol>
				<li>河南再次发生矿难，死伤人数超过100</li>
				<li>禽流感在全国多处农作物农延，温家宝指示</li>
				<li>南方大旱，农作物减产绝收面积上亩</li>
				<li>猪流感在广东群体性暴发</li>
				<li>禽流感在全农作物继续蔓延，温家宝指示</li>
				<li>南方大农作物减产绝收面积上亩</li>
				<li>猪流感在广东群体性暴发</li>
			</ol>
		</section>
		<section class="cont" id="funny">
			<ol>
				<li>河南再次发生矿难，死伤人数超过101 </li>
				<li>禽流感在全国多处农作物农延，温家宝指示</li>
				<li>南方大旱，农作物减产绝收面积上亩</li>
				<li>猪流感在广东群体性暴发</li>
				<li>禽流感在全农作物继续蔓延，温家宝指示</li>
				<li>南方大农作物减产绝收面积上亩</li>
				<li>猪流感在广东群体性暴发</li>
			</ol>
		</section>
    </div>
    <script>
		/*
		* 1.页面初始化的时候可以指定当前选择的页签
		* 2.点击页签的时候可以做到样式的切换
		* 3.点击的时候可以让对应的内容  做对应的显示
		* */

		/*function tab(index){
			/!*---*!/
		}
		tab(0);*/

		(function(index){

			var tabList = document.querySelectorAll('nav > a');

			var sectionList = document.querySelectorAll('section');

			for(var i = 0 ; i < tabList.length ; i++){

				var tab = tabList[i];

				/*1.页面初始化的时候可以指定当前选择的页签*/
				tab.classList.remove('active');

				if(index == i){
					tab.classList.add('active');
					document.querySelector('#'+tab.dataset['cont']).style.display = "block";
				}

				/*2.点击页签的时候可以做到样式的切换*/
				tab.onclick = function(){

					if(this.classList.contains('active')){
						return false;
					}

					for(var j = 0 ; j < tabList.length ; j++){
						tabList[j].classList.remove('active');
					}

					this.classList.add('active');

					for(var k = 0 ; k < sectionList.length ; k ++){
						sectionList[k].style.display = 'none';
					}

					document.querySelector('#'+this.dataset['cont']).style.display = 'block';
				}
			}

		})(0);

	</script>
</body>
</html>
```


