
一、 语言深度（Swift & OC 混编视角）
题目 1： 在 Swift 中，Struct 内部修改属性为什么必须加 mutating？其底层对 self 做了什么操作？

题目 2： 请解释 Swift 的类型擦除 (Type Erasure)。为什么要用 AnyIterable<T> 这种方式来包装协议？它解决了什么痛点？

题目 3： Objective-C 的 Block 捕获 __block 修饰的变量时，如果变量是基本类型，在 Block 从栈拷贝到堆的过程中，变量的内存地址是如何变化的？

题目 4： 谈谈 Swift Actor 的重入性 (Reentrancy) 问题。如果一个 async 方法在执行过程中挂起，其他任务进入 Actor 会发生什么？

二、 底层原理（Runtime & 线程安全）
题目 1： 假如一个对象调用了一个没有实现的方法，在消息转发的“补救”阶段，forwardingTargetForSelector: 和 forwardInvocation: 在性能和灵活性上有什么区别？

题目 2： 深入 RunLoop：为什么 NSTimer 默认在 NSDefaultRunLoopMode 下滑动时会停止？如果我们要实现一个高精度的定时器且不阻塞 UI，你会如何设计？

题目 3： 线程安全： 既然 atomic 不能保证绝对的线程安全（如对数组的操作），请写出一种基于 dispatch_barrier 实现“多读单写”的高性能缓存方案。

题目 4： weak 指针在被置为 nil 的那一刻，底层是如何通过 sideTable 查找到并清除对应地址的？

三、 UI 渲染与性能调优
题目 1： 描述一次点击事件从触摸屏幕到找到最终响应者的完整路径。如果在 hitTest 中返回 nil，会对子视图产生什么影响？

题目 2： 离屏渲染： 为什么给 UIImageView 设置圆角和 masksToBounds 在 iOS 9 之后可能不再触发离屏渲染，而给 UIView 设置却依然会？

题目 3： 监控工具：如果不使用 Instruments，你如何通过代码实时获取当前 App 的 CPU 使用率和 堆内存占用？

题目 4： 如何通过 CADisplayLink 实现一套线上卡顿监控系统？如何判定“堆栈信息”落在了哪个耗时方法上？

四、 架构设计与模式
题目 1： 在 MVVM 架构中，如果你不使用 RxSwift 或 Combine，你会如何实现 View 和 ViewModel 之间的双向绑定？请写出核心伪代码。

题目 2： 组件化： 谈谈 CTMediator (基于 Target-Action) 和 BeeHive (基于 Protocol) 的优缺点。在大型项目中，如何处理组件间的回调（如 A 组件需要 B 组件处理完后异步返回数据）？

题目 3： 谈谈你对 依赖注入 (Dependency Injection) 的理解。它在单元测试中起到了什么关键作用？

五、 工程化与网络安全
题目 1： 启动优化： 什么是 Order File 二进制重排？它是如何通过减少 Page Fault（缺页中断）来加速启动的？

题目 2： 网络安全： 描述 HTTPS 的“双向认证”流程。如果在抓包工具（如 Charles）中能看到明文，说明 App 缺少了哪项安全加固？

题目 3： 包体积： 业务线过长导致 IPA 超过 200MB，请列举至少 3 种有效的包体积瘦身手段（除压缩图片外）。
