# refreshlayout介绍

为了统一support包版本而创建的，希望大家引用原项目，本项目不维护，

TwinklingRefreshLayout原项目：https://github.com/lcodecorex/TwinklingRefreshLayout


本项目修改了support包版本及一些细节来满足公司项目的需求的！！！！！


# 使用
```java
allprojects {
    repositories {
	  ...
	  maven { url 'https://jitpack.io' }
    }
}

dependencies {
       compile 'com.github.supertaohaili:RefreshLayout:1.0.0'
}
```
```xml
<?xml version="1.0" encoding="utf-8"?>
<com.lcodecore.tkrefreshlayout.TwinklingRefreshLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/refreshLayout"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    app:tr_wave_height="180dp"
    app:tr_head_height="100dp">

    <android.support.v7.widget.RecyclerView
        android:id="@+id/recyclerview"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:overScrollMode="never"
        android:background="#fff" />
</com.lcodecore.library.TwinklingRefreshLayout>
```
```java
refreshLayout.setOnRefreshListener(new RefreshListenerAdapter(){
            @Override
            public void onRefresh(final TwinklingRefreshLayout refreshLayout) {
                new Handler().postDelayed(new Runnable() {
                    @Override
                    public void run() {
                        refreshLayout.finishRefreshing();
                    }
                },2000);
            }

            @Override
            public void onLoadMore(final TwinklingRefreshLayout refreshLayout) {
                new Handler().postDelayed(new Runnable() {
                    @Override
                    public void run() {
                        refreshLayout.finishLoadmore();
                    }
                },2000);
            }
        });
    }
```


### Known Issues
If you have any questions/queries/Bugs/Hugs please mail @
taohailili@gmail.com