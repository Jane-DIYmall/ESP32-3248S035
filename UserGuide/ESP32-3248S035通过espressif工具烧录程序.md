# ESP32-3248S035通过espressif工具烧录程序

## 前言
本教程目的是展示如何通过**espressif工具**对**ESP32-3248S035**进行烧录
有关 **ESP32-3248S035** 的资料包，请前往下载
[FZ5821A-3.5inch_ESP32-3248S035.zip](https://pan.baidu.com/s/1l0-mM-d07XuXz0gYd6AgHA?pwd=vcjd)

## espressif工具准备
espressif工具：**ESP32 FLASH DOWNLOAD TOOL**

1.  资料包中的 **3.5inch_ESP32-3248S035\8-Burn operation\flash_download_tool_3.9.3**
2.  通过官网下载，下载链接[other-tools](https://www.espressif.com.cn/zh-hans/support/download/other-tools)
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035%E9%80%9A%E8%BF%87espressif%E5%B7%A5%E5%85%B7%E7%83%A7%E5%BD%95%E7%A8%8B%E5%BA%8F.md/315995523231393.png)
注意：本教程所使用的是资料包的烧录版本测试
## 烧录说明
1. 先确认 **ESP32-3248S035** 已经接到电脑上，并且驱动已经正常工作，如下图
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035%E9%80%9A%E8%BF%87espressif%E5%B7%A5%E5%85%B7%E7%83%A7%E5%BD%95%E7%A8%8B%E5%BA%8F.md/181994622255366.png)

注意：如果以上驱动没有自动安装，请在资料包的
 **3.5inch_ESP32-3248S035\7-Character&Picture_Molding_Tool** 路径下安装 **USB-SERIAL CH340.rar** 驱动
 
2. 双击打开ESP32 FLASHDOWNLOAD TOOL 烧录工具
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035%E9%80%9A%E8%BF%87espressif%E5%B7%A5%E5%85%B7%E7%83%A7%E5%BD%95%E7%A8%8B%E5%BA%8F.md/587015923242844.png)
3. 双击打开ESP32 FLASHDOWNLOAD TOOL 烧录工具，此步骤会弹出一个命令窗口，一个界面窗口，在界面窗口的 ChipType 选择**ESP32**，WorkMode 选择**Develop**，现在好后点击OK。
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035%E9%80%9A%E8%BF%87espressif%E5%B7%A5%E5%85%B7%E7%83%A7%E5%BD%95%E7%A8%8B%E5%BA%8F.md/542150000235730.png)
4. 选择后会进入如下界面，需要注意红框标注的进行设置，选择需要烧录的Bin文件，Bin文件在资料包的**\3.5inch_ESP32-3248S035\8-Burn operation\Burn files** ，设置烧录速度，设置SPI模式，此处需注意选择对应的COM口。以上对应选择后点击START开始烧录。
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035%E9%80%9A%E8%BF%87espressif%E5%B7%A5%E5%85%B7%E7%83%A7%E5%BD%95%E7%A8%8B%E5%BA%8F.md/143440700263294.png)
5. 点击开始，出现烧录中，烧录时间较短，请耐心等待。
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035%E9%80%9A%E8%BF%87espressif%E5%B7%A5%E5%85%B7%E7%83%A7%E5%BD%95%E7%A8%8B%E5%BA%8F.md/216980900245507.png)
6. 出现烧录成功标志后烧录成功，可以关闭烧录软件
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035%E9%80%9A%E8%BF%87espressif%E5%B7%A5%E5%85%B7%E7%83%A7%E5%BD%95%E7%A8%8B%E5%BA%8F.md/280175923233897.png)
7. 此次烧录的是**ESP32-3248S035**出厂程序，烧录后请按下开发板上的**RST**按键进行重启，查看是否烧录正确
