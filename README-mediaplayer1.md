### ＭediaPlayer播放视频文件
+ `SurfaceView` 具有`双缓冲技术`, 该组件是一个`重量级组件`，只要不可见就不会创建，可见时，才会创建，只要不可见，就会销毁；因此一般推荐使用`VideoView`来播放视频；

|使用MediaPlayer播放视频的步骤|
|------|
|创建MediaPlayer对象，并让它加载指定的视频文件|
|在界面布局文件中定义SurfaceView组件，或在程序中创建SurfaceView组件，并为SurfaceView的SurfaceHolder添加Callback监听器|
|调用MediaPlayer对象的setDisplay(SurfaceHolder sh)方法将所播放的视频图像输出到指定的SurfaceView组件|
|调用MediaPlayer对象的start()、stop()、pause()方法控制视频的播放|
