## 下方个版本说明，可以当做简单的wiki使用~，效果可参考DEMO。

### 1.5.8
* 修改了锁定屏幕触摸功能再播放结束后的问题。

### 1.5.7
* change AudioManger get。

### 1.5.6
* 修复了mUrl再error后为空的问题。
* 增加了GSYVideoManager的option配置接口。

```
/**
 * 设置IJK视频的option
 */
public void setOptionModelList(List<VideoOptionModel> optionModelList)
```

### 1.5.5
* update ijk 0.7.6。
* 快播与慢播接口支持M以下。


### 1.5.4
* 增加了静音播放接口。

GSYVideoManager下
可参考：ListNormalAdapter
```
/**
 * 是否需要静音
 */
public void setNeedMute(boolean needMute)
```

### 1.5.3
* 修改了在缓冲的时候，默认loading点击会重置的问题。
* 虚拟按键在弹出的后，过一段时间自动隐藏。

## 1.5.2
* 增加了Error的回调接口。
* 修复了Demo的PlayActivity兼容问题

### 1.5.1
* 全屏滑动弹出虚拟按键会影响进度问题。
* 优化了滑动的弹出dialog。
* 修改了一些问题。

### 1.5.0
* 增加了全屏和普通播放下使用两套布局的支持，增加demo：LandLayoutVideo。
* 修改了DEMO的recyclerView的一个问题。
* 修改了一些bug。
* 增加了WebView滑动demo。

```

/**
 * 如果需要使用到：全屏和普通播放下使用两套布局的支持。
 * 那么重载播放器请记得重载下方构造方法
 */
public XXXXXXXXXX(Context context, Boolean fullFlag) {
    super(context, fullFlag);
}

····

//这个必须配置最上面的构造才能生效
@Override
public int getLayoutId() {
    if (mIfCurrentIsFullscreen) {
        return R.layout.sample_video_land;
    }
    return R.layout.sample_video;
}

```
### 1.4.9
* 增加了连续播放列表的支持 ListGSYVideoPlayer。
* 增加了列表播放的demo  DetailListPlayer。
* 减小了https版本的so的大小。


### 1.4.8
* 锁定屏幕按键增加锁定屏幕旋转功能。
* 锁定屏幕按键增加回调接口。
* 修复了横屏的一个问题。

### 1.4.7
* 修复直接横屏有闪动的问题。
* 修改了流量提示的接口。
* 增加了HTTPS支持。

```
/**
 * 是否需要显示流量提示,默认true
 */
public void setNeedShowWifiTip(boolean needShowWifiTip)
```

### 1.4.6
* 修改了某些虚拟按键手机下，全屏后返回导致界面显示不正的问题。
* 增加测试版CustomGSYVideoPlayer，实现滑动进度条预览效果（测试效果）。
* 修改了出现除以0的的问题，全屏时候调整UI样式无效的情况。
* 注：CustomGSYVideoPlayer目前对已完全缓存的视频，或者本地文件支持好一些，对纯网络视频支持“较”差。

```
/**
 * 如果是需要进度条预览的设置打开，默认关闭
 */
public void setOpenPreView(boolean localFile)
```

### 1.4.5
* 支持切换IJKPlayer和EXOPlayer,不过EXOPlayer后台播放回到前台黑的问题除了seekto无解啊。

GSYVideoManager

```
/**
 * 设置了视频的播放类型
 * GSYVideoType IJKPLAYER = 0 or IJKEXOPLAYER = 1;
 */
public void setVideoType(Context context, int videoType)
```

### 1.4.4

* 调整lib，DEMO中SampleVideo增加了调整清晰度的支持,DEMO借用了jjdxm_ijkplayer的URL。
* 优化了Cache缓存和IJK 缓存之间的显示。


### 1.4.3

* 增加了设置显示比例GSYVideoType。
* DEMO增加SampleVideo，在PlayActivity使用，调节显示比例效果。
* 增加了开启和关闭硬解码的接口GSYVideoType。

GSYVideoType
```
/**
 * 设置显示比例
 */
public static void setShowType(int type)

/**
 * 使能硬解码，播放前设置
 */
public static void enableMediaCodec() {
    MEDIA_CODEC_FLAG = true;
}

/**
 * 关闭硬解码，播放前设置
 */
public static void disableMediaCodec()
```

### 1.4.2

* 修改了暂停画面在对旋转视频/竖屏播放时变形的问题。
* 调整了亮度的灵敏度，优化了亮度调节。

