### 音频接口类

|音频接口类|
|------|
|音乐类型的音频资源：通过[ＭediaPlayer](https://github.com/ningbaoqi/AudioService/blob/master/README-%EF%BC%ADediaPlayer.md)来播放|
|音调：通过ToneGenerator来播放|
|提示音：通过Ringtone来播放|
|游戏中的音频资源：通过SoundPool播放|
|录音功能：通过[ＭediaRecorder](https://github.com/ningbaoqi/AudioService/blob/master/README-%EF%BC%ADediaRecorder.md)和[AudioRecord](https://github.com/ningbaoqi/AudioService/blob/master/README-AudioRecord.md)等来记录音频||

|音频相关类|说明|
|------|------|
|[AudioManager](https://github.com/ningbaoqi/AudioService/blob/master/README-audiomanager.md)|通过音频服务，为上层提供了音量和铃声模式控制的接口，铃声模式控制包括扬声器、耳机、蓝牙等是否打开，麦克风是否静音等|
|AudioSystem|提供了定义音频系统的基本类型和基本操作的接口|
|[AudioTrack](https://github.com/ningbaoqi/AudioService/blob/master/README-AudioTrack.md)|直接为PCM数据提供支持|
|AudioRecord|音频系统的录音接口，默认的编码格式为PCM_16_BIT|
|Ringtone和RingtoneManager|为铃声、提示音、闹钟等提供了快速播放以及管理的接口，实质是对媒体播放器提供了一个简单的封装|
|[SoundPool](https://github.com/ningbaoqi/AudioService/blob/master/README-SoundPool.md)|能够播放音频流的组合音，主要被应用在游戏领域|
|android.media.audiofx包|android2.3新增的包，提供了对单曲和全局的音效的支持，包括重低音、环绕音、均衡器、混响、可视化等声音特效|
|AudioEffect|Android可以控制播放音乐时的均衡器、重低音、音场及显示音乐波形等|
