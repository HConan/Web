作者：HConan
日期：2019-04-01

相关说明：ConanHtmlDemo.html涵盖示例

目录：
* [1. 认识网页](#认识网页)
* [2. 标签](#标签)
	* [2.1 单标签](#单标签)
	* [2.2 双标签](#双标签)
	* [2.3 标签关系及特殊字符](#标签关系及特殊字符)
* [3. html4、xhtml结构](#html4、xhtml结构)
* [4. 列表](#列表)
* [5. 标签详解](#标签详解)
	* [5.1 多媒体标签](#多媒体标签)
	* [5.2 meta标签](#meta标签)
	* [5.3 link标签](#link标签)
* [6. 表格](#表格)
* [7. 表单](#表单)
	* [7.1 表单域](#表单域)
	* [7.2 input类型](#input类型)
	* [7.3 非input类型](#非input类型)
	* [7.4 智能表单](#智能表单)
	* [7.5 新增表单元素](#新增表单元素)
	* [7.6 相关属性](#相关属性)

<span id="HTML"></span>
# HTML

<span id="认识网页"></span>
## 1. 认识网页
组成：
	文字、图片、输入框等

标准：
	1. 结构标准（html）
	2. 表现标准（css）
	3. 行为标准（js）

<span id="标签"></span>
## 2. 标签

<span id="单标签"></span>
### 2.1 单标签
1. `<hr>`	水平线
2. `<br>`	换行
3. `<meta>`	网页编码（具体在下面介绍）
4. `<base>`	网页跳转

	`<base>`标签属性：
		target:
			'_self' 在当前窗口中打开新页面
			'_blank' 在新窗口中打开页面
5. `<img>`	图片标签

	`<img>`标签属性：
		src：
			相对路径：
				同一个文件夹中
				页面在上一级目录中（用`./`来表示当前目录或下一级目录）
				页面在下一级目录中（用`../`来表示上一级目录）
			绝对路径：
				带有磁盘目录或者网站地址
		title:
			鼠标悬停显示内容
		alt:
			设置图片的描述信息
			该属性是为搜索引擎提供服务的
		width/height:
			一般width/height只设置一个即可，会自动缩放
		

<span id="双标签"></span>
### 2.2 双标签
#### 语义标签
1. `<p>`	段落
2. `<h1> ... <h6>`	标题
	
	注意：
		一个网页中最好只出现一次1号标题
3. `<a href="">`	超链接
	
	1. 跳转到其他页面：
		通过href属性设置相对或绝对路径
		跳转方式：
			target:
				'_self' 在当前窗口中打开新页面
				'_blank' 在新窗口中打开页面
			优化写法（整个网页里面都会在新窗口中打开）：
				在head标签中设置base标签的值为"_blank"
			title属性:
				鼠标悬停显示内容
	2. 跳转到本页面：
			直接设置 href="#"
			使用锚链接：
				必须用id属性
				<a href="#id属性值"></a>

4. 常用文本处理标签

|标签	|含义	|不推荐使用	|
|--		|--		|--			|
|em		|斜体	|i			|
|stong	|加粗	|b			|
|ins	|下划线	|u			|
|del	|删除线	|s			|

5. 新语义标签
		1. head:网页布局中的头部
		2. footer:网页布局中的底部
		3. nav:网页布局中的导航
		4. article:网页布局中的正文
		5. aside:网页布局中的侧边栏
		6. section:网页布局中的区域
	
	备注：
		1. 与div标签用法一样
		2. 该标签有语义，div标签无语义

#### 无语义标签
	常用：
		div:块元素（能用p标签的时候不使用div）
		span:行元素
	不推荐使用：
		i:斜体（推荐使用em标签）
		b:加粗（推荐使用strong标签）
		u:下划线（推荐使用ins标签）
		s:删除线（推荐使用del标签）

<span id="标签关系及特殊字符"></span>
### 2.3 标签关系及特殊字符
**标签关系**

	并列关系
	嵌套关系

**特殊字符**

	&nbsp; 空格
	&alt; 小于号
	&gt; 大于号

<span id="html4、xhtml结构"></span>
## 3. html4、xhtml结构
**html4结构**

	严格模式：strict.dtd
	过渡模式：loose.dtd
	
**xhtml结构**

	严格模式
	过渡模式
	
<span id="列表"></span>
## 4. 列表
**无序列表**
```html
<body>
	<ul>
		<!-- 列表项 -->
		<li>无</li>
		<li>序</li>
	</ul>
</body>
```
**有效列表**
```html
<body>
	<ol>
		<!-- 列表项 -->
		<li>有</li>
		<li>序</li>
	</ol>
</body>
```
**自定义列表**
```html
<body>
	<dl>
		<!-- 列表项标题 -->
		<dt>分行（顶格显示）</dt>
		<!-- 列表项 -->
		<dd>自</dd>
		<dd>定</dd>
		<dd>义</dd>
	</dl>
</body>
```

<span id="标签详解"></span>
## 5. 标签详解

<span id="多媒体标签"></span>
### 5.1 多媒体标签
video/audio:

	controls:显示控制栏
	autoplay:自动播放
	loop:设置视频循环播放

支持多种格式：
```html
<body>
	<video>
		<source src="格式1地址">
		<source src="格式2地址">
	</video>
<body>
```

<span id="meta标签"></span>
### 5.2 meta标签
1. 设置网页编码：
	`<meta charset="utf-8">`
	
	备注：charset:字符集，一般使用utf-8
	
2. 设置网页关键字：
	`<meta name="keywords" content="">`
	
	备注：为搜索引擎服务
	
3. 设置网页描述信息：
	`<meta name="description" content="">`
	
	备注：为搜索引擎提供服务，比如百度上展示的网页相关性描述，就是通过description来表示的
	
4. 设置网页重定向：
	`<meta http-equiv="refresh" content="3; http://www.t2.com">`
	
	备注：比如起初的网址是`www.t.com`现在为`www.t2.com`，那么当人们进入`www.t.com`的时候会自动引导跳转到`www.t2.com`

<span id="link标签"></span>
### 5.3 link标签
**设置网页图标**
	
	一般将网页图标放置到网站的根目录下，一般使用ico格式的
```html
<head>
	<!-- 设置网页图标 -->
	<link rel="icon" href="./title.ico">
</head>
```

**引用外部样式表**
```html
<head>
	<!-- 引用样式表，href放样式表的地址 -->
	<link rel="stylesheet" href="">
</head>
```

<span id="表格"></span>
## 6. 表格
**基本格式：**

备注：
	1. 一般thead/tbody/tfoot不用写，低版本浏览器无法识别
	2. th设置表格的标题（会有加粗、居中效果）
```html
<body>
	<table border="1" cellpadding="10" cellspacing="0" align="center" bgcolor="chocolate">
		<caption>人员信息表</caption>
		<!-- 一般thead/tbody/tfoot不用写，低版本浏览器无法识别 -->
		</thead>
			<tr bgcolor="green">
				<!-- th设置表格的标题（会有加粗、居中效果） -->
				<th>姓名</th>
				<th>年龄</th>
				<th>职业</th>
				<th>籍贯</th>
				<th>性别</th>
			</tr>
		<thead>
		<tbody>
			<tr align="center">
				<td>小段</td>
				<td>20</td>
				<td>学生</td>
				<td>张家口</td>
				<td>男</td>
			</tr>
		</tbody>
		<tfoot>
			<tr align="center">
				<td>小红</td>
				<td>25</td>
				<td>攻城狮</td>
				<td>北京</td>
				<td>女</td>
			</tr>
		</tfoot>
	</table>
</body>
```

**基本结构：**

	1. head:头
	2. tbody:
		tr:行
		td:列
		th:标题栏的列
	3. tfoot:尾
	4. caption:表头
	
**属性：**

	1. border:边框（默认值为0）
	2. cellspacing:单元格之间的距离（默认值为2）
	3. cellpadding:内容与边框之间的距离（此时就相当于自动调整边距，不与width、height同时使用）
	4. align:设置table标签时，只能改变table标签的对齐方式，不能改变其内容的对齐方式
		left
		center
		right
	5. width/height:（想要表格随网页的大小动态调整，则width设置为100%、90%等类）
		
**合并单元格：**
	
	横向合并：colspan
	纵向合并：rowspan
	
**emmet快捷输入：**

emmet语法快捷输入表格样式，输入下面代码后按Tab键即可快捷生成

table中属性用[]表示，>表示包含的关系，table中包含tr，tr中包含td

`table[border=1 width=600 height=400]>tr*3>td*5`

<span id="表单"></span>
## 7. 表单

**作用：**

通过表单控件搜集数据

**组成：**
	1. 表单域：form
	2. 提示信息
	3. 表单控件
		input类型
		非input类型

<span id="单表域"></span>
### 7.1 单表域

说明：

	action：设置一个用来接收数据的一个后台程序
	method：有get与post两种；设置如何将数据交给后台程序的一种方式
	get能看到传给1.php之后的username与pwd
	post后面看不到传给1.php的username与pwd
```html
<body>
	<form action="1.php" method="get" id="testForm">
	
	</form>
</body>
```

<span id="input类型"></span>
### 7.2 input类型
1. `<input type="text">` 文本输入（邮箱等）
2. `<input type="password">` 密码输入
3. `<input type="checkbox">` 复选框输入
4. `<input type="radio">` 单选框输入
5. `<input type="button">` 按钮
6. `<input type="submit">` 提交
7. `<input type="reset">` 重置
8. `<input type="image">` 图片
9. `<input type="file">` 上传文件

```html
<body>
	<!-- 只能提交表单里面的，如果页面需求，不同的表单里面的东西提交使用form属性，链接ID即可 -->
	<input type="text" form="testForm">
	
	<form action="1.php" method="get" id="testForm">
		邮箱地址：
		<input type="text" maxlength="16" name="" placeholder="请输入邮箱地址">
		<br>
		密码：
		<input type="password" name="pwd">
		<br>
		爱好：
		<!-- 复选框：checkbox -->
		<input type="checkbox" name="" checked>看书
		<input type="checkbox" name="">写字
		<input type="checkbox" name="" checked>写代码
		<br>
		性别：
		<!-- 单选框：radio -->
		<!-- 如果要实现单选效果，那么需要将该控件设置相同的name属性值 -->
		<input type="radio" name="sex" checked>男
		<input type="radio" name="sex" >女
		<br>
		<!-- 该按钮不能直接在表单域中提交数据 -->
		<!-- 该按钮一般配合JS使用 -->
		<input type="button" value="注册">
		<br>
		<!-- 提交按钮 -->
		<input type="submit">
		<br>
		<!-- 将控件中的值恢复到默认值 -->
		<input type="reset">
		<br>
		<!-- 提交按钮 -->
		<input type="image" src="logo.jpg" width="200">
		<br>
		上传文件：
		<input type="file">
	</form>
</body>
```

<span id="非input类型"></span>
### 7.3 非input类型
	1. select:下拉菜单
	2. textarea:多行文本域
	3. fieldset:将表单内的相关元素分组
```html
<body>	
	<form action="1.php" method="get">
		<!-- select中有multiple属性（多选） -->
		<select>
			<option selected>安徽</option>
			<option>浙江</option>
			<option>江苏</option>
		</select>
		<select>
			<optgroup label="安徽省">
				<option>合肥</option>
				<option selected>安庆</option>
				<option>马鞍山</option>
			</optgroup>
		</select>
		<br>
		<!-- 按ctrl可以多选 -->
		<select multiple="multiple">
			<option>IT行业</option>
			<option>计算机行业</option>
			<option>市场推广</option>
		</select>
	</form>
	
	<!-- 多行文本域 -->
	<textarea rows="10" cols="50">
		测试内容
	</textarea>
	
	<form action="1.php" method="post">
		<fieldset>
			<legend>注册信息</legend>
		</fieldset>
	</form>
</body>
```


<span id="智能表单"></span>
### 7.4 智能表单
```html
<body>
	<form action="1.php" method="post">
		<fieldset>
			<legend>注册信息</legend>
			
			<!-- 智能表单 -->
			邮箱地址：
			<input type="email" name="em" placeholder="输入邮箱地址">
			<font size="3" color="pink">此控件对格式有限制(智能表单)，验证邮箱的控件</font>
			<br><br>
			电话号码：
			<input type="tel">
			<font size="3" color="pink">移动手机端可以直接弹出数字键盘</font>
			<br><br>
			数字：
			<input type="number" step="5">
			<font size="3" color="pink">每一次加五个数，能输入字母e(科学计数)</font>
			<br><br>
			拾色器：
			<input type="color" value="#0000f0">
			<font size="3" color="pink">拾色器的默认颜色要通过<em> #xxxxxx </em>这种格式来改变</font>
			<br><br>
			网址：
			<input type="url">
			<br><br>
			滑块：
			<input type="range">
			<br><br>
			时间：
			<input type="time">
			<br><br>
			日期：
			<input type="date">
			<br><br>
			周：
			<input type="week">
			<br><br>
			月：
			<input type="month">
			
		</fieldset>
	</form>
</body>
```


<span id="新增表单元素"></span>
### 7.5 新增表单元素

```html
<body>
	<input type="text" list="date">
	<datalist id="date">
		<option value ="qd">前端培训</option>
		<option value ="qz">全栈培训</option>
		<option value ="ja">JAVA培训</option>
	</datalist>
	<br><br>
	<input type="text" list="date2">
	<datalist id="date2">
		<option>前端培训</option>
		<option>全栈培训</option>
		<option>JAVA培训</option>
	</datalist>
</body>
```

<span id="相关属性"></span>
### 7.6 相关属性
	
	maxlength：设置控件中最多能输入多少个字符
	readonly：设置控件为只读模式（不能输入）
	disabled：设置控件为未激活（不能输入）
	name：为控件设置名称
	id：设置控件唯一标识（身份证号）
	value：设置控件默认值
		value是为了区分不同标签的类型
		name是为了区分相同类型里不同的值而确定的，是让后台识别的
		value和name都是让后台识别的，name的范围比value的范围要广
		name是控件的名称 ，value是控件的值， id是控件的身份标志。
	placeholder：设置控件的提示信息
	autofocus：设置控件自动获取焦点
	required：设置控件为必须填写
	placeholder：占位符（提示信息）
	autocomplete:自动完成（默认为on，可以改为off)
	novalidate:关闭验证，比如智能填email时需要满足格式，关闭后可跳过
	
