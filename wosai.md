# wosai

> 喔噻云平台

## 1. 开发环境

node v8.9.3

npm v5.6.0

vue-cli v2.9.2

## 2. 初始化项目

	vue init webpack wosai
	
项目结构：

	.
	├── README.md*
	├── build/
	├── config/
	├── dist/
	├── favicon.ico
	├── index.html
	├── node_modules/
	├── package-lock.json
	├── package.json
	├── src/
	└── static/
	
引入jQuery：

方式一：通过npm安装依赖引入

（1）安装

	npm install jquery  --save-dev

（2）修改webpack配置文件（build/webpack.base.conf.js）

	  module: {...},
	  // 引入jquery
	  plugins: [
	    new webpack.ProvidePlugin({
	      $: "jquery",
	      jQuery: "jquery"
	    })
	  ],
	  node: {...}
	  
方式二：手动载入

（1）手动下载jquery 放在static 目录下，如：static/js/jquery.min.js  

（2）定义别名和插件位置（build/webpack.base.conf.js）

	alias: {
	    'vue$': 'vue/dist/vue.common.js',
	    'src': resolve('src'),
	    'assets': resolve('src/assets'),
	    'components': resolve('src/components'),
	    // 定义别名和插件位置
	    "jquery": path.resolve(__dirname, '../static/js/jquery.min.js') 
	}

引入jQuery后，在main.js中引用：

	import $ from 'jquery';
	
引入Bootstrap:

（1）安装
	
	npm install bootstrap --save-dev
	
 (2)在main.js中引用

	import 'bootstrap/dist/css/bootstrap.min.css';
	import 'bootstrap/dist/js/bootstrap.min.js';	


