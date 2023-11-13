# ESP32-3248S035Arduino Demo 3.5CTP 的编译及上传
## 前言
本教程主要是指导资料包关于Arduino Demo中的3.5寸电容触控屏例程的编译运行指导

有关 **ESP32-3248S035** 的资料包，请前往下载
[FZ5821A-3.5inch_ESP32-3248S035.zip](https://pan.baidu.com/s/1l0-mM-d07XuXz0gYd6AgHA?pwd=vcjd)

## 前置条件
在执行本例程前，请先确保已经成功执行 《ESP32-3248S035在Arduino IDE上的编译和上载》 中的例程


## 本教程所执行的Arduino Demo程序
程序：**LVGL_Arduino-3.5CTP-gt911**  
本程序位于资料包的位置如下：
>3.5inch_ESP32-3248S035\1-Demo\Demo_Arduino\3_4-7_3.5 LVGL_Arduino Capacitive touch\3_4-7_3.5 LVGL_Arduino Capacitive touch\LVGL_Arduino-gt911\LVGL_Arduino-3.5CTP-gt911
 ![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035arduino%20demo%203.5ctp%20%E7%9A%84%E7%BC%96%E8%AF%91%E5%8F%8A%E4%B8%8A%E4%BC%A0.md/28110117249371.png)

 
## 执行例程所需要的Arduino库
* lvgl           8.3.3 
* TFT_eSPI  2.4.61 
以上库经采用资料包中已经下好的库文件：库文件位置如下：
> 3.5inch_ESP32-3248S035\1-Demo\Demo_Arduino\libraries
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035arduino%20demo%203.5ctp%20%E7%9A%84%E7%BC%96%E8%AF%91%E5%8F%8A%E4%B8%8A%E4%BC%A0.md/401850517237238.png)

把库文件复制到Arduino的库文件夹里：
如果Arduino为默认配置，请复制到以下区域
> C:\Users\XXX\Documents\Arduino\libraries

如果库文件位置已经变更，请安装变更的位置放置
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035arduino%20demo%203.5ctp%20%E7%9A%84%E7%BC%96%E8%AF%91%E5%8F%8A%E4%B8%8A%E4%BC%A0.md/362273317242382.png)
放置示意图如下
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035arduino%20demo%203.5ctp%20%E7%9A%84%E7%BC%96%E8%AF%91%E5%8F%8A%E4%B8%8A%E4%BC%A0.md/546004017257866.png)

如果需要安装最新的库文件，也可以使用Arduino的库管理器搜索对应的库文件名进行下载，如下示意图举例lvgl库，TFT_eSPI库也是如此。
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035arduino%20demo%203.5ctp%20%E7%9A%84%E7%BC%96%E8%AF%91%E5%8F%8A%E4%B8%8A%E4%BC%A0.md/42711117246628.png)
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035arduino%20demo%203.5ctp%20%E7%9A%84%E7%BC%96%E8%AF%91%E5%8F%8A%E4%B8%8A%E4%BC%A0.md/222601017250073.png)

## 相关库底层配置文件替换
本文所运用到的库文件底层配置文件在资料包的，共有两个文件
> 3.5inch_ESP32-3248S035\1-Demo\Demo_Arduino\3_4-7_3.5 LVGL_Arduino Capacitive touch\3_4-7_3.5 LVGL_Arduino Capacitive touch\TFT_eSPI bottom layer replacement file\
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035arduino%20demo%203.5ctp%20%E7%9A%84%E7%BC%96%E8%AF%91%E5%8F%8A%E4%B8%8A%E4%BC%A0.md/93215017255368.png)

1. 关于**lv_conf.h**文件的放置位置 Arduino库文件根目录
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035arduino%20demo%203.5ctp%20%E7%9A%84%E7%BC%96%E8%AF%91%E5%8F%8A%E4%B8%8A%E4%BC%A0.md/526385117236609.png)
注：此文件不可放在其他位置，lvgl库文件里有指定，如果需要放在其他位置，请更改库文件（不建议）

2. 关于**User_Setup.h **文件的放置位置
> Arduino\libraries\TFT_eSPI\
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035arduino%20demo%203.5ctp%20%E7%9A%84%E7%BC%96%E8%AF%91%E5%8F%8A%E4%B8%8A%E4%BC%A0.md/321755817259049.png)

以上完成后就可以打开对应例程进行编译

## 编译和下载
先确认一下如下配置
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035arduino%20demo%203.5ctp%20%E7%9A%84%E7%BC%96%E8%AF%91%E5%8F%8A%E4%B8%8A%E4%BC%A0.md/262104222230945.png)
如下编译成功
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035arduino%20demo%203.5ctp%20%E7%9A%84%E7%BC%96%E8%AF%91%E5%8F%8A%E4%B8%8A%E4%BC%A0.md/237004622249371.png)


## 已知问题及处理方式
###  1.编译过程中出现找不到lv_demo.h文件
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035arduino%20demo%203.5ctp%20%E7%9A%84%E7%BC%96%E8%AF%91%E5%8F%8A%E4%B8%8A%E4%BC%A0.md/249281218231395.png)
* 检测lvgl库文件中是否含有这个文件
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035arduino%20demo%203.5ctp%20%E7%9A%84%E7%BC%96%E8%AF%91%E5%8F%8A%E4%B8%8A%E4%BC%A0.md/541080718247731.png)
* Mac系统上似乎会现在识别不到库文件里的这个文件，尝试把这个文件直接复制到例程的目录文件夹
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035arduino%20demo%203.5ctp%20%E7%9A%84%E7%BC%96%E8%AF%91%E5%8F%8A%E4%B8%8A%E4%BC%A0.md/309001018240865.png)
###  2.编译过程中出现找不到lv_cof.h文件
![](https://raw.githubusercontent.com/Jane-DIYmall/VNote-Image/main/%E9%A3%9E%E5%87%A1%E6%95%99%E7%A8%8B%E5%90%88%E9%9B%86/esp32-3248s035/esp32-3248s035arduino%20demo%203.5ctp%20%E7%9A%84%E7%BC%96%E8%AF%91%E5%8F%8A%E4%B8%8A%E4%BC%A0.md/573351218233899.png)
参考上方库底层配置文件的放置说明