### 1.4.1

* 增加了全屏锁开关，锁定后屏幕点击无效。
* 增加了全局暂停和播放，支援列表状态。
* 修正了亮度调节的问题。

StandardGSYVideoPlayer/ListVideoUtil

```
/**
 * 是否需要全屏锁定屏幕功能
 * 如果单独使用请设置setIfCurrentIsFullscreen为true
 */
public void setNeedLockFull(boolean needLoadFull)
```

GSYVideoManager

```
/**
 * 暂停播放
 */
public static void onPause()

/**
 * 恢复播放
 */
public static void onResume()
```


### 1.4.0 (3.8和3.9难产了)

* 添加了lib封面对复用封面的支持和demo。
* 修复了缓冲进度条；
* 增加了recyclerViewDemo。
* update VideoCache，去除error out put log输出。
* 修正了列表中隐藏虚拟键盘与actionbar的冲突。



### 1.3.7
* 优化了弹出框。
* 优化了暂停的时候(全屏/恢复全屏/退到)会是黑色的问题。
* 解决了暂停的时候拖动进度条问题。


### 1.3.6
* 区分了没有网络和没有wifi的提示。
* 更新了Demo detailPlayer直接旋转全屏。
* 返回正常的详情效果。


### 1.3.5
* 增加了全屏隐藏虚拟按键。
* 修复了缓冲过程中加载动画就停止了。

```
/**
 * 全屏隐藏虚拟按键，默认打开
 */
public void setHideKey(boolean hideKey)
```

### 1.3.4
* 增加了清除默认缓存接口。
* 增加了播放偏移。
* 优化了拖动进度条或者缓存导致播放时间跳动的问题。

GSYVideoManager

```
/**
 * 删除默认所有缓存文件
 */
public static void clearAllDefaultCache(Context context)

/**
 * 删除url对应默认缓存文件
 */
public static void clearDefaultCache(Context context, String url)
```

GSYVideoPlayer

```

/**
 * 清除当前缓存
 */
public void clearCurrentCache()

/**
 * 从哪里开始播放
 * 目前有时候前几秒有跳动问题
 */
public void setSeekOnStart(int seekOnStart)

```

### 1.3.3

* 优化了一些内存泄漏问题。
* 更新了demo。

### 1.3.2

* 解决了因为兼容FragmentActivity导致actionbar隐藏失败问题。

### 1.3.1
* 更新了lastListener的判空问题。

### 1.3.0
* 支持配置缓存路径，添加了ListVideoUtils的一些接口。

正常模式

```
//默认缓存路径方式
holder.gsyVideoPlayer.setUp(url, true , "");

···

//一个列表的视频缓存路径相同
holder.gsyVideoPlayer.setUp(url, true, new File(FileUtils.getTestPath(), ""));

···

//如果一个列表里的缓存路径不同，需要用下方的方式

//避免全屏返回的时候不可用了，只初始化不是当前位置的ui
if (playPosition < 0 || playPosition != position ||
        !GSYVideoManager.instance().getPlayTag().equals(ListNormalAdapter.TAG)) {
    holder.gsyVideoPlayer.initUIState();
}

//如果设置了点击封面可以播放，如果缓存列表路径不一致，还需要设置封面点击
holder.gsyVideoPlayer.setThumbPlay(true);

holder.gsyVideoPlayer.getStartButton().setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        //需要切换缓存路径的
        holder.gsyVideoPlayer.setUp(url, true, new File(FileUtils.getTestPath(), ""));
        holder.gsyVideoPlayer.startPlayLogic();
    }
});

holder.gsyVideoPlayer.getThumbImageViewLayout().setOnClickListener(new View.OnClickListener() {
    @Override
    public void onClick(View v) {
        //需要切换缓存路径的
        holder.gsyVideoPlayer.setUp(url, true, new File(FileUtils.getTestPath(), ""));
        holder.gsyVideoPlayer.startPlayLogic();
    }
});
```
ListVideoUtils

```
public void setCachePath(File cachePath)

public void setObjects(Object[] objects)

public void setMapHeadData(Map<String, String> mapHeadData)

```


### 1.2.9

* 增加了下载速度的接口。

