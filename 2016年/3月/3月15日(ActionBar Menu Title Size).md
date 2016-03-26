# 3月15日(ActionBar Menu Title Size)

## 总结

- 解释 ProgressBar 属性

  ```
  public static ProgressDialog show(
  Context context, // 上下文
      CharSequence title, // 标题，设为null可以去掉标题
      CharSequence message, // 显示一个提示语
      // 单词的意思是模糊的，为true时，显示一个无限滚动的圆圈；为false时，显示具体的进度
      boolean indeterminate,
      boolean cancelable, //是否可以取消
      OnCancelListener cancelListener)// 取消时回调
  ```


- 改变ActionBar Menu Title Size

​	可以在主题Style中添加一个属性`actionMenuTextAppearance`，使用中记得兼容性问题，高版本下要加上`android:XXX`具体使用方法：

```
 <style name="Nutstore.Theme" parent="Theme.AppCompat.Light.DarkActionBar">
 	<item name="actionMenuTextAppearance">
    	@style/Nutstore.ActionBar.MenuTitleStyle</item>
 </style>
 <style name="Nutstore.ActionBar.MenuTitleStyle"
 	parent="TextAppearance.AppCompat.Widget.ActionBar.Menu">
 	<item name="android:textSize">18sp</item>
 </style>

```



​	

## 今日目标

- [x] 添加加载进度条
- [x] 给**NutstoreSettingsShareOptions**添加返回按钮
- [x] 完成**日期时间**界面和功能
- [x] 完成**密码访问**
- [x] 完成**禁止下载**
- [x] 完成**允许上传**

## 明日目标

1. 根据目前使用到的API编写文档，参考微博API文档。
2. 分析并编写"分享权限-指定用户"

