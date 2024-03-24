# HP Elite C1030 / x360 13c Chromebook Hackintosh
 <!-- About achieving the perfect hackintosh on the HP Elite C1030/x360 13c Chromebook models. -->
 在HP Elite C1030/x360 13c Chromebook机型上实现黑苹果。没时间写详细安装教程，简单说下思路，首先解锁刷bios（这个自行参考[Chromebook研究院](http://120.79.199.53?_blank)相关教程），目前统一官方Mrchromebox的定制BIOS，使用脚本`cd; curl -LO mrchromebox.tech/firmware-util.sh && sudo bash firmware-util.sh`
。另外也可以使用使用macOS定制版BIOS，使用脚本`cd; curl -LO ethanthesleepy.one/macos/firmware-util.sh && sudo bash firmware-util.sh。相关rom固件可以在BIOS文件目录里面下载。`。
 然后U盘用工具Etcher写入MacOS镜像安装包,[点击此处下载](https://pan.baidu.com/s/1rGgZaoxMyyI9a_P2qx_HOw?pwd=3ry8)。最后把EFI放入硬盘ESP分区，进行安装完成。
 MacOS安装的具体操作可参照[黑果小兵](https://blog.daliansky.net/Intel-NUC9-Hackintosh-and-macOS-Sonoma-Installation-Tutorial.html?_blank)。

---------------------------------------------------------------------------------------------------------------------------------------------------
 ### 加入交流群：112526282 <a target="_blank" href="https://qm.qq.com/cgi-bin/qm/qr?k=9YB2qnvcV8FmUcbwUdcN8gbmXPIAN8Rx&jump_from=webapi&authKey=UjdWQ0PVRv6OghQ69LT2wyokUfvKdFAQ7575jFsKyIIWYiQbYxIqxe+TUg2PKKQ1"><img border="3" src="Resources/group.png" alt="112526282" title="112526282"></a>
---------------------------------------------------------------------------------------------------------------------------------------------------

##  概况
#### 最佳仿制机型：MacBook Air（视网膜显示屏，13 英寸，2020 年）
<!-- ## |<img src="Resources/img1.png">|<img src="Resources/img2.jpg">| -->
---------------------------------------------------------------------------------------------------------------------------------------------------
| 关于本机 | 实拍图 |
|------------|-------------|
|<img src="Resources/img1.png" width="960">|<img src="Resources/img2.jpg" width="960">|

### MacOS版本(最新支持)：MacOS Sonoma (14.4)（推荐14，旧版自行更换wifi驱动）
### OpenCore版本(最新支持)：OpenCore 1.0.0
### CoreBoot版本(最新支持)：BIOS 4.22.2

### 基本硬件信息：
#### 惠普 Elite C1030/x360 13c Chromebook （JinLon）       
|            硬件 | 型号                                                                 | 
|---------------:|:---------------------------------------------------------------------|
|          处理器 | 英特尔 酷睿 i3-10110U / i5-10310U / i7-10610U                         |
|            内存 | 16GB（8GB x2）DDR4 2666MHz（板载）                                    |
|            硬盘 | 固态硬盘 128GB /256GB（可自行更换 NVMe 2230 2240，推荐西数SN740）        |
|            显卡 | 英特尔核芯显卡 UHD 620 / 630 / 655                                    |
|      无线 + 蓝牙 | 英特尔 AX201 无线网卡 (Wi-Fi 6 + 蓝牙 5.2)                            |
|            声卡 | 英特尔 SOF 音频 智音技术                                                            |
|          显示器 | 惠普 (13.5 英寸 1920*1280 分辨率)                                    |
---------------------------------------------------------------------------------------------------------------------------------------------------

### 完美计划进度->98%


| **功能**            | **状况**             | **说明**                                                                                             |
|--------------------|----------------------|-----------------------------------------------------------------------------------------------------|
| CPU睿频             | 正常                 | 已对CPU进行定制驱动，变频正常，性能最大化                                                                  |
| 电池/供电            | 正常                 | 支持65W快充，电池数据及相关传感器信息准确显示                                                              |
| 风扇                | 正常                 | 安装风扇控制器和EC驱动工具，可以实现风扇监测和手动/自动调度。                                                                      |
| 无线网络             | 正常                 | 连接稳定，连接wifi6速度正常，使用旧版系统自行更换旧版的无线网卡驱动[AirportItlwm.kext](https://github.com/OpenIntelWireless/itlwm/releases)                                                                            |
| 蓝牙                | 正常                 | 蓝牙5.2设备连接正常、稳定，AirPods系列耳机自带功能正常                                                      |
| 睡眠                | 正常                 | 睡眠质量不错，刷最新BIOS固件正常唤醒，可自行定义hibernatemode，推荐0                                                   |
| 键盘                | 正常                 | 美式标准按键，除Command位置不同和部分功能快捷键其他按键正常，可自行通过第三方App改键                                         | 
| 键盘背光             | 正常                 | 已经完美驱动，可6级调节，调节可以在设置→键盘，取消暗光自动可调出自感应模式。快捷键：`1.F8/F9` `2.Alt(目前为CMD键) + 亮度+(F6) 或 亮度- (F7) `                                                                |           
| 功能快捷键           | 正常                 | 全正常使用，完整功能完美重新映射，泰酷辣！                                                     |
| 触控板              | 正常                  | 点按、手势相关功能都正常使用，可在设置触控屏进行偏好设置                                                      | 
| 触摸屏              | 正常                  | 已正常驱动，使用体验还是挺不错的                                                         | 
| 核显                | 正常                 | 已定制最佳缓冲帧和显卡4G显存，激活H264和HEVC硬件加速，4K、HDR真彩流畅播放                                      |
| NVME固态硬盘         | 正常                 | 实测更换西数SN740固态后可直接免驱使用，可去掉`NVMeFix.kext`驱动，保证供电校正建议保留                                  |    
| HDMI/DP显示器       | 正常                  | 使用TypeC转DP或HDMI可正常连接4k显示器                                                                   |
| HDMI音频            | 正常                 | 正常使用，配合使用TypeC转DP或HDMI连接显示器， 显示器无外放可连音响                                            |                                      
| USB端口             | 正常                 | 已完美定制USB驱动和内建控制器，端口、蓝牙正常使用                                                            |
| 摄像头              | 正常                  | 正常免驱，同时快捷开关键正常使用，一键开关                                                                  |
| 注销/锁屏           | 正常                  | 正常，和原生MacOS无差别                                                                                 |
| 关机/重启           | 正常                  | 正常开关机和重启，同时注入不影响                                                                          |    
| HDPI                | 正常                | 因为1080p原生不支持，可以用`BetterDisplay`等HDPI软件来强开，并且会修复logo不一致问题，推荐1920x1280分辨率或者1600x1066                                                                      |
| 内置外放             | 禁用               | 声卡驱动`ChultraSOF.kext`测试阶段，魔改的螃蟹声卡驱动已集成EFI中。非魔改推荐使用蓝牙音响或耳机平替（如小米、小度便携智能音箱等等）                                                               |
| 3.5mm耳机接口        | 禁用               | 受声卡无法驱动影响，无法使用                                                                              |
| 内置麦克风           | 禁用               | 受声卡无法驱动影响，无法使用                                                                              |
| SD卡                | 禁用               | 目前暂时无法驱动，已禁用                                                                     |
| 指纹                | 禁用               | 目前暂时无法驱动，已禁用                                                                       |
---------------------------------------------------------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------------------------------------------
### 风扇控制器食用教程：
1.下载风扇控制器_.dmg并安装；</p>
2.下载ectool，存放本地任意目录；</p>
3.在当前目录打开终端，或者打开终端后切换到当前ectool所在路径；</p>
4.执行下面两段命令：</p>
`sudo cp ./ectool /usr/local/bin/ectool`</p>
`sudo chmod +x /usr/local/bin/ectool`</p>
5.再打开风扇控制器这个App即可正常食用啦~
---------------------------------------------------------------------------------------------------------------------------------------------------

---------------------------------------------------------------------------------------------------------------------------------------------------
### 注意事项：
1.安装完成后请自行使用OC工具进行更新三码，以保证后续正常食用</p>
2.不要随意改动EFI，关键补丁和驱动缺失，容易导致黑屏或加载不进系统</p>
3.类似模具也可以使用，比如Acer 713等CB本</p>
4.HP c1030商业版（LTE版）慎入，目前发现问题较多c
5.macOS13及之前版本自行更换无线网卡驱动</p>
6.未经允许禁止转载使用商业化，免费开源，需要注明出处！
---------------------------------------------------------------------------------------------------------------------------------------------------