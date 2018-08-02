### MediaPlayer
+ MediaPlayer既可以播放音频，也可以播放视频；

|MediaPlayer的接口|说明|
|------|------|
|MediaPlayer.OnBufferingUpdateListener|定义了唤起指明网络上的媒体资源以缓冲流的形式播放|
|MediaPlayer.OnCompletionListener|为当媒体资源的播放完成后被唤起的回放定义的|
|MediaPlayer.OnErrorListener|定义了当在异步操作的时候(其他错误将会在呼叫方法的时候抛出异常)出现错误后唤起的回放操作|
|MediaPlayer.OnInfoListener|定义了与一些关于媒体或它的播放的信息以及/或者警告相关的被唤起的回放|
|MediaPlayer.OnSeekCompleteListener|定义了指明查找操作完成后唤起的回放操作|
|MediaPlayer.OnVideoSizeChangedListener|定义了当视频大小被首次知晓或更新的时候唤起的回放|

|MediaPlayer的常用方法|说明|
|------|------|
|public static MediaPlayer create(Context context, Uri uri) |根据给定的uri创建|
|public static MediaPlayer create(Context context, int resid)|根据给定的资源id创建|
|public static MediaPlayer create(Context context, Uri uri, SurfaceHolder holder)|根据给定的uri创建|
|public native int getCurrentPosition()|获取当前播放的位置|
|public native int getDuration()|获取文件段|
|public native int getVideoHeight()|获取视频的高度|
|public native int getVideoWidth()|获取视频的宽度|
|public native boolean isLooping()|是否处于循环|
|public native boolean isPlaying()|是否正在播放|
|public void pause()|暂停播放|
|public void prepare()|让播放器处于准备状态(同步的)|
|public native void prepareAsync()|让播放器处于准备状态(异步的)|
|public void release()|释放资源|
|public void reset()|重置到初始化状态|
|public void seekTo(long msec, @SeekMode int mode)|搜寻指定的时间位置|
|public void setAudioStreamType(int streamtype)|设置音频流类型|
|public void setDataSource(@NonNull Context context, @NonNull Uri uri)|指定一个uri内容的资源|
|public void setDataSource(FileDescriptor fd)|指定数据源|
|public void setDataSource(String path)|从指定的path路径所代表的文件|
|public void setDataSource(FileDescriptor fd, long offset, long length)|指定装载fd所代表的文件中从offset开始长度为length的文件内容|
|public void setDisplay(SurfaceHolder sh)|设定播放该video的媒体播放器的SurfaceHolder|
|public native void setLooping(boolean looping)|设置播放器循环还是不循环|
|public void setOnBufferingUpdateListener(OnBufferingUpdateListener listener)|注册一个当网络缓冲数据流变化时唤起的播放事件|
|public void setOnCompletionListener(OnCompletionListener listener)|注册一个当媒体资源在播放的时候到达终点时唤起的播放事件|
|public void setOnErrorListener(OnErrorListener listener)|注册一个当在异步操作过程中发生错误的时候唤起的播放事件|
|public void setOnInfoListener(OnInfoListener listener)|注册一个当有消息/警告出现的时候唤起的播放事件|
|public void setOnPreparedListener(OnPreparedListener listener)|注册一个当媒体资源准备播放时唤起的播放事件|
|public void setOnSeekCompleteListener(OnSeekCompleteListener listener)|注册一个当搜寻操作完成后唤起的播放事件|
|public void setOnVideoSizeChangedListener(OnVideoSizeChangedListener listener)|注册一个当视频大小知晓或更新后唤起的播放事件|
|public void setScreenOnWhilePlaying(boolean screenOn)|控制当视频播放发生时是否使用ＳurfaceＨolder来保持屏幕|
|public void setVolume(float leftVolume, float rightVolume)|设置播放器的音量|
|public void setWakeMode(Context context, int mode)|设置低等级的电源管理状态|
|start()|开始或恢复播放|
|stop()|停止播放|








