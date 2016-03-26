# 3月18日(ListView type，CheckBox错乱)

## 总结

### ListView type

今天上午又被“ListView”恶心到了，为了在ListView中显示多种类型的ItemView，除了复写

```
public int getCount()

public Object getItem(int position)

public View getView(int position, View convertView, ViewGroup parent)

```

这三个方法外还要复写另外两个方法：

```
public int getItemViewType(int position)

public int getViewTypeCount()
```

刚开始的时候马虎大意，忘记了复写`getViewTypeCount`，这是我的错，这得承认，依然还有错，继续跟网上的Blog比较，getView()应该没有错了，怎么还是有问题呢，然后又把需要复写的这五个方法重新撸了一遍，还是不对，问题出在滚动到下一屏闪退，控制台的错误信息时：

```
java.lang.ArrayIndexOutOfBoundsException: length=2; index=49
```

怎么会有49呢，那么只能怀疑是我的TYPE_XXX常量写的有问题了，因为有一个常量我定义的值是：`0x31`，接着又跟[Android ListView添加多种类型的ItemView](http://www.cnblogs.com/sw926/p/3426606.html)这篇文章中Type常量对比了一下，发现他的常量定义是从0开始依次加一，然后就又尝试了一遍，发现好了，心里慰问了ListView作者的妈妈一百遍，你管我定义什么常量呢！！！

### ListView checkbox

Checkbox在ListView错乱的原因是类似的，可以看这篇文章：

[ListView with CheckBox Scrolling Issue](http://lalit3686.blogspot.co.id/2012/06/today-i-am-going-to-show-how-to-deal.html)，以后再出现这样的问题，只参考这篇文章。

## 今日目标

- [x] 完成"指定用户"

- [ ] 完成"指定群组"

- [ ] 修复一个Bug

      描述："我的文件TAB"-"keystore文件夹"-"分享sharedemo.jks"-"点击设置"-"崩溃"

      异常：` ObjectNotFound, DetailMsg : The pub object can not be found, Payload: null
- [x] 解决CheckBox在ListView中错乱显示的问题
- [x] 解决“指定群组”中type不同的ItemView，CheckBox在ListView中错乱显示的问题。
