# 2月4日（总结Android Drawable）

## 总结

今天忘了一个知识点，给TextView设置了一个background，用的是SelectListDrawable，就是想实现View在不同状态下改变背景色。怎么试效果就是出不来，忘了一件事，还是通过源码比较直接：

``` 
public void setOnClickListener(@Nullable OnClickListener l) {
	if (!isClickable()) {
		setClickable(true);
	}
	getListenerInfo().mOnClickListener = l;
}

public boolean onTouchEvent(MotionEvent e) {
	...
    if (((viewFlags & CLICKABLE) == CLICKABLE ||
    (viewFlags & LONG_CLICKABLE) == LONG_CLICKABLE) ||
    (viewFlags & CONTEXT_CLICKABLE) == CONTEXT_CLICKABLE) {
    ...
}
```

创建TextView的时候，默认状态下并不会设置CLICKABLE，可以通过添加点击监听，判断TextView是否可点，如果isClickable为false，就会添加CLICKABLE标记，这个时候再回调onTouchEvent的时候`if (((viewFlags & CLICKABLE) == CLICKABLE ||…`处理点击事件的代码才会被执行。

## 今日目标

- [ ] 阅读 [RecyclerView初探](http://blog.csdn.net/wanglu198506/article/details/43898131)
- [ ] 着手Timeline Item的实现，除了图片加载以外，要尽快完成
- [x] 总结《艺术探索》 Android的Drawable（已保存到/Summary/中）

## 明日目标

- [ ] 调研主题切换（参考App <Material Design Palettes>）
- [ ] 阅读 [RecyclerView初探](http://blog.csdn.net/wanglu198506/article/details/43898131)
- [ ] 着手Timeline Item的实现，除了图片加载以外，要尽快完成

