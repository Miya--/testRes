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
  
10.
