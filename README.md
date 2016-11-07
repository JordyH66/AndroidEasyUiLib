#关于EasyUi说明#
EasyUi 是为了让更多的人在使用Ui 或找寻Ui 的时候简单哈。

目前大致的方向是将手上的Ui 做个一个个Activiy 加入项目中来。

如果你也想参数,可以下载代码。然后新建你的package

之后修改MainActivity中的
mActivityUiClass 和 mActiviUiTitles 两个变量

如
```
	private Class[] mActivityUiClass = new Class[]{
            NewsTopTitleActivity.class
    };
    private String[] mActiviUiTitles = new String[]{
            "仿新闻顶部导航"
    };
```

MainActivity在initViews方法中会将这些动态添加进去

```
	for( index = 0; index < mActiviUiTitles.length;index++){
            final int i = index;
            Button button = new Button(getApplicationContext());
            button.setTextColor(Color.BLACK);
            button.setText(mActiviUiTitles[i]);
            button.setOnClickListener(new View.OnClickListener() {
                @Override
                public void onClick(View view) {
                    startActivity(new Intent(MainActivity.this,mActivityUiClass[i]));
                }
            });
            mLayout.addView(button);
        }
```

当然,如果你创建了新的ui ,请不要忘记在<font color="red">AndroidManifest.xml</font>文件中注册你的Activity

* <activity android:name=".newstoptitle.NewsTopTitleActivity" ></activity>

同时为了让大家更加简单实用这个Ui ,请不要忘记编写注释。