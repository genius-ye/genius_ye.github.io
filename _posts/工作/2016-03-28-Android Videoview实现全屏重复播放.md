---
layout: blog
title: Android Videoview实现全屏重复播放
background-image: https://cdn.sspai.com/2018/01/26/416e1fb49b1375be6f851fecdc38e292.jpg?imageMogr2/quality/95/thumbnail/!700x233r/gravity/Center/crop/700x233
istop: true
work: true
category: 工作
tags: 
    work
    android
---

### 1.videoview实现全屏

> 代码：

``` java

import android.content.Context;
import android.util.AttributeSet;
import android.widget.VideoView;

public class FullVideoView extends VideoView {

	public FullVideoView(Context context) {
		super(context);
		// TODO Auto-generated constructor stub
	}

	public FullVideoView(Context context, AttributeSet attrs) {
		super(context, attrs);
	}

	public FullVideoView(Context context, AttributeSet attrs, int defStyle) {
		super(context, attrs, defStyle);
	}

	@Override
	protected void onMeasure(int widthMeasureSpec, int heightMeasureSpec) {
		int width = getDefaultSize(0, widthMeasureSpec);
		int height = getDefaultSize(0, heightMeasureSpec);
		setMeasuredDimension(width, height);
	}

}

```
### 2.videoview实现重复播放

> 代码：

``` java
 videoView.setOnCompletionListener(new MediaPlayer.OnCompletionListener() {
            @Override
            public void onCompletion(MediaPlayer mp) {
                videoView.setVideoPath(filePath);
                videoView.start();
            }
        });

```
