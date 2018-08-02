### ＭediaPlayer播放视频文件
+ `SurfaceView` 具有`双缓冲技术`, 该组件是一个`重量级组件`，只要不可见就不会创建，可见时，才会创建，只要不可见，就会销毁；因此一般推荐使用`VideoView`来播放视频；

|使用MediaPlayer播放视频的步骤|
|------|
|创建MediaPlayer对象，并让它加载指定的视频文件|
|在界面布局文件中定义SurfaceView组件，或在程序中创建SurfaceView组件，并为SurfaceView的SurfaceHolder添加Callback监听器|
|调用MediaPlayer对象的setDisplay(SurfaceHolder sh)方法将所播放的视频图像输出到指定的SurfaceView组件|
|调用MediaPlayer对象的start()、stop()、pause()方法控制视频的播放|

#### Activity

```
public class MainActivity extends AppCompatActivity {
     private MediaPlayer player;
     SurfaceHolder holder;
     static int position;
     @Override
     protected void onCreate(Bundle savedInstanceState) {
         super.onCreate(savedInstanceState);
         setContentView(R.layout.activity_main);
         SurfaceView surfaceView = (SurfaceView) findViewById(R.id.surface);
         holder = surfaceView.getHolder();
         playVideo();
     }
     private void playVideo() {
         holder.addCallback(new SurfaceHolder.Callback() {
             @Override
             public void surfaceCreated(SurfaceHolder holder) {
                 if (player == null) {
                     player = new MediaPlayer();
                 }
                 player.reset();
                try {
                     player.setDataSource("http://192.168.188.41:8080/sb.mp4");
                     player.setDisplay(holder);
                     player.prepareAsync();
                     player.setOnPreparedListener(new MediaPlayer.OnPreparedListener() {
                         @Override
                         public void onPrepared(MediaPlayer mp) {
                             player.start();
                             player.seekTo(position);
                         }
                     });
                 } catch (Exception e) {
                     e.printStackTrace();
                 }
             }
             @Override
             public void surfaceChanged(SurfaceHolder holder, int format, int width, int height) {//结构改变时调用
             }
             @Override
             public void surfaceDestroyed(SurfaceHolder holder) {//销毁时调用，销毁时停止播放视频
                 if (player != null) {
                     position = player.getCurrentPosition();
                     player.stop();
                     player.release();
                     player = null;
                 }
            }
         });
     }
 }
```

#### res/layout/activity_main.xml

```
<LinearLayout>
    <SurfaceView
         android:id="@+id/surface"
         android:layout_width="match_parent"
         android:layout_height="match_parent" />
</LinearLayout>
```
