## 配置scss环境 
  -- 安装 node
  -- 安装淘宝镜像 npm install -g cnpm --registry=https://registry.npm.taobao.org
  -- cd 到项目目录
  -- 初始化项目 npm init  ，都直接按回车
  -- 安装依赖  cnpm install --save-dev node-sass  
  -- 在 package.json中的配置下sass
	```
	{
	  "name": "wifi",
	  "version": "1.0.0",
	  "description": "demo",
	  "main": "index.js",
	  "scripts": {
		"sass": "node-sass"  /*添加这句，复制的时候，需要去掉这句话哈，json注释不带这样的*/
	  },
	  "author": "WiFi_Uncle",
	  "license": "ISC",
	  "devDependencies": {
		"node-sass": "^4.5.3"
	  }
	}
	```
  -- 创建 test.scss
  ```
  body{
  	
  	div{background:lightblue;}
  }
  ```
  -- 执行 npm run sass test.scss test.css 会在当前目录下生成一个解析好的test.css的文件
  
  -- 还可以全局安装 node-sass  
  npm install -g node-sass
  --然后执行 watch命令 监听只要更改就重新生成 .css的文件
  node-sass --watch test.scss  test.css
  node-sass --style compressed test.scss test.css 

## scss 和less的区别
	-- Sass与Scss是什么关系?
	Sass的缩排语法，对于写惯css前端的web开发者来说很不直观，也不能将css代码加入到Sass里面，因此sass语法进行了改良，Sass 3就变成了Scss(sassy css)。与原来的语法兼容，只是用{}取代了原来的缩进。
	Less也是一种动态样式语言. 对CSS赋予了动态语言的特性，如变量，继承，运算， 函数.  Less 既可以在客户端上运行 (支持IE 6+, Webkit, Firefox)，也可在服务端运行 (借助 Node.js)。
	
	-- 二. Sass/Scss与Less区别
	1.编译环境不一样
	Sass的安装需要Ruby环境，是在服务端处理的，而Less是需要引入less.js来处理Less代码输出css到浏览器，也可以在开发环节使用Less，然后编译成css文件，直接放到项目中，也有 Less.app、SimpleLess、CodeKit.app这样的工具，也有在线编译地址。

	2.变量符不一样，Less是@，而Scss是$，而且变量的作用域也不一样。
	3.输出设置，Less没有输出设置，Sass提供4中输出选项：nested, compact, compressed 和 expanded。
	　* nested：嵌套缩进的css代码，它是默认值。

　　* expanded：没有缩进的、扩展的css代码。

　　* compact：简洁格式的css代码。

　　* compressed：压缩后的css代码

	4.Sass支持条件语句，可以使用if{}else{},for{}循环等等。而Less不支持。
	5.引用外部CSS文件
	scss引用的外部文件命名必须以_开头, 如下例所示:其中_test1.scss、_test2.scss、_test3.scss文件分别设置的h1 h2 h3。文件名如果以下划线_开头的话，Sass会认为该文件是一个引用文件，不会将其编译为css文件.
	6.Sass和Less的工具库不同
	Sass有工具库Compass, 简单说，Sass和Compass的关系有点像Javascript和jQuery的关系,Compass是Sass的工具库。在它的基础上，封装了一系列有用的模块和模板，补充强化了Sass的功能。

	Less有UI组件库Bootstrap,Bootstrap是web前端开发中一个比较有名的前端UI组件库，Bootstrap的样式文件部分源码就是采用Less语法编写。
