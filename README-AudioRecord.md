### AudioRecord
+ 使用AudioRecord刻录音频；

|AudioRecord的公共方法|说明|
|-------|-------|
|getAudioFormat()|返回设置的音频数据格式|
|getAudioSource()|返回音频录制源|
|getChannelConfiguration()|返回设置的频道设置|
|getChannelCount()|返回设置的频道数目|
|getMinBufferSize(int sampleRateInHz,int channelConfig,int audioFormat)|返回成功创建AudioRecord对象所需要的最小缓冲区大小；sampleRateInHz采样率；channelConfig音频通道设置；audioFormat：音频数据保证支持此格式|
|getNotificationMarkerPosition()|返回通知，标记框架中的位置|
|getPositionNotificationPeriod()|返回通知，更新框架中的时间位置|
|getRecordingState()|返回AudioRecord实例的录制状态|
|getSampleRate()|返回设置的音频数据样本采样率，单位为Ｈz|
|getState()|返回AudioRecord实例的状态|
|read(short[] audioData , int offsetInShorts,int sizeInShorts)|从音频硬件刻录缓冲区读取数据；audioData：写入的音频刻录数据；offsetInShorts:目标数组audioData的起始偏移量；sizeInShorts:请求读取的数据大小|
