### ＭediaRecorder
+ 使用ＭediaRecorder实现录制音频和视频功能；使用MediaRecorder录制视频与录制音频的步骤基本相同，只是录制视频时不仅需要采集声音，还需要采集图像，为了让MediaRecorder录制时采集图像，应该在调用setAudioSource(int audio_source)方法时再调用setVideoSource(int video_source)方法来设置图像来源；

|ＭediaRecorder常用的方法|说明|
|------|------|
|setAudioEncoder(int audio_encoder)|设置刻录的音频编码，其值可以通过MediaRecoder内部类的MediaRecorder.AudioEncoder的几个常量：|
|||
