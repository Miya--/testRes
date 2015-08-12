1.Js里的递归思想？
  递归、迭代、斐波那契数列、阶乘、汉诺塔
  递归函数：直接调用或间接调用自身的一种函数，高效操作树形结构。

2.第一个：
  var i,j,k;
   for(i=0,j=0;i<10,j<6;i++,j++) {
    k = i+j;
   }
  console.log(k); // 10
  第二个：
  var i,j,k;
   for(i=0,j=0;j<6,i<10;i++,j++) {
    k = i+j;
   }
  console.log(k); // 18

3.Github上follow了哪些项目？

4.制作一个网页的工作流程

5.渐进增强和优雅降级之间的不同？
  渐进增强 progressive enhancement：针对低版本浏览器进行构建页面，保证最基本的功能，然后再针对高级浏览器进行效果、交互等改进和追加功能达到更好的用户体验。
  优雅降级 graceful degradation：一开始就构建完整的功能，然后再针对低版本浏览器进行兼容。
  区别：优雅降级是从复杂的现状开始，并试图减少用户体验的供给，而渐进增强则是从一个非常基础的，能够起作用的版本开始，并不断扩充，以适应未来环境的需要。降级（功能衰减）意味着往回看；而渐进增强则意味着朝前看，同时保证其根基处于安全地带。
  
6.语义化的HTML如何理解？
  用正确的标签做正确的事情！
  html语义化就是让页面的内容结构化，便于对浏览器、搜索引擎解析；
  在没有样式CCS情况下也以一种文档格式显示，并且是容易阅读的。
  搜索引擎的爬虫依赖于标记来确定上下文和各个关键字的权重，利于 SEO。
  使阅读源代码的人对网站更容易将网站分块，便于阅读维护理解。

7.你如何对网站的文件和资源进行优化？为什么利用多个域名来存储网站资源会更有效？（浏览器一次可以从一个域名下做多少资源？）

8.怎样测试代码的性能？

9.文档类型的作用是什么？你知道多少种文档类型？
  影响浏览器对html代码的编译渲染
  html2.0
  xHtml
  html5
  
10.请描述一下cookies，sessionStorage和localStorage的区别？

11.你使用过那些Javascript库？

12.截取字符串abcdefg的efg
  alert('abcdefg'.substring(4));

13.判断一个字符串中出现次数最多的字符，统计这个次数
  var str = 'asdfssaaasasasasaa';
  var json = {};
  
  for (var i = 0; i < str.length; i++) {
          if(!json[str.charAt(i)]){
                  json[str.charAt(i)] = 1;
          }else{
                  json[str.charAt(i)]++;
          }
  };
  var iMax = 0;
  var iIndex = '';
  for(var i in json){
          if(json[i]>iMax){
                  iMax = json[i];
                  iIndex = i;
          }
  }
  alert('出现次数最多的是:'+iIndex+'出现'+iMax+'次');

14.IE与FF脚本兼容性问题
  obj.addEventListener(sEv, fn, false);
  obj.attachEvent('on'+sEv,fn);
  detachevet
  removeEventListener
  DOMContentLoaded
  onreadystatechange  complete
  DOMMouseScroll FF
  onmousewheel   非FF
  event.wheelDelta 上滚120 下-120
  event.detail     上滚-3   下3  
  obj.getCurrentStyle[attr]
  getComputedStyle(obj,false)[attr]
  XMLHttpRequest
  ActiveXObject('Mircorsoft.XMLHttp')
  FF本地能设置读取cookie 其他不行
  event  ev
  事件源
  srcElement||target
  toElement||relatedTarget
  obj.setCapture();只有ie认
  obj.releaseCapture();

15.规避javascript多人开发函数重名问题
  命名空间
  封闭空间
  js模块化mvc（数据层、表现层、控制层）
  seajs
  变量转换成对象的属性
  对象化

16.javascript面向对象中继承实现
  function Person(name){
        this.name = name;
  }
  Person.prototype.showName = function(){
          alert(this.name);
  }
  function Worker(name, job){
          Person.apply(this,arguments)
          this.job = job;
  }
  for(var i in Person.prototype){
          Worker.prototype = Person.prototype;
  }
  new Worker('sl', 'coders').showName();

