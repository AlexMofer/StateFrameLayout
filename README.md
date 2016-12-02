# StateFrameLayout
![ICON](https://raw.githubusercontent.com/AlexMofer/ProjectX/master/stateframelayout/icon.png)

项目详细地址：[**ProjectX**](https://github.com/AlexMofer/ProjectX/tree/master/stateframelayout)(方便统一管理)

状态帧布局，通常用于网络请求的四种状态，普通、载入、错误、空白。支持Drawable或者View来展示，也可以混搭。
## 预览
![Screenshots](https://raw.githubusercontent.com/AlexMofer/ProjectX/master/stateframelayout/screenshots.gif)
## 要求
minSdkVersion 4
## 引用
```java
dependencies {
    ⋯
    compile 'am.widget:stateframelayout:1.0.3'
    ⋯
}
```
## 使用
- 基本布局
```xml
<am.widget.stateframelayout.StateFrameLayout
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    app:sflLoadingDrawable="@drawable/"
    app:sflErrorDrawable="@drawable/"
    app:sflEmptyDrawable="@drawable/"
    app:sflState="loading">
    ⋯
</am.widget.stateframelayout.StateFrameLayout>
```
- 基本代码
```java
lytState = (StateFrameLayout) findViewById(R.id.sfl_lyt_state);
lytState.setOnStateClickListener(listener);
lytState.setStateDrawables(mLoadingDrawable, mErrorDrawable, mEmptyDrawable);
lytState.setStateViews(mLoadingView, mErrorView, mEmptyView);
```
## 注意
- 继承自帧布局
- 各种状态下都不拦截子View的点击事件，除Normal状态且isAlwaysDrawChild() == true时，内容子项不会被绘制及显示
- setAlwaysDrawChild(true)强制各种状态下都显示内容子项

## 历史
- [**1.0.2**](https://bintray.com/alexmofer/maven/StateFrameLayout/1.0.2)
- [**1.0.1**](https://bintray.com/alexmofer/maven/StateFrameLayout/1.0.1)
- [**1.0.0**](https://bintray.com/alexmofer/maven/StateFrameLayout/1.0.0)
