### SoundPool
+  如果应用程序经常需要播放密集、短促的音效，这时还用MediaPlayer就显得有些不合适了：

|MediaPlayer存在如下缺点|
|------|
|资源占用量较高，延迟时间较长|
|不支持多个音频同时播放|

+ Android还提供了SoundPool来播放音效，SoundPool使用音效池的概念来管理多个短促的音效,SoundPool使用了独立的线程来载入音乐文件，不会阻塞UI主线程的操作；例如它可以开始就加载20个音效，以后在程序中按音效的ID进行播放；SoundPool主要用于播放一些较短的声音片段，与MediaPlayer相比，SoundPool的优势在于CPU资源占用量低和反应延迟小，另外，SoundPool还支持自行设置声音的品质、音量、播放比率等参数；Android系统SoundPool提供了一个Builder内部类，该内部类专门用于创建SoundPool；从Android5.0开始，SoundPool的构造器被设置为过时的，因此推荐使用SoundPool.Builder来创建SoundPool对象；一旦得到了SoundPool对象后，接下来就可调用SoundPool的多个重载份额load()方法来加载声音了；
