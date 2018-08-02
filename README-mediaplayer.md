### ＭediaPlayer播放音频文件
##### Activity

```
 public class MainActivity extends AppCompatActivity {
     private Intent intent;
     private MyServiceConnection connection;
     private MusicPlayerProxyInterface player;
     private static SeekBar seekBar;
     static Handler handler = new Handler() {
         @Override
         public void handleMessage(Message msg) {
             super.handleMessage(msg);
             Bundle bundle = msg.getData();
             int total = bundle.getInt("total");
             int current = bundle.getInt("current");
             seekBar.setMax(total);
             seekBar.setProgress(current);
         }
     };
     @Override
     protected void onCreate(Bundle savedInstanceState) {
         super.onCreate(savedInstanceState);
         setContentView(R.layout.activity_main);
         seekBar = (SeekBar) findViewById(R.id.seek);
         seekBar.setOnSeekBarChangeListener(new SeekBar.OnSeekBarChangeListener() {
             @Override
             public void onProgressChanged(SeekBar seekBar, int progress, boolean fromUser) {//手指滑动时调用
             }
             @Override
             public void onStartTrackingTouch(SeekBar seekBar) {//手指按下时调用
             }
             @Override
             public void onStopTrackingTouch(SeekBar seekBar) {//手指抬起时调用
                /**
                  * 根据拖动的进度改变音乐的播放进度
                  * */
                 int current = seekBar.getProgress();
                 player.seekTo(current);
             }
         });
         intent = new Intent(this, PlayMusicService.class);
         connection = new MyServiceConnection();
         startService(intent);
         bindService(intent, connection, BIND_AUTO_CREATE);
     }
     public void play(View view) {
         player.play();
     }
     public void pause(View view) {
         player.pause();
     }
     public void continuePlay(View view) {
         player.continuePlay();
     }
     public void exit(View view) {
         unbindService(connection);
         stopService(intent);
     }
     class MyServiceConnection implements ServiceConnection {
         @Override
         public void onServiceConnected(ComponentName name, IBinder service) {
             player = (MusicPlayerProxyInterface) service;
         }
         @Override
         public void onServiceDisconnected(ComponentName name) {
         }
     }
 }
```

##### MusicPlayerProxyInterface.java

```
public interface MusicPlayerProxyInterface {
     void play();
     void pause();
     void continuePlay();
     void seekTo(int time);
 }
```

#### PlayMusicService.java

```
public class PlayMusicService extends Service {
     private MediaPlayer player;
     private Timer timer;
     @Nullable
     @Override
     public IBinder onBind(Intent intent) {
         return new MusicProxy();
     }
     @Override
     public void onCreate() {
         super.onCreate();
         player = new MediaPlayer();
     }
     public void play() {
         player.reset();
         try {
             player.setDataSource("http://192.168.188.41:8080//caonima.mp3");//设置网络资源
             player.prepareAsync();//设置异步准备设置异步准备
             player.setOnPreparedListener(new MediaPlayer.OnPreparedListener() {//设置准备监听器
                 @Override
                 public void onPrepared(MediaPlayer mp) {//当准备完成时候调用
                     player.start();
                     addTimer();
                 }
             });
         } catch (Exception e) {
             e.printStackTrace();
         }
     }
     private void addTimer() {
         final int totalTime = player.getDuration();// 获取歌曲总时长
         if (timer == null) {
             timer = new Timer();
         }
         timer.schedule(new TimerTask() {// Timer计时器，其实就是开启一个子线程执行一个任务，可以设置执行子线程的时间
             @Override
             public void run() {
                 int currentDuration = player.getCurrentPosition();
                 Message msg = MainActivity.handler.obtainMessage();
                 Bundle bundle = new Bundle();
                 bundle.putInt("total", totalTime);
                 bundle.putInt("current", currentDuration);
                 msg.setData(bundle);
                 MainActivity.handler.sendMessage(msg);
             }
         }, 5, 50);
     }
     public void seekTo(int time) {
         player.seekTo(time);
     }
     public void pause() {
         player.pause();
     }
     public void continuePlay() {
         player.start();
     }
     /**
      * 必须显式的释放音乐播放器资源，否则就算服务退出了，音乐也还是会被播放，所以应该将释放资源的代码放在 onDestroy 中
      */
     @Override
     public void onDestroy() {
         super.onDestroy();
         player.stop();
         player.release();
         player = null;
         if (timer != null) {
             timer.cancel();
             timer = null;
         }
     }
     class MusicProxy extends Binder implements MusicPlayerProxyInterface {
         @Override
         public void play() {
             PlayMusicService.this.play();
         }
         @Override
         public void pause() {
             PlayMusicService.this.pause();
         }
         @Override
         public void continuePlay() {
             PlayMusicService.this.continuePlay();
         }
         @Override
         public void seekTo(int time) {
             PlayMusicService.this.seekTo(time);
         }
     }
 }
```
