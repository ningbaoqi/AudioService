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
