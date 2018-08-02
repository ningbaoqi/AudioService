### AudioManager

|AudioManager常用的方法|说明|
|------|------|
|`adjustStreamVolumn(int streamType , int direction , int flags)`|调整手机指定类型的声音；其中第一个参数streamType指定声音类型，该参数可接受如下几个值：STREAM_ALARM：手机闹钟的声音；STREAM_DTMF：DTMF音调的声音；STREAM_NUSIC：手机音乐的声音；STREAM_NOTIFICATION：系统提示的声音；STREAM_RING：电话铃声的声音；STREAM_SYSTEM：手机系统的声音；STREAM_VOICE_CALL：语音电话的声音；第二个参数指定对声音进行增大还是减小，第三个参数是调整声音时的标签，例如执行FLAG_SHOW_UI：则调整声音时显示音量进度条|
|`setMode(int mode)`|设置声音模式，可设置的值有NORMAL、RINGSTONE、IN_CALL|
|`setRingerMode(int ringerMode)`|设置手机的电话铃声模式，可支持如下几个属性值：RINGER_MODE_NORMAL：正常的手机铃声；RINGER_MODE_SILENT：手机铃声静音；RINGER_MODE_VIBRATE：手机震动|
