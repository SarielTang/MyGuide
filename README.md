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

一. XMPPFramework: (https://github.com/robbiehanson/XMPPFramework) ，这个如果是做过聊天的通信通信可能会用过，本人因为工作原因，两年前第一次接触这个代码，就对这个大牛非常崇拜。代码值得学习的东西非常多。作者在开发这个框架的时候，同时也开发了非常多的基础库，都非常值得学习。

1. 首先是插件是框架设计，设计的非常优雅，功能强大易扩展，而且写的很简洁，易懂。

2. 作者基于GCD设计的一对多的delegate机制--GCDMulticastDelegate，后来在项目中我尝试使用过这个框架，多个模块依赖于某一个核心组件，使用这个类，可以把耦合问题降到很低，值得推荐。

3. CocoaAsyncSocket， (https://github.com/robbiehanson/CocoaAsyncSocket) ，这个是让本人又无比崇拜的一个类库，作者根据iOS平台的特性，实现了两套异步socket网络库，一个基于GCD与POSIX Socket开发的socket异步网络库，另外一个是使用CFSocket与runloop实现，我曾经尝试去阅读这个类库，不过后来发现自己能力实现有限，只能看个大概的轮廓。

4. CocoaLumberjack， (https://github.com/robbiehanson/CocoaLumberjack) ，这个是作者写的一个log系统，实现了分级别的日志系统，不过本人没有使用和学习这个，我们项目没有那么复杂，我是自己使用宏和NSLog写了一个分级别显示的日志系统，只能用于打印，不能像这个日志可以写入文件。

5. KissXML  (https://github.com/robbiehanson/KissXML) ，我们平时一般使用json格式的数据，除了组装xmpp聊天消息，对这个没有怎么使用过，不敢评论。

二. AFNetworking： (https://github.com/AFNetworking/AFNetworking) ，毫无疑问，最火的网络库，本人11年开始做iOS开发的时候，是使用ASI的，一直没有使用过AFNetworking，直到12年的时候，发现ASI作者基本不更新ASI之后，才开始关注这个项目。ASI是基于CFSocket实现的HTTP网络库，作者功底之强，跟上面的老大一样让人拜服，而AFNetworking是基于NSURLConnection，以及iOS7之后出现的NSURLSession为基础开发的。由于AFNetworking基于Apple的封装，少了很多需要自己维护的地方，而且整个项目也会非常整洁，可能效率上也会高于ASI的封装。建议可以把整个项目过一遍，框架设计思想不用说了，里面也可以学习到非常多的技术点。

1. NSOperation的封装与使用，面试的时候很多人只知道apple有NSOperation这个技术，但是实际上使用的机会并不多，只知道是个队列，但是对于如何使用并不知晓。可惜的是，这个只提供了如何使用进非并发Operation的封装。完整学习的话，可以学习ASI中对operation的使用，会更完整一些。

2. HTTP请求的封装，如何封装POST请求，如何进行URL encode，如何使用NSInputstream，可以对HTTP理解有个突破。同时可以学习一下NSURLSession与NSURLConnection的使用。

3. Runloop的使用，建议与ASI实现同步请求的方法进行对比，有条件的话可以跟android的looper机制进行对比，说不定什么时候会使用到，实际xmppframework中也有用到，只是不是核心机制，而且本人没有研究过。本人从11年做iOS到现在，只是使用到过一次，是需要自己实现一个OpenGL的渲染队列，由于需要在子线程中做渲染，无法使用CADisplaylink。刚开始其实是使用GCD的，但发现即使我创建一个dispatch_queue_t，也无法保证block是在子线程中被执行，而且还有较为复杂的内存管理问题，最后使用NSThread与runloop才解决问题。

三. SDWebImage： (https://github.com/rs/SDWebImage) ，不需要多说，这个框架写的非常简洁，也是读这个框架，让我明白什么是缓存机制，以及如何做面向对象的封装设计，我之后有的场景也需要自己去设计一些cache，每次都是借鉴这个框架实现，能力有限，自己实在想不出比这个设计思路好的地方，只能借鉴别人的做法。我觉得这个项目还有一个非常值得推崇的地方，就是对category的使用，这个是我今年之前一直忽略的非常重要的设计模式，太适合团队开发了，<cocoa设计模式>上讲的东西，做到现在我才明白怎么回事，可以对比Android使用网络图片，你会发现OC的category真方便。

四.EGOTableViewPullRefresh： (https://github.com/enormego/EGOTableViewPullRefresh) ，本来不打算说UI方面类库的，但是这个必须说一下。建议读一下这个的源码，以及如何使用，对iOS UI开发有很大提升，这个类库写的很简洁，可以帮助理解delegate机制以及Protocol的概念，还能加深对UIScrollView的理解，推荐读一下。

五. TheElements： (https://developer.apple.com/library/ios/samplecode/TheElements/Introduction/Intro.html) ，这个是apple的官方示例代码，每次我朋友问题如何学习iOS的时候，我总会推荐这个samplecode，这个代码让我对iOS开发的理解有个很大的突破。里面并没有使用大量的storyboard和xib隐藏细节，并不是说只能用纯代码做事情，而是可以让人看到里面很多的实现细节，加深理解。读这个代码，我才明白什么是apple说的MVC，还有一个xcode工程到底是如何从main函数运行起来的，非常强烈推荐阅读学习。


