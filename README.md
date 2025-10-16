# XDS功率计连接ANT+码表教程

## 硬件清单

- Adafruit feather nrf52840 express

- ESP32 devkit c v4 （32D）

- 3.7v锂电池（给feather供电）

- *5v锂电池（给ESP32供电）*

- *ESP32电源扩展板*

ESP32的供电方式可以不必和我一样（我这里使用了5V电池是取决于我的电源扩展板），选择你适合的方式即可，**其余建议和我保持一致以提高成功率**

## 开发环境搭建

下载安装ArduinoIDE

给feather配置协议栈并修改相关库文件[ANT+设备开发指南 | 知者不言](https://neuronx.top/2025/09/25/ANT-%E8%AE%BE%E5%A4%87%E5%BC%80%E5%8F%91%E6%8C%87%E5%8D%97/)

## 烧录代码

[GitHub - 1wpc/PowerMeter_Arduino: XDSHacker function: XDS -&gt; nrf52840 -&gt; magene](https://github.com/1wpc/PowerMeter_Arduino)（feather）

[GitHub - 1wpc/xds_repeater](https://github.com/1wpc/xds_repeater)（ESP32）

## 使用方式

1. 先启动AD350的功率计，看到功率计绿灯闪烁即为启动成功（注意此时要确保功率计不要被任何设备连接）

2. 给ESP32上电

3. 给feather上电（看到蓝灯由闪烁变为常量即为正常）

**遵循以上步骤的顺序可以保证较大的成功率**

## 相关信息

喜德盛功率计的蓝牙服务为0x1828（Mesh Proxy Service）特征值为0x2A63（Cycling Power Measurement）

<img src="file:///E:/project/xdstutorial/d3c369fd352335afadc29b018a0c1bec.jpg" title="" alt="d3c369fd352335afadc29b018a0c1bec.jpg" width="409">

另外，用nrf52840直接连接喜德盛功率计收不到数据，暂时用ESP32中转一下，所以该系统还有优化的空间，最好是能用一个板子解决。


