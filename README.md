### 音频接口类

|音频接口类|
|------|
|音乐类型的音频资源：通过ＭediaPlayer来播放|
|音调：通过ToneGenerator来播放|
|提示音：通过Ringtone来播放|
|游戏中的音频资源：通过SoundPool播放|
|录音功能：通过ＭediaRecorder和AudioRecord等来记录音频||

|音频相关类|说明|
|------|------|
|AudioManager|通过音频服务，为上层提供了音量和铃声模式控制的接口，铃声模式控制包括扬声器、耳机、蓝牙等是否打开，麦克风是否静音等|
|AudioSystem|提供了定义音频系统的基本类型和基本操作的接口|
|AudioTrack|直接为PCM数据提供支持|
|AudioRecord|音频系统的录音接口，默认的编码格式为PCM_16_BIT|
