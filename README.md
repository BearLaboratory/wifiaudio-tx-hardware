<h1 align="center" style="font-size:50px;font-weight:bold">WiFiAudio</h1>
<p align="center">基于WiFi的语音传输系统</p>
<p align="center">
    <a href="https://github.com/">
        <img src="https://img.shields.io/badge/license-GPL-blue" alt="GPL License" />
    </a>
    <a href="">
        <img src="https://img.shields.io/badge/version-v1.0-green" alt="v1.0">
    </a> 
    <a href="https://github.com/BruceAKABear">
        <img src="https://img.shields.io/badge/author-dengyi-blueviolet" alt="Author">
    </a>
</p>


整个系统在组织下分为及个仓库，请根据个人的需求参考：
- [语音发射端硬件](https://github.com/BearLaboratory/wifiaudio-tx-hardware)
- [发射端固件](https://github.com/BearLaboratory/wifiaudio-tx-firmware)
- [接收端硬件](https://github.com/BearLaboratory/wifiaudio-rx-hardware)
- [接收端固件](https://github.com/BearLaboratory/wifiaudio-rx-firmware)
- [PC端接收服务](https://github.com/BearLaboratory/wifiaudio-rx-pc)
- [PCM5102A解码验证模块](https://github.com/BearLaboratory/esp32-pcm51202-audio-hardware)

整个系统所使用的到的工具；
- [EDA工具使用开源免费的Kicad](https://www.kicad.org/)
- [固件开发使用简单的Arduino](https://www.arduino.cc/)

# 1. WiFi Audio TX （基于WiFi的无线麦克风发射端硬件）


WiFi Audio项目的目的是DIY一个开源且便宜的无线麦克风，辅助自己在拍摄视频时的收音。项目有几个根本点：
- 软件键全开源，方便大家对软硬件部分进行针对性的修改；
- 整体成本尽量低，为了达到这个目的在硬件设计部分，我舍弃了很多锦上添花的硬件（比如屏幕）；
- 基于WiFi，由于我个人想让麦克风能接入网络，因此抛弃了传统的UHF转而投入了WiFi的怀抱，正巧这两年芯片价格飞涨唯一还算正常的是上来乐鑫的ESP32系列芯片，价格便宜功能强大具有WiFi及蓝牙功能，因此选择它作为我们麦克的核心处理芯片。

麦克风选择我直接抛弃了传统模拟麦克风，虽然价格便宜，但是其外围电路较复杂，电路对声音音质的影响较大，不适合我们DIY。麦克风我测试的有两款一个是inmp441另一款是ics43434，后者是前者的替代品拥有更高的信噪比，我个人十分推荐使用ics43434。当然还有其他麦克风，奈何我自己没有买来测试，如果有小伙伴有自行测试，请将测试结果反馈给我 <mail>dengyi@dengyi.pro</mail>

# 2. 如何自行打板

整个硬件部分已完整打板测试，如果你使用嘉立创下单助手，直接将gebber目录下压缩文件上传即可，我推荐板材厚度选择1,1.6厚度过大，平时自己焊接过程中加热较麻烦。

如果你使用嘉立创smt服务时，上传坐标文件及bom_lc bom清单即可，如果出现错误，你需要手动去调整原件的方向等，确保焊盘准确即可，bom本身无任何问题。

# 2. 如何上传固件

固件部分，请参考其他仓库。对于固件我都是使用arduino进行编写，因此你需要安装arduino IDE，然后克隆固件仓库，然后进行编译上传。

需要特殊说明：因为我想尽量控制设备成本，所以没有板载烧录电路。进行固件的烧写需要使用我之前开发的ESP系列芯片烧录工具，具体的信息请参见这个仓库[ESP系列芯片烧录工具](https://github.com/BearLaboratory/downloader)

# 3. 如何使用

对于如何使用这部分，我推荐大家反复观看我的项目视频。因为我个人精力有限，每次readme文档我都写的比较糙（虽然多次召集负责写readme的小伙伴，但是并未成功）
# 4. 其他

整个项目在GPL协议下开源，禁止商用，商用请联系<mail>dengyi@dengyi.pro</mail>。

组织下所有开源项目均为个人出于兴趣进行开发及维护，并没有任何盈利，所以在维护频率上可能有很大的延迟，如果小伙伴们有兴趣可以发送邮件到<mail>dengyi@dengyi.pro</mail>与我个人联系或参与到开发中。同时非常欢迎对我的视频频道进行点赞或者关注，[B站](https://space.bilibili.com/402729300),[知乎](https://www.zhihu.com/people/deng-yi-92-16/columns),[youtube](https://www.youtube.com/channel/UCXvLKESzLbINYVe9J8rXerQ)

硬件可以个人自行在嘉立创下单打板，如果需要成品请直接在咸鱼搜索用户**BLab大熊实验室**，由于是非职业卖家，快递费由系统自行计算我做不了主还请谅解。
