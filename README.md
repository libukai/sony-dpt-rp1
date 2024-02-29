# SONY DPT-RP1 折腾记录

随着编程学习进度的深入，发现阅读专业类书籍的需求越来越多，而且大多数的专业类书籍都至少是 A5 尺寸，这也对电子书的尺寸提出了更大的要求，毕竟尺寸太小连代码都看不完整。

从性价比的角度考虑，我选择了 SONY DPT-RP1 这款曾经的电子书王者，在破解之后即使在今天它依然是一款非常优秀的电子书阅读器。

SONY DPT-RP1 拥有 13.3 寸的电子墨水屏阅读器，屏幕分辨率为 1600x2200，支持触摸和手写笔，内置 16GB 存储空间，支持 Wi-Fi 和蓝牙连接。而它最大的优点，就是轻！轻！轻！它的重量只有 349g，比起其他的 13.3 寸电子书阅读器轻了很多，非常适合长时间手持式的沉浸式阅读。

## 准备工作

在开始折腾之前，需要准备一些工具和资料，我已经全部放到了 GitHub 上，可以在 [libukai/sony-dpt-rp1](https://github.com/libukai/sony-dpt-rp1) 中找到。

- ADB : 用于连接电脑和 DPT-RP1 的命令行工具，进行文件传输和命令操作， Mac 版本在 /platform-tools/ 目录下
- APP : 需要安装到 DPT-RP1 上的固件和软件，包括破解工具和系统增强工具，可以在 /su 目录下找到

## 固件破解

SONY DPT-RP1 的破解主要是为了解决它的一些限制，比如说它只能通过官方的软件进行书籍的传输，而且只支持 PDF 和 EPUB 两种格式，而且它的官方阅读软件也是非常难用的。

破解之后，它相当于是一个开放系统的 Android 平板，可以安装第三方的阅读软件，支持更多的格式，比如说看 ePub 的微信读书墨水屏版、看 PDF 的 KOReader 和看漫画的 Perfect Viewer，，而且可以通过 FTP 方式进行书籍的便捷传输。

目前可用的破解方法是在特定的机型上，通过刷入第三方的固件实现，具体的破解方法可以参考开源项目 [HappyZ/dpt-tools](https://github.com/HappyZ/dpt-tools)。事实上，淘宝商家标榜的专用解锁版，应该也是在这个版本的基础上做了一些二次开发后拿出来卖钱的。

以下是刷新固件以及获得超级权限的各个步骤的参考文档列表：

* [The Ultimate Rooting Guide](https://github.com/HappyZ/dpt-tools/wiki/The-Ultimate-Rooting-Guide)
* [The Upgrade Guide/Getting back su](https://github.com/HappyZ/dpt-tools/wiki/The-Upgrade-Guide#getting-back-su)
* [Install Special Xposed for DPT-RP1](https://github.com/HappyZ/dpt-tools/issues/191)

## 系统增强

在完成了破解以及安装权限管理软件之后，接下去需要安装五款系统增强软件，继续提升使用体验：

* E-ink Launcher：一个专门为 E-ink 屏幕设计的桌面软件，可以作为系统的默认桌面
* 手心输入法：最简洁的输入法，其中的魅族皮肤非常适合 E-ink 屏幕
* 按钮救星：简洁的快捷键功能，主要是增加“返回”和“主页”两个功能
* SkyOlin助手：和 Xposed 框架配合使用，调节软件 DPI，解决部分软件字体偏小的问题
* 文件管理器+： 一个简洁的文件管理器，支持 FTP 传输

## 阅读软件

终于进入到了最重要的环节，接下去我们要根据不同的场景，选择最适合的阅读软件。

* [微信读书墨水屏版](https://ink.qq.com/)：适合看 ePub 格式的书籍，比如说小说、文学类的书籍
* [Legado](https://github.com/gedoor/legado)：适合看来追网文，可以使用各种书源，在电子书上无比爽快的看网文
* [KOReader](https://koreader.rocks/)：适合看 PDF 格式的书籍，比如说专业类的书籍、技术类的书籍
* [Perfect Viewer](https://perfect-viewer.en.uptodown.com/android)：适合看漫画，持续多种格式，以及丰富的自定义排版选项
* [EinkBro](https://github.com/plateaukao/einkbro)：墨水屏专用浏览器，非常的简洁好用，可以用来和 Inoreader 配合看 RSS

以后的几款软件都有专属的 E-ink 版本，所以也不用到处去找什么漂白版了，直接使用最新的版本也能很好的适配 DPT-RP1  的硬件。

!!! TIPS " Perfect Viewer 的全屏设置"

    通过将 `设置` - `电子书格式设置` - `编辑颜色主题` - `背景图片` 的属性值改为 `背景颜色`（白色），可以将漫画图片之外的背景颜色改为白色，这样在阅读漫画的时候就能实现真正的全屏效果了。

## 学习工具

在专业书籍的阅读的过程中，经常会遇到一些生僻词汇，这时候就需要一个好用的词典软件，来帮助我们快速的查找词汇的释义。

建议使用 [Eudic](https://www.eudic.net/v4/en/app/eudic) 这个跨平台的词典工具，它在 DPR-DT1 上有三个非常大的优势：

* 可以和 KoReader 整合，实现即按即译的快速查词功能
* 可以使用第三方词典，根据自己的需求进行词典的定制
* 可以跨平台使用，将 DPT-RP1 上的生词同步到其他设备上进行复习
