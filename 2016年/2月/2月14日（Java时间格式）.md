# 2月14日（Java时间格式）

## 总结

1. 几天完成并上传了 FooterView 接口，作用主要是帮助实现 **带有底部** 加载条的适配器。由于对`RecyclerView#OnScrollListener`并不太熟悉，并且不是特别核心的功能，所以现在只实现了**最后一个Item可见，并且Scroll_State_Idel**时，加载数据的功能。有时间的话，再补上其他的功能。
   
2. 今天在解析时间字符串时，遇到了点问题，格式如下：
   
   `Sun Feb 14 15:28:28 +0800 2016`，使用`new SimpleDateFormat(formatStr);`来解析，结果解析失败，后来参考了[27/Feb/2008:10:12:44 +0800这样的日期格式在java里的解析.](http://www.blogjava.net/jjwwhmm/archive/2008/02/28/182679.html)这篇文章，使用另外一个构造：`new SimpleDateFormat(formatStr, Locale.ENGLISH);`。解决了这个问题

## 今日目标

- [x] 根据 FooterLceRecyclerFragment.java 和 RefreshRecyclerFragment.java 编写实例代码
- [ ] 继续写《Liam》
- [ ] Timeline Item 的 Text 中的**链接**
- [x] 图片加载工具 `ImageLoader`，封装了`Picasso`
- [x] Java 的时间格式



## 明日目标

1. 继续写《Liam》
   1. Timeline Item 的 Text 中的**链接**

