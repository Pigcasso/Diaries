# 1月29日（分析Aisen请求数据的实现）

## 总结

今天虽然没有完成一项**今日目标**，不过收获远远大于完成这些目标。

今天上午为了解决一些小的不该再犯的SB问题，忙活了不少时间，比如ProgressBar隐藏的问题。然后跟踪Aisen项目，分析它的缓存机制，Debug了一下午。晚上就总结了一下下午的成果，收获良多。具体的内容都在`/Develop/Summary/Liam微博客户端总结/调研《Aisen》微博客户端缓存机制.md`中了。明天还是接着分析没有分析完的内容，可能还会对我的代码进行一番重构。

## 今日目标

- [ ] 完成`WeiboRefreshListFragment.java`获取缓存和保存缓存的功能（主要是决定规则）
- [ ] 完成`WeiboRefreshListFragment.java`处理**网络异常**的问题
- [ ] 调研Timeline的Item实现

## 明日目标

1. 读Aisen源码
   1. 分析`ICacheUtility # findCacheData)`实现
   2. 分析`ABizLogic # putToCache()`实现
2. 调研[Realm Java](https://realm.io/cn/docs/java/latest/#json)
3. 看一篇文章    [笔记 - Android应用架构 (Android Dev Summit 2015)](http://blog.zhaiyifan.cn/2016/01/29/android-app-architecture-2015/?from=groupmessage&isappinstalled=0)