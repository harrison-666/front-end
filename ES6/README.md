﻿    1.ES6参考网站:
        http://es6.ruanyifeng.com/#README
        ES6是js的超集,Java化了,引进了类class的概念

    2.ES6不能直接运行,需要转换成ES5来运行.
        需要用babel库来转换.

    3.环境构建及运行程序
    (1)新建一个babel的配置文件.babelrc,必须存在根目录下
    先建一个记事本文档，再重命名：
        DOS重命名方法：rename 1.txt .babelrc
        Linux重命名方法：mv 1.txt .babelrc

        dos清屏：cls
        linux清屏：clear

    (2)创建package.json
        npm init
    (3)安装转码规则:
        npm install --save-dev babel-preset-latest
        npm install --save-dev babel-preset-react
        npm install --save-dev babel-preset-stage-2
	(4)添加.babelrc文件内容
          {
            "presets": [
              "latest",
              "react",
              "stage-2"
            ],
            "plugins": []
          }
	  (5)安装babel-cli工具
	       npm install --global babel-cli
	  (6)安装完成,转换单个ES6文件
	  	   babel 源文件 -o 转换后的js文件
	  (7)整个目录转码
	        babel 源目录 -d 目标目录
	  (8)babel-register模块改写require命令，为它加上一个钩子。此后，每当使用require加载.js、.jsx、.es和.es6后缀名的文件，就会先用Babel进行转码。
         npm install --save-dev babel-register
         使用时，必须首先加载babel-register。
         require("babel-register");
         require("./index.js");
         然后，就不需要手动对index.js转码了。
         需要注意的是，babel-register只会对require命令加载的文件转码，而不会对当前文件转码。另外，由于它是实时转码，所以只适合在开发环境使用。


	  4.let
	  闭包的作用:防止变量被污染和值被释放。
	  let保护了变量，let定义的变量的位置不能被提升，一般要求变量在使用之前必须先定义。

	  5.rest参数必须放在最后

	  6.箭头函数
	  var x = item=>item + 1
      var x = 参数 => 函数体
      var x = function(item){
      	return item + 1;
      }

      var x=()=>{return x + 5;}


	  7.继承
		ES5中继承是原型链的继承，隐式原型
		对象._proto_===类型.prototype
		function Person(){

		}
		var p = new Person();
		p._proto_===Person.prototype//继承的关系

		子.prototype = new 父();
