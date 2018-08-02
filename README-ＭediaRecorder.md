### ＭediaRecorder
+ 使用ＭediaRecorder实现录制音频和视频功能；使用MediaRecorder录制视频与录制音频的步骤基本相同，只是录制视频时不仅需要采集声音，还需要采集图像，为了让MediaRecorder录制时采集图像，应该在调用setAudioSource(int audio_source)方法时再调用setVideoSource(int video_source)方法来设置图像来源；

|ＭediaRecorder常用的方法|说明|
|------|------|
|setAudioEncoder(int audio_encoder)|设置刻录的音频编码，其值可以通过MediaRecoder内部类的MediaRecorder.AudioEncoder的几个常量：AAC、AMR_NB、AMR_WB、DEFAULT|
|setAUdioEncodingBitRate(int bitRate)|设置音频编码比特率|
|setAudioSource(int audio_source)|设置音频的来源，其值可以通过MediaRecorder内部类的MediaRecorder.AudioSource的几个常量来设置，通常设置的值MIC，来源麦克风|
|setCamera(Camera a)|设置摄像头用于来刻录|
|setOutputFormat()|设置输出文件格式;其值可以通过MediaRecord内部类MediaRecorder.OutputFormat的一些常量字段来设置，比如一些3pg(THREE_GPP)、mp4(MPEG4)等|
|setOutputFile(String path)|设置输出文件的路径|
|setVideoEncoder(int video_source)|设置视频的编码格式，其值可以通过MediaRecorder内部类的MediaRecorder.VideoEncoder的几个常量：Ｈ263、Ｈ264、MPEG_4_SP设置|
|setVideoSource(int video_source)|设置刻录视频来源，其职可以通过MediaRecorder内部类MediaRecorder.VideoSource来设置，比如可以设置刻录视频来源为摄像头：CAMERA|
|setVideoEncodingBitRate(int bitRate)|设置编码的比特率|
|setVideoSize(int width , int height)|设置视频的大尺寸|
|setVideoFrameRate()|所录制的视频编码格式，编码位率，每秒多少帧等，这些参数可以控制所录制的视频品质，文件大小，一般来说，视频品质越好，视频文件越大|
|setPreviewDisplay(Surface sv)|设置使用哪个SurfaceView来显示视频预览|
|start()|开始刻录|
|prepare()|预期做准备|
|stop()|停止|
|release()|释放该对象的资源|

[录制生活短片](https://github.com/ningbaoqi/AudioService/blob/master/README-%EF%BC%ADediaRecorder1.md)
