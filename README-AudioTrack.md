### AudioTrack
+ 使用AudioTrack播放音频；

```
// 每秒8k个点，双声道，一个采样点16bit 2字节
int bufSize = AudioTrack.getMinBufferSize(8000, AudioFormat.CHANNEL_CONFIGURATION_STEREO, AudioFormat.ENCODING_PCM_16BIT);
AudioTrack trackPlayer = new AudioTrack(AudioManager.STREAM_MUSIC, 8000, AudioFormat.CHANNEL_CONFIGURATION_STEREO, AudioFormat.ENCODING_PCM_16BIT, bufSize, AudioTrack.MODE_STREAM);
trackPlayer.play();//开始
trackPlayer.write(bytes_pkg, 0, bytes_pkg.length);//往track中写数据
trackPlayer.stop();//停止播放
trackPlayer.release();//释放底层资源
```