17.FF下面实现outerHTML
  var oDiv = document.createElement('div');
  var oDiv1 = document.getElementById('div1');
  var oWarp = document.getElementById('warp');
  
  oWarp.insertBefore(oDiv, oDiv1);
  oDiv.appendChild(oDiv1);
  var sOut = oDiv.innerHTML;
  oWarp.insertBefore(oDiv1, oDiv);
  oWarp.removeChild(oDiv);
  alert(sOut);

18.编写一个方法 求一个字符串的字节长度，假设一个中文占两个字节
  var str = '22两是';
  alert(getStrlen(str))
  function getStrlen(str){
          var json = {len:0};
          var re = /[\u4e00-\u9fa5]/;
          for (var i = 0; i < str.length; i++) {
                  if(re.test(str.charAt(i))){
                          json['len']++;
                  }
          };
          return json['len']+str.length;
  }

19.编写一个方法 去掉一个数组的重复元素
  var arr = [1,2,3,1,43,12,12,1];
  var json = {};
  var arr2 = [];
  for (var i = 0; i < arr.length; i++) {
          if(!json[arr[i]]){
                  json[arr[i]] = true;
          }else{
                  json[arr[i]] = false;
          }
  
          if(json[arr[i]]){
                  arr2.push(arr[i]);
          }
  };
  for (var i = 0; i < arr.length; i++) {
          if(!aa(arr[i], arr2)){
                  arr2.push(arr[i])
          }
  };
  function aa(obj, arr){
          for (var i = 0; i < arr.length; i++) {
                  if(arr[i] == obj) return true;
                  else return false;
          };
  }
  alert(arr2)

20.写出3个使用this的典型应用，谈谈This对象的理解。
  事件： 如onclick  this->发生事件的对象
  构造函数          this->new 出来的object
  call/apply        改变this
  
  this是js的一个关键字，随着函数使用场合不同，this的值会发生变化。
  但是有一个总原则，那就是this指的是调用函数的那个对象。
  this一般情况下：是全局对象Global。 作为方法调用，那么this就是指这个对象 

21.如何深度克隆
  var arr = [1,2,43];
  var json = {a:6,b:4,c:[1,2,3]};
  var str = 'sdfsdf';
  
  var json2 = clone(json);
  
  alert(json['c'])
  function clone(obj){
          var oNew = new obj.constructor(obj.valueOf());
          if(obj.constructor == Object){
                  for(var i in obj){
                          oNew[i] = obj[i];
                          if(typeof(oNew[i]) == 'object'){
                                  clone(oNew[i]);
                          }
                  }
          }
          return oNew;
  }

22.JavaScript中如何检测一个变量是一个String类型？请写出函数实现
  typeof(obj) == 'string'
  obj.constructor == String;

23.网页中实现一个计算当年还剩多少时间的倒数计时程序，要求网页上实时动态显示“××年还剩××天××时××分××秒”
  var oDate = new Date();
  var oYear = oDate.getFullYear();
  
  var oNewDate = new Date();
  oNewDate.setFullYear(oYear, 11, 31, 23, 59, 59);
  var iTime = oNewDate.getTime()-oDate.getTime();
  
  var iS = iTime/1000;
  var iM = oNewDate.getMonth()-oDate.getMonth();
  var iDate =iS

24.请说出三种减低页面加载时间的方法
  1、压缩css、js文件
  2、合并js、css文件，减少http请求
  3、外部js、css文件放在最底下
  4、减少dom操作，尽可能用变量替代不必要的dom操作

25.什么是FOUC？你如何来避免FOUC？
  由于css引入使用了@import 或者存在多个style标签以及css文件在页面底部引入使得css文件加载在html之后导致页面闪烁、花屏
  用link加载css文件，放在head标签里面

26.浏览器标准模式和怪异模式之间的区别是什么？
  盒模型解释不同

27.哈希表
  具有散列（映射）特性的数据模型
  
28.什么是闭包（closure），为什么要用它？
  子函数能被外部调用到，则该作用连上的所有变量都会被保存下来。
  执行say667()后,say667()闭包内部变量会存在,而闭包内部函数的内部变量不会存在.使得Javascript的垃圾回收机制GC不会收回say667()所占用的资源，因为say667()的内部函数的执行需要依赖say667()中的变量。这是对闭包作用的非常直白的描述.
    function say667() {
      // Local variable that ends up within closure
      var num = 666;
      var sayAlert = function() { alert(num); }
      num++;
      return sayAlert;
  }
   var sayAlert = say667();
   sayAlert()//执行结果应该弹出的667 
   
