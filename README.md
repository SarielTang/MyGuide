# MyGuide
some guide put in order for me to read.
一些给我自己看的引导 

## 引文（学习引导）
 "最近还是在深入学习ReactiveCocoa，看ReactiveCocoa的源码。对响应式编程还是有很多期待的，有时间也要重温函数式编程（比如Haskell），或者把响应式编程的公开课（Coursera.org(https://www.coursera.org/course/reactive)）看完。编程范式的选择可以说是相当重要的。未来是多核+并发的时代，函数式编程无疑是更好的选择。
iOS的UI也很重要，但是如果理解apple的CoreAnimation及CoreGraphics框架，大部分UI基本是没问题的。当前，iOS7的各种炫酷效果，也需要对图像的处理有一定理解。说到图形学，OpenCV是一个不错的选择，而OpenGL也是另一个不错的方向（推荐的公开课：Interactive 3D Graphics Course With Three.js & WebGL(https://www.udacity.com/course/cs291)）。"

## 值得关注的项目
### 推荐一：
- ReactiveCocoa(https://github.com/ReactiveCocoa/ReactiveCocoa)
  GitHub自家的函数式响应式编程范式的Objective-C实现，名字听着很高大上，学习曲线确实也比较陡，但是绝对会改变你对iOS编程的认知，首推之。
- Mantle(https://github.com/Mantle/Mantle)
  GitHub自家的产物，轻量级建模的首选，也可以很好的配合CoreData工作。
- AFNetworking(https://github.com/AFNetworking/AFNetworking)
  使用苹果的NSURLRequest及iOS7的NSURLSession，清晰的架构，足够的文档，可以认为是第三方开源库的楷模了。
- pop(https://github.com/facebook/pop)
  facebook出品的paper，动画效果太好了，赶超apple的原生app一大截。pop就是paper的动画库！
- GPUImage(https://github.com/BradLarson/GPUImage)
  OS7出来时，很多好看的效果，其实都是对图像的各种处理（比如模糊效果）。图像处理看来以后也是iOS开发的必备技能之一了。而GPUImage，就是能快速处理各种图像效果的利器！

### 推荐二：
- 首先，学习这类开源项目的主要目的是为了实现产品汪需求，如果不是这个目的，完全可以看Explore GitHub(https://github.com/explore)，当前最火的开源项目都在这里，当然你需要过滤一下语言。
1. 网络
  - AFNetworking
  - JSONKit
  - Reachability
  - SVPullToRefresh

为啥？
  网络请求首选AFNetworking，无数个项目证明，只选对的。
  解析JSON数据推荐JSONKit，而且优势相当的明显，解析速度拉SBJson好几条长安街。
  Reachability也要用起来，时不时检查一下网络状况，然后配合MBProgressHUD告知用户「亲，你丫现在没网啦，别特么戳了。」
  使用SVPullToRefresh处理刷新。

2. 本地存储
  - FMDB
  - Core Data
  - SDWebImage
  - TMCache

为啥？
  第一次开发中引入数据库的时候使用过FMDB，其实蛮强大的，只不过需要写sql语句，select ＊ from user（从user表中筛选出全部数据）。

  后来慢慢的抛弃了它，一点也不面向对象。好吧，其实我是想说还是CoreData好用，至少你不会因为不会写sql而没法保存数据。（接手过的项目竟然还有全部存NSUserDefault的，真是没脾气了）

  看过一篇对比CoreData和FMDB查询大数据性能的文章，FMDB赢了，不过还是推荐用CoreData。

至于SDWebImage，同样也是早期使用过，和SBJson一样，会有crash，尽管用它来缓存图片很方便，但是我们有更好的解决方案，同样不推荐。

  年前的项目中CTO推荐了我们TMCache，tumblr团队使用的一个缓存项目（科普时间：tumblr是国外的轻博客服务，随后国内就出现了点点等同期产品），有时间可以去了解一下，目前应用的不是特别多，当然啦，对我来说。

3. 动画效果
  - MBProgressHUD
  - pop  

为啥？
  上面说到的没网了提示用户的MBProgressHUD，用起来吧，当然还有很多转菊花（loading）的开源项目，同样是我使用最多的。
  pop是facebook paper使用的动画效果，开源了出来，很赞啊，不过应用到项目中的可能性很低。。。太特么炫酷了。

### 推荐三：




