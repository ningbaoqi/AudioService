### AudioEffect


|AudioEffect的子类|说明|
|------|------|
|AcousticEchoCanceler|取消回声控制器；只要调用其静态create()方法创建相应的实例，然后调用其的isAvailable()方法判断是否可用，再调用setEnabled(boolean enabled)方法启动相应效果即可|
|AutomaticGainControl|自动增益控制器；只要调用其静态create()方法创建相应的实例，然后调用其的isAvailable()方法判断是否可用，再调用setEnabled(boolean enabled)方法启动相应效果即可|
|NoiseSuppressor|噪声压制控制器；只要调用其静态create()方法创建相应的实例，然后调用其的isAvailable()方法判断是否可用，再调用setEnabled(boolean enabled)方法启动相应效果即可|
|BassBoost|重低音控制器；需要调用构造器来创建实例；创建实例时，同样需要传入一个audioSession参数，为了启动它，同样要调用AudioEffect基类的setEnabled(true)方法；获取BassBoost对象之后，可调用它的setStrenght(short strenght)方法来设置重低音的强度|
|Equalizer|均衡控制器；需要调用构造器来创建实例；创建实例时，同样需要传入一个audioSession参数，为了启动它，同样要调用AudioEffect基类的setEnabled(true)方法；Equalizer提供了getNumberOfPresets()方法获取系统所有预设的音场，并提供了getPresetName()方法获取预设音场的名称；获取Equalizer对象之后，可以调用它的getNumberOfBands()方法获取该均衡器支持的总频率数，再调用getCenterFreq(short band)方法根据索引来获取频率，当用户想为某个频率的均衡器设置参数值时，可调用setBandLevel(short band , short level)方法进行设置|
|PresetRevert|预设音场控制器；需要调用构造器来创建实例；创建实例时，同样需要传入一个audioSession参数，为了启动它，同样要调用AudioEffect基类的setEnabled(true)方法；获取PresetRevert对象之后，可调用它的setPreset(short preset)方法设置使用预设置的音场|
|Visualizer|示波器；需要调用构造器来创建实例；创建实例时，同样需要传入一个audioSession参数，为了启动它，同样要调用AudioEffect基类的setEnabled(true)方法；Visualizer对象并不用于控制音乐播放效果，它只是显示音乐的播放波形，为了实时显示该示波器的数据，需要为该组件设置一个onDataCaptureListener监听器，该监听器将负责更新波形显示组件的界面|

#### 启动取消回声功能的代码

```
AcousticEchoCanceler canceler = AcousticEchoCanceler.create(0 , mPlayer.getAudioSessionId());
if(canceler.isAvailable){
       //启动取消回声功能
       canceler.setEnabled(true);
}
```

#### 启动自动增益功能的代码

```
AutomaticGainControl ctrl = AutomaticGainControl.create(0 , mPlayer.getAudioSessionId());
if(ctrl.isAvailable()){
       //启动自动增益功能
       ctrl.setEnabled(true);
}
```

#### 启动噪音压制功能的代码

```
NoiseSuppressor suppressor = NoiseSuppressor.create(0 , mPlayer.getAudioSessionId());
if(suppressor.isAvailable()){
       //启动噪声压制功能
       suppressor.setEnabled(true);
}
```

#### 音乐的示波器、均衡、重低音和音场

![image](https://github.com/ningbaoqi/AudioService/blob/master/gif/pic-2.jpg)

![image](https://github.com/ningbaoqi/AudioService/blob/master/gif/pic-3.jpg)

![image](https://github.com/ningbaoqi/AudioService/blob/master/gif/pic-4.jpg)

![image](https://github.com/ningbaoqi/AudioService/blob/master/gif/pic-5.jpg)

![image](https://github.com/ningbaoqi/AudioService/blob/master/gif/pic-6.jpg)

![image](https://github.com/ningbaoqi/AudioService/blob/master/gif/pic-7.jpg)

![image](https://github.com/ningbaoqi/AudioService/blob/master/gif/pic-8.jpg)

![image](https://github.com/ningbaoqi/AudioService/blob/master/gif/pic-9.jpg)

![image](https://github.com/ningbaoqi/AudioService/blob/master/gif/pic-10.jpg)

![image](https://github.com/ningbaoqi/AudioService/blob/master/gif/pic-11.jpg)

![image](https://github.com/ningbaoqi/AudioService/blob/master/gif/pic-12.jpg)

![image](https://github.com/ningbaoqi/AudioService/blob/master/gif/pic-13.jpg)
