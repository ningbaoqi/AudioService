### SoundPool
+  如果应用程序经常需要播放密集、短促的音效，这时还用MediaPlayer就显得有些不合适了：

|MediaPlayer存在如下缺点|
|------|
|资源占用量较高，延迟时间较长|
|不支持多个音频同时播放|

+ Android还提供了SoundPool来播放音效，SoundPool使用音效池的概念来管理多个短促的音效,SoundPool使用了独立的线程来载入音乐文件，不会阻塞UI主线程的操作；例如它可以开始就加载20个音效，以后在程序中按音效的ID进行播放；SoundPool主要用于播放一些较短的声音片段，与MediaPlayer相比，SoundPool的优势在于CPU资源占用量低和反应延迟小，另外，SoundPool还支持自行设置声音的品质、音量、播放比率等参数；Android系统SoundPool提供了一个Builder内部类，该内部类专门用于创建SoundPool；从Android5.0开始，SoundPool的构造器被设置为过时的，因此推荐使用SoundPool.Builder来创建SoundPool对象；一旦得到了SoundPool对象后，接下来就可调用SoundPool的多个重载份额load()方法来加载声音了；

|SoundPool提供了如下4个load()方法|说明|
|-------|-------|
|int load(Context context , int resId , int priority)|从resId所对应的资源加载声音|
|int load(FileDescriptor fd , long offset , long length , int priority)|加载fd所对应的文件中从offset开始，长度为length的声音|
|int load(AssetFileDescriptor afd , int priority)|从afd所对应的文件中加载声音|
|int load(String path , int priority)|从path对应的文件去加载声音|

+ 上面4个方法中都有一个priority参数，该参数目前还没有任何作用，Android建议将该参数设置为1，保持和未来的兼容性；上面4个方法加载声音之后，都会返回该声音的ID，所以程序就可以通过该声音的ID来播放指定声音了；

|SoundPool提供的播放指定声音的方法|说明|
|-------|-------|
|int play(int soundID , float leftVolume , float rightVolume ,int priority , int loop , float rate)|该方法的第一个参数指定播放哪个声音，leftVolume、rightVolume指定左、右的音量；priority：指定播放声音的优先级，数值越大，优先级就越高；loop：指定是否循环，0为不循环，-1为循环；rate：指定播放的比率，数值可从0.5到2，1为正常比率|

+ 为了更好的管理SoundPool所加载的每个声音的ID，程序会使用`HashMap<Integer , Integer>`对象来管理声音；
