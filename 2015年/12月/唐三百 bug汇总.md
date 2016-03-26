

[TOC]

## 清除缓存

- 清除缓存后，点击`历史记录`或`我的收藏`列表仍然有数据，但点击条目，界面闪退。关闭应用，再点击`历史记录`或`我的收藏`，这时，列表才清空。

解决方法：出现这个bug是由于清除了缓存后，没有关闭`SQLiteOpenHelper`导致的。

## 修改全局文字后，卡得不行

- 12月15日，修改全局的文字，使用这种方式：

``` 
@Override
public void setText(CharSequence text, TextView.BufferType type) {
        Typeface typeface = Typeface.createFromAsset(getContext().getAssets(), ICON_FONT_PATH);
        setTypeface(typeface);
        super.setText(text, type);
    }
```

解决方法：全局共用一个`Typeface`实例，即刻解决卡的问题，将这个`Typeface`实例作为`TangApplication`成员。