29.你如何组织自己的代码？是使用模块模式，还是使用经典继承的方法？
  对内：模块模式
  对外：继承
  
30.你如何优化自己的代码？
  代码重用
  避免全局变量（命名空间，封闭空间，模块化mvc..）
  拆分函数避免函数过于臃肿
  注释
  
31.你能解释一下JavaScript中的继承是如何工作的吗？
  子构造函数中执行父构造函数，并用call\apply改变this
  克隆父构造函数原型上的方法

32.请尽可能详尽的解释AJAX的工作原理。AJAX的交互模型(流程)? AJAX跨域的解决办法?
  创建ajax对象（XMLHttpRequest/ActiveXObject(Microsoft.XMLHttp)）
  判断数据传输方式(GET/POST)
  打开链接 open()
  发送 send()
  当ajax对象完成第四步（onreadystatechange）数据接收完成，判断http响应状态（status）200-300之间或者304（缓存）执行回调函数
  
33.对Web标准的理解

34.浏览器的内核分别是什么?
  IE浏览器的内核Trident、
  Mozilla的Gecko、
  Chrome的Blink（WebKit的分支）、
  Opera内核原为Presto，现为Blink；
  
35.选择器优先级 

36.DOM结构 —— 两个节点之间可能存在哪些关系以及如何在节点之间任意移动。

37.DOM操作  ——如何添加、移除、移动、复制、创建和查找节点等。

38.事件 —— 如何使用事件，以及IE和标准DOM事件模型之间存在的差别。

39.XMLHttpRequest —— 这是什么、怎样完整地执行一次GET请求、怎样检测错误。

40.Doctype? 严格模式与混杂模式-如何触发这两种模式，区分它们有何意义?
  Doctype声明位于文档中的最前面的位置，处于标签之前。此标签可告知浏览器文档使用哪种 HTML 或 XHTML 规范。该标签可声明三种DTD 类型，格版本、过渡版本以及基于框架的HTML文档。当浏览器厂商开始创建与标准兼容的浏览器时，他们希望确保向后兼容性。为了实现这一点，他们创建了两种呈现模式：标准模式和混杂模式（quirksm标准模式中，浏览器根据规范呈现页面；在混杂模式中，页面以一种比较宽松的向后兼容的方式显示。混杂模式通常模拟老式浏览器（比如Microsoft IE 4和 Navigator 4）的行为以防止老站点无法工作。
  浏览器根据DOCTYPE是否存在以及使用的哪种DTD来选择要使用的呈现方法。如果XHTML文档包含形式完整的DOCTYPE，那么它一般以标准模式于HTML 4.01文档，包含严格DTD的DOCTYPE常常导致页面以标准模式呈现。包含过渡DTD和URI的DOCTYPE也导致页面以标准模式呈现，但DTD而没有URI会导致页面以混杂模式呈现。DOCTYPE不存在或形式不正确会导致HTML和XHTML文档以混杂模式呈现。
  
41.盒模型 —— 外边距、内边距和边框之间的关系，及IE8以下版本的浏览器中的盒模型

42.块级元素与行内元素 —— 怎么用CSS控制它们、以及如何合理的使用它们

43.浮动元素——怎么使用它们、它们有什么问题以及怎么解决这些问题。

44.HTML与XHTML——二者有什么区别，你觉得应该使用哪一个并说出理由。

45.JSON  —— 作用、用途、设计结构。
  JSON(JavaScript Object Notation) 是一种轻量级的数据交换格式。
  它是基于JavaScript的一个子集。数据格式简单, 易于读写, 占用带宽小
  {'age':'12', 'name':'back'}
  
46.Doctype作用? 严格模式与混杂模式如何区分？它们有何意义?
  1.<!DOCTYPE> 声明位于文档中的最前面，处于 <html> 标签之前。告知浏览器的解析器，用什么文档类型 规范来解析这个文档。 
  2.严格模式的排版和 JS 运作模式是  以该浏览器支持的最高标准运行。
  3.在混杂模式中，页面以宽松的向后兼容的方式显示。模拟老式浏览器的行为以防止站点无法工作。
  4.DOCTYPE不存在或格式不正确会导致文档以混杂模式呈现。
  
