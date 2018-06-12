## 锚点
*   [开发规范](#开发规范)
*   [开发注意事项](#开发注意事项)
*   [html-head](#html-head)
*   [CSS常用](#CSS常用)
    	[1、单行溢出省略号](#1、单行溢出省略号)
	[2、多行溢出省略号 ](#2、多行溢出省略号)
    	[3、placeholder样式](#3、placeholder样式)
	[4、渐变](#4、渐变)
	[5、flex页脚置底(兼容至ie10)](#5、flex页脚置底(兼容至ie10))
	[6、css三角形](#6、css三角形)
	[7、tab常用响应式不转行，可左右拉动](#7、tab常用响应式不转行，可左右拉动)
	[8、让背景图随DIV变化，且不变形居中](#8、让背景图随DIV变化，且不变形居中)
*   [JS常用](#JS常用)
    	[1、获取URL参数值](#1、获取URL参数值)
	[2、头部提取之后，导航跳转添加对应的active ](#2、头部提取之后，导航跳转添加对应的active)
    	[3、swiper常用参数](#3、swiper常用参数)
	[4、锚链接平滑移动](#4、锚链接平滑移动)


## 开发规范
> 不管有多少人共同参与同一项目，一定要确保每一行代码都像是同一个人编写的。    
[编码规范传送门](http://codeguide.bootcss.com/)

## 开发注意事项

1、插件的版本是否统一；

2、全局样式用谁的；

3、样式表的结构是不是继承的写法，会不会互相干扰；

4、样式优先级如下：    
` 通用选择器 * < 元素(类型)选择器 < 类选择器 < 属性选择器 < 伪类 < ID 选择器 < 内联样式 `

5、团队协作下使用git了吗；

6、不同团队开发，在关于复用的组件以及全局的变量是否有进行沟通；

7、如非特殊情况，慎用!important，因为使用!important会扰乱原本层叠和权重产生正常的作用顺序，使后期维护带来麻烦；

8、链接加title，图标加alt，logo要用h1包裹！

9、一排的展示布局优先使用swiper，否则后面说要加滑动功能就麻烦一些，不如直接用swiper然后不初始化就行了！


## html-head
```
<meta charset="UTF-8">
<!-- Set the width of the document, or not -->
<meta name="viewport" content="width=device-width, user-scalable=no, initial-scale=1.0, maximum-scale=1.0, minimum-scale=1.0">
<!-- First use the latest version of IE and Chrome -->
<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1"/>
<title></title>
<!-- Keyword -->
<meta name="keywords" content="">
<!-- describe -->
<meta name="description" content="">
<!--[if lte IE 8]>
<p style="background:#000;text-align: center;color:#fff;font-size: 16px; line-height: 25px;">你的浏览器太老了，请到<a href="http://browsehappy.com" style="color:#ddd">这里</a>更新，以获取最佳的体验</p>
<![endif]-->
<!--[if lte IE 7]>
<p style="background:#000;text-align: center;color:#fff;font-size: 16px; line-height: 25px;">你的浏览器太老了，请到<a href="http://browsehappy.com" style="color:#ddd">这里</a>更新，以获取最佳的体验</p>
<![endif]-->
<!--[if lte IE 6]>
<p style="background:#000;text-align: center;color:#fff;font-size: 16px; line-height: 25px;">你的浏览器太老了，请到<a href="http://browsehappy.com" style="color:#ddd">这里</a>更新，以获取最佳的体验</p>
<![endif]-->
<!-- 让IE8/9支持媒体查询，从而兼容栅格 -->
<!--[if lt IE 9]>
<script src="https://cdn.staticfile.org/html5shiv/r29/html5.min.js"></script>
<script src="https://cdn.staticfile.org/respond.js/1.4.2/respond.min.js"></script>
<![endif]-->
<!-- 360 use Google Chrome Frame -->
<meta name="renderer" content="webkit">
<!-- Baidu prohibition of transcoding -->
<meta http-equiv="Cache-Control" content="no-siteapp">
<!-- Definition of web search engine index -->
<meta name="robots" content="index,follow">
<!-- ios -->
<!-- The title that is added to the main screen -->
<meta name="apple-mobile-web-app-title" content="titie">
<!-- Whether WebApp full screen mode is enabled -->
<meta content="yes" name="apple-mobile-web-app-capable">
<meta content="yes" name="apple-touch-fullscreen">
<!-- Setting the background color of the State Bar -->
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<!-- Android theme-color  Used to control the color of the tabs -->
<meta name="theme-color" content="#747474">
<meta name="mobile-web-app-capable" content="yes">
<!-- Turn off the translation plug-in under the Chrome browser -->
<meta name="google" value="notranslate"/>
<!-- uc Forced vertical screen -->
<meta name="screen-orientation" content="portrait">
<!-- QQ Forced vertical screen -->
<meta name="x5-orientation" content="portrait">
<!-- UC Mandatory full screen -->
<meta name="full-screen" content="yes">
<!-- QQ Mandatory full screen -->
<meta name="x5-fullscreen" content="true">
<!-- UC Application mode -->
<meta name="browsermode" content="application">
<!-- QQ Application mode -->
<meta name="x5-page-mode" content="app">
```

## CSS常用
### 1、单行溢出省略号
```
overflow: hidden;
text-overflow: ellipsis;
white-space: nowrap;
```

### 2、多行溢出省略号
```
overflow : hidden;
text-overflow: ellipsis;
display: -webkit-box;
-webkit-line-clamp: 2;
-webkit-box-orient: vertical;
```

### 3、placeholder样式
```
input::-webkit-input-placeholder{
  color:red;
}
input::-moz-placeholder{
  color:red;
}
input:-moz-placeholder{
  color:red;
}
input:-ms-input-placeholder{
  color:red;
}
```
 
### 4、渐变
*  从上到下
```
background: -webkit-linear-gradient(red, blue);
background: -o-linear-gradient(red, blue);
background: -moz-linear-gradient(red, blue);
background: linear-gradient(red, blue);
```
 
*  从左到右
```
background: linear-gradient(to right, red , blue);
```
 
*  角度
```
background: linear-gradient(to bottom right, red , blue);  /*左上角至右下角*/
background: linear-gradient(180deg, red, blue);  /*指定角度*/
```
 
*  多个颜色
```
background: linear-gradient(red, green, blue);
```
 
### 5、flex页脚置底(兼容至ie10)
```
<body>
    <header></header>
    <main></main>
    <footer></footer>
</body>

html{height: 100%;}
body{
	height: 100%;
	min-height: 100%;
	display: flex;
	flex-direction: column;
}
.main{
	flex: 1 0 auto;
}
.footer{
	flex: 0 0 auto;
}
```

### 6、css三角形
[传送门](http://www.jb51.net/article/42513.htm)

### 7、tab常用响应式不转行，可左右拉动
放在容器里的样式
```
    white-space: nowrap;
    overflow-x: auto;
    display: flex;
    overflow-y: hidden;
```

### 8、让背景图随DIV变化，且不变形居中
让背景图随DIV变化，且不变形居中。
```
   background-image: url("../images/index/banner.png");
   background-repeat: no-repeat;
   background-size: cover;
   background-attachment: fixed;
   background-position: center center;
```

## JS常用
### 1、获取URL参数值
获取URL的参数的值。
```
function getQueryString(name) {
    var reg = new RegExp("(^|&)" + name + "=([^&]*)(&|$)", "i");
    var r = window.location.search.substr(1).match(reg);
    if (r != null) return unescape(r[2]); return null;
}
```

### 2、头部提取之后，导航跳转添加对应的active
添加到提取的header.html中
```
$(".navbar-nav a").each(function(){
  $this = $(this);
  if($this[0].href==String(window.location)){
    $(".navbar-nav li").removeClass("active");
    $this.parent("li").addClass("active");
  }
});
```

### 3、swiper常用参数
```
var Swiper1 = new Swiper('.swiper-container', {
        autoplay: {		//自动播放
            delay: 1000,	//间隔时间
            disableOnInteraction: false,	//用户操作swiper之后，是否禁止autoplay。
        },
        slidesPerView: 4,	//一屏显示多少个
	slidesPerColumn: 2,	//显示2行
        spaceBetween: 30,	//每个之间的间距
        noSwiping : true,	//使该slide无法拖动，希望文字被选中时可以考虑使用
        noSwipingClass : 'no-swiper',
	centeredSlides : true,	//居中显示
	loop: true,		//头尾循环
	observer: true,		//修改swiper自己或子元素时，自动初始化swiper 
        observeParents: true,	//修改swiper的父元素时，自动初始化swiper 
	pagination: {		//分页器
            el: '.certificate-pagination',
            clickable :true,	//允许点击分页器切换
        },
	navigation: {		//前进后退按钮
	nextEl: '.swiper-button-next',
	prevEl: '.swiper-button-prev',
	},
        breakpoints: {		//响应式设置
          1200: {
            slidesPerView: 4,
            spaceBetween: 35
          },
          992: {
            slidesPerView: 3,
            spaceBetween: 35
          },
          768: {
            slidesPerView: 2,
            spaceBetween: 35
          },
          400: {
            slidesPerView: 1,
            spaceBetween: 35
          }
        }
    })
```

### 4、锚链接平滑移动
```
  $('a[href*=#]').click(function() {  
      if (location.pathname.replace(/^\//, '') == this.pathname.replace(/^\//, '') && location.hostname == this.hostname) {  
          var $target = $(this.hash);  
          $target = $target.length && $target || $('[name=' + this.hash.slice(1) + ']');  
          if ($target.length) {  
              var targetOffset = $target.offset().top;  
              $('html,body').animate({  
                  scrollTop: targetOffset  
              },700);  
              return false;  
          }  
      }  
  });
```