```
/**
 * 网络速度
 * 注意，这里如果是开启了缓存，因为读取本地代理，缓存成功后还是存在速度的
 * 再打开已经缓存的本地文件，网络速度才会回0.因为是播放本地文件了
 */
public long getNetSpeed()

/**
 * 网络速度
 * 注意，这里如果是开启了缓存，因为读取本地代理，缓存成功后还是存在速度的
 * 再打开已经缓存的本地文件，网络速度才会回0.因为是播放本地文件了
 */
public String getNetSpeedText()

```

### 1.2.8

* 升级IJKPlayer到0.7.5。
* 增加了改变播放速度(0-2左右的速度)，但只支持6.0以上。

```
/**
 * 播放速度
 */
public void setSpeed(float speed)
```

### 1.2.7
* 修改了循环播放的时候，重新播放不弹出控制UI。
* 修改了FragmentActivity的actionBar问题。


### 1.2.6

* 修正了StandardGSYVideoPlayer的接口全屏回调问题。
* 增加了循环播放的接口。

```

public void setLooping(boolean looping)

```


### 1.2.5

* 增加了新接口，支持直接横屏锁住界面。
* 关闭全屏动画，组合接口使用。

##### GSYVideoPlayer

```
/**
 * 全屏动画
 *
 * @param showFullAnimation 是否使用全屏动画效果
 */
public void setShowFullAnimation(boolean showFullAnimation)

/**
 * 是否开启自动旋转
 */
public void setRotateViewAuto(boolean rotateViewAuto)

/**
 * 一全屏就锁屏横屏，默认false竖屏，可配合setRotateViewAuto使用
 */
public void setLockLand(boolean lockLand)
```

##### ListVideoUtil

```
/**
 * 是否自动旋转
 *
 * @param autoRotation 是否要支持重力旋转
 */
public void setAutoRotation(boolean autoRotation) {
    this.autoRotation = autoRotation;
}

/**
 * 是否全屏就马上横屏
 *
 * @param fullLandFrist 如果是，那么全屏的时候就会切换到横屏
 */
public void setFullLandFrist(boolean fullLandFrist) {
    this.fullLandFrist = fullLandFrist;
}

/**
 * 全屏动画
 *
 * @param showFullAnimation 是否使用全屏动画效果
 */
public void setShowFullAnimation(boolean showFullAnimation) {
    this.showFullAnimation = showFullAnimation;
}
```


### 1.2.4

* 兼容API修改至16,全屏动画兼容全API。
　

### 1.2.3

*增加了X86类型的依赖，个人可根据爱好在APP的build里面添加自己要的支持类型。

arm64和-86_64的没有加入，如果需要自己添加即可，因为编译最低需要API21

```
android {
···
defaultConfig {
    ···
    ndk {
        //设置支持的SO库架构
        abiFilters 'armeabi', 'armeabi-v7a', 'x86'
    }
}

```


### 1.2.2

*开放了取时长和总时长的接口。
*增加了VideoAllCallBack的准备视频完成的回调onPrepared。

```

 listVideoUtil.getDuration()
 listVideoUtil.getCurrentPositionWhenPlaying();

 GSYVideoPlayer.getDuration()
 GSYVideoPlayer.getCurrentPositionWhenPlaying();

```


### 1.2.1

* 调整了小窗口回调拦截错误的情况。
* 增加了SampleListener在列表小窗口点击关闭的时候更新页面。

```
//小窗口关闭被点击的时候回调处理回复页面
listVideoUtil.setVideoAllCallBack(new SampleListener(){
    @Override
    public void onQuitSmallWidget(String url, Object... objects) {
        super.onQuitSmallWidget(url, objects);
        //大于0说明有播放,//对应的播放列表TAG
        if (listVideoUtil.getPlayPosition() >= 0 && listVideoUtil.getPlayTAG().equals(ListVideoAdapter.TAG)) {
            //当前播放的位置
            int position = listVideoUtil.getPlayPosition();
            //不可视的是时候
            if ((position < firstVisibleItem || position > lastVisibleItem)) {
                //释放掉视频
                listVideoUtil.releaseVideoPlayer();
                listVideoAdapter.notifyDataSetChanged();
            }
        }
    }
});
```
　
### 1.2.0

* 去除了一些无用的依赖库，升级IJKPlayer到0.7.4。

更容易导入，减少了无用的依赖情况，去除了import的时候需要配置gradle.properties的问题。

### 1.1.9

* 修正了回调接口VideoAllCallBack的回调结果，添加了注释，可以根据需要继承后覆写。