47.行内元素有哪些？块级元素有哪些？ 空(void)元素有那些？
  1.CSS规范规定，每个元素都有display属性，确定该元素的类型，每个元素都有默认的display值，比如div默认display属性值为“block”，成为“块级”元素；span默认display属性值为“inline”，是“行内”元素。
  2. 行内元素有：a b span img input select strong（强调的语气）
     块级元素有：div ul ol li dl dt dd h1 h2 h3 h4…p
  3.知名的空元素 : <br> <hr> <img> <input> <link> <meta> 
    鲜为人知的是 : <area> <base> <col> <command> <embed> <keygen> <param> <source> <track> <wbr>

48.link 和@import 的区别是？
  1.link属于XHTML标签，而@import是CSS提供的;
  2.页面被加载的时，link会同时被加载，而@import引用的CSS会等到页面被加载完再加载;
  3.import只在IE5以上才能识别，而link是XHTML标签，无兼容问题;
  4.link方式的样式的权重 高于@import的权重.

49.png24位的图片在iE6浏览器上出现背景
  做成PNG8
  
50.浏览器默认的margin和padding不同
  加一个全局的*{margin:0;padding:0;}来统一
  
51.IE6双边距bug:块属性标签float后，又有横行的margin情况下，在ie6显示margin比设置的大。浮动ie产生的双倍距离 #box{ float:left; width:10px; margin:0 0 0 10px;}这种情况之下IE会产生20px的距离
  在float的标签样式控制中加入 ——_display:inline;将其转化为行内属性。(_这个符号只有ie6会识别)
  渐进识别的方式，从总体中逐渐排除局部。首先，巧妙的使用“\9”这一标记，将IE游览器从所有情况中分离出来。接着，再次使用“+”将IE8和IE7、IE6分离开来，这样IE8已经独立识别。
  .bb{
      background-color:#f1ee18;/*所有识别*/
      .background-color:#00deff\9; /*IE6、7、8识别*/
      +background-color:#a200ff;/*IE6、7识别*/
      _background-color:#1e0bd1;/*IE6识别*/ 
  } 
  
52.获取自定义属性的兼容性问题
  IE下,可以使用获取常规属性的方法来获取自定义属性,也可以使用getAttribute()获取自定义属性;
  Firefox下,只能使用getAttribute()获取自定义属性. 
  解决方法:统一通过getAttribute()获取自定义属性

53.Chrome 中文界面下默认会将小于 12px 的文本强制按照 12px 显示
  可通过加入 CSS 属性 -webkit-text-size-adjust: none; 解决

54.超链接访问过后hover样式就不出现了 被点击访问过的超链接样式不在具有hover和active了
  改变CSS属性的排列顺序:
  L-V-H-A :  a:link {} a:visited {} a:hover {} a:active {}
  
55.html5有哪些新特性？
  HTML5 现在已经不是 SGML 的子集，主要是关于图像，位置，存储，多任务等功能的增加。
  绘画 canvas  ：用于媒介回放的 video 和 audio 元素 
  本地离线存储 localStorage 长期存储数据，浏览器关闭后数据不丢失；sessionStorage 的数据在浏览器关闭后自动删除
  语意化更好的内容元素，比如 article、footer、header、nav、section 
  表单控件，calendar、date、time、email、url、search  
  新的技术webworker, websockt, Geolocation
  
56.html5移除了那些元素?
  纯表现的元素：basefont，big，center，font, s，strike，tt，u；
  对可用性产生负面影响的元素：frame，frameset，noframes；

57.如何处理HTML5新标签的浏览器兼容问题？
  IE8/IE7/IE6支持通过document.createElement方法产生的标签，可以利用这一特性让这些浏览器支持HTML5新标签，
  浏览器支持新标签后，还需要添加标签默认的样式：
  当然最好的方式是直接使用成熟的框架、使用最多的是html5shim框架
   <!--[if lt IE 9]> 
   <script> src="http://html5shim.googlecode.com/svn/trunk/html5.js"</script> 
   <![endif]--> 
   
58.如何区分 HTML 和 HTML5？
  DOCTYPE声明\新增的结构元素\功能元素
  
59.HTML5的离线储存？
  localStorage    长期存储数据，浏览器关闭后数据不丢失；
  sessionStorage  数据在浏览器关闭后自动删除。
  
60.(写)描述一段语义的html代码吧。
  （HTML5中新增加的很多标签（如：<article>、<nav>、<header>和<footer>等）就是基于语义化设计原则）  
    <div id="header"> 
      <h1>标题</h1> 
      <h2>专注Web前端技术</h2> 
    </div>

61. 












