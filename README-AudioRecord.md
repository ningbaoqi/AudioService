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
|read(byte[] audioData , int offsetInBytes , int sizeInBytes)|从音频硬件刻录缓冲区读取数据，读入缓冲区的总字节数；audioData：写入的音频刻录数据；offsetInBytes：audioData的起始偏移量，单位为Ｂ，sizeInBytes：读取的最大字节数|
|read(ByteBuffer bytebuffer , int sizeInBytes)|从音频硬件刻录缓冲区读取数据，直接复制到指定缓冲区，如果audioBuffer不是直接的缓冲区，此方法总是返回0；bytebuffer：存储写入音频录制数据的缓冲区；sizeInBytes：请求的最大字节数|
|release()|释放本地AudioRecord资源，对象不能经常使用此方法，而且在调用release()方法后，必须设置引用为null|
|setNotificationMarketPosition(int markerInFrames)|如果设置了setRecordPositionUpdateListener(OnRecordPositionUpdateListener)或setRecordPositionUpdateListener(OnRecordPositionUpdateListener listener,Handler)通知监听者设置位置标记|
|setPositionNotificationPeriod(int periodInFrames)|如果设置了setRecordPositionUpdateListener(OnRecordPositionUpdateListener)或setRecordPositionUpdateListener(OnRecordPositionUpdateListener ,Handler)通知监听者设置时间标记|
|setRecordPositionUpdateListener(AudioRecord.OnRecordPositionUpdateListener listener , Handler handler)|当之前设置的标记已经成立，或者周期录制位置更新时，设置处理监听者|
|setRecordPositionUpdateListener(AudioRecord.OnRecordPositionUpdateListener listener)|当之前设置的标记已经成立，或者周期录制位置更新时，设置处理监听者|
|startRecording()|表示AudioRecord实例开始进行录制|