有全屏到非全屏，有小窗口到非小窗口，结束播放错误触摸等等的接口回调，增加了Debuger，可以使能或者关闭调试输出。

### 1.1.8

* 增加了如果Cache文件出现播放异常，就清除缓存文件的处理（预防）。
* StandardGSYVideoPlayer增加了一些UI配置接口。

```
/**
 * 底部进度条-弹出的
 */
public void setBottomShowProgressBarDrawable(Drawable drawable, Drawable thumb)


/**
 * 底部进度条-非弹出
 */
public void setBottomProgressBarDrawable(Drawable drawable)

/**
 * 声音进度条
 */
public void setDialogVolumeProgressBar(Drawable drawable)


/**
 * 中间进度条
 */
public void setDialogProgressBar(Drawable drawable)

/**
 * 中间进度条字体颜色
 */
public void setDialogProgressColor(int highLightColor, int normalColor)

```

### 1.1.7

* 增加了第二种列表 ListVideoUtil可拖动小窗口支持。

```
@Override
public void onScroll(AbsListView view, int firstVisibleItem, int visibleItemCount, int totalItemCount) {
    int lastVisibleItem = firstVisibleItem + visibleItemCount;
    //大于0说明有播放,//对应的播放列表TAG
    if (listVideoUtil.getPlayPosition() >= 0 && listVideoUtil.getPlayTAG().equals(ListVideoAdapter.TAG)) {
        //当前播放的位置
        int position = listVideoUtil.getPlayPosition();
        //不可视的是时候
        if ((position < firstVisibleItem || position > lastVisibleItem)) {
            //如果是小窗口就不需要处理
            if (!listVideoUtil.isSmall()) {
                //小窗口
                int size = CommonUtil.dip2px(ListVideo2Activity.this, 150);
                listVideoUtil.showSmallVideo(new Point(size, size), false, true);
            }
        } else {
            if (listVideoUtil.isSmall()) {
                listVideoUtil.smallVideoToNormal();
            }
        }
    }
}
```

### 1.1.6
* 优化了第二种列表ListVideoUtil的全屏效果，和列表一的全屏效果一致，两种全屏效果增加是否打开关闭接口。

```
/**
 * 全屏动画
 *
 * @param showFullAnimation 是否使用全屏动画效果
 */
public void setShowFullAnimation(boolean showFullAnimation)
```

### 1.1.5

* 优化了一些UI，增加了一些有趣的动画，比如播放按键。
* 推荐这个动画效果[ENViews](https://github.com/codeestX/ENViews)。
* 增加自定义继承模板**SampleExtendsPlayer**，个人建议直接拷贝**StandardGSYVideoPlayer**修改也行。

### 1.1.4
* 优化了第一种列表的全屏动画,5.0以上展开和返回过渡顺畅，支持自动旋转的开启与关闭。
* 修改了全屏下的滑动接口不正常问题，全屏下自动变为滑动的，非全屏可以设置。

```
/**
 * 是否可以滑动界面改变进度，声音等
 */
public void setIsTouchWiget(boolean isTouchWiget)

```


### 1.1.2
* 增加了TAG和position来实现第一种list列表（非ListVideoUtil模式的列表实现）的滑动错位问题。

```

videoList.setOnScrollListener(new AbsListView.OnScrollListener() {
    @Override
    public void onScrollStateChanged(AbsListView view, int scrollState) {
    }

    @Override
    public void onScroll(AbsListView view, int firstVisibleItem, int visibleItemCount, int totalItemCount) {
        int lastVisibleItem = firstVisibleItem + visibleItemCount;
        //大于0说明有播放
        if (GSYVideoManager.instance().getPlayPosition() >= 0) {
            //当前播放的位置
            int position = GSYVideoManager.instance().getPlayPosition();
            //对应的播放列表TAG
            if (GSYVideoManager.instance().getPlayTag().equals(ListNormalAdapter.TAG)
                    && (position < firstVisibleItem || position > lastVisibleItem)) {
                //如果滑出去了上面和下面就是否，和今日头条一样
                GSYVideoPlayer.releaseAllVideos();
                listNormalAdapter.notifyDataSetChanged();
            }
        }
    }
});

····

holder.gsyVideoPlayer.setPlayTag(TAG);
holder.gsyVideoPlayer.setPlayPosition(position);

```

### 1.1.1
* 增加了ListVideoUtil全屏是否显示横屏，全屏是否自动旋转。
* 增加了ListVideoUtils隐藏状态栏和title的接口。


