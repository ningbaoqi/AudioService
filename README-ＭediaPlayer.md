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
