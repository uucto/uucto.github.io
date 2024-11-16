---
title: CTF-图片隐写那些事儿
date: 2024-11-15 21:26:39
tags: [misc]

---

# CTF-图片隐写那些事儿

## 1 steghide

分为windows和linux两个版本，（jpg隐藏信息）

Steghide是一种隐写程序，能够隐藏各种图像和音频文件中的数据。颜色方面的样本频率不会更改，主要是对jpg文件。

![](CTF-图片隐写那些事儿/2022-11-27-11-43-28-image.png)

steghide-0.5.1-win32.zip   已下载软件及其版本

以下是kali下使用方法：

![](CTF-图片隐写那些事儿/2022-11-27-11-46-30-image.png)

steghide爆破密码：

> 有些题目用steghide加密文件但是不给密码，此时就需要爆破，steghide本身并不支持爆破，需要一些其他的方法：[GitHub - Va5c0/Steghide-Brute-Force-Tool](https://github.com/Va5c0/Steghide-Brute-Force-Tool)

![](CTF-图片隐写那些事儿/2022-11-27-11-47-55-image.png)

## 2 stegdetect

Stegdetect主要用于分析JPEG文件，可以检测到通过JSteg、JPHide、OutGuess、Invisible Secrets、F5、appendX和Camouflage等这些隐写工具隐藏的信息（PS：我没用过）
Stegdetect通过统计测试来分析图像文件中是否包含隐藏内容；运行静态测试以判断隐藏的内容是否存在；尝试识别隐藏内容是通过哪个隐写工具嵌入的。

kali安装命令

![](CTF-图片隐写那些事儿/2022-11-27-12-08-09-image.png)

使用方法：

![](CTF-图片隐写那些事儿/2022-11-27-12-35-46-image.png)![](CTF-图片隐写那些事儿/2022-11-27-12-38-47-image.png)

## 3 outguess

OutGuess是一种通用的隐写工具，允许插入隐藏信息到数据源的冗余位中。

![](CTF-图片隐写那些事儿/2022-11-27-11-50-13-image.png)

![](CTF-图片隐写那些事儿/2022-11-27-11-50-30-image.png)

没有密码的则kali下使用

outguess -r avatar.jpg -t 1.txt

## 4 Stegsolve

一款ctf中常用的图形化工具，需要安装java环境，破解LSB算法、隐藏二维码等

![](CTF-图片隐写那些事儿/2022-11-27-12-02-32-image.png)

![](CTF-图片隐写那些事儿/2022-11-27-12-03-20-image.png)

青少年CTF训练赛--光头强小分队2

![](CTF-图片隐写那些事儿/2022-11-28-00-12-09-image.png)

![](CTF-图片隐写那些事儿/2022-11-28-00-16-21-image.png)

![](CTF-图片隐写那些事儿/2022-11-28-00-16-48-image.png)

![](CTF-图片隐写那些事儿/2022-11-28-00-24-18-image.png)

![](CTF-图片隐写那些事儿/2022-11-28-00-30-42-image.png)

![](CTF-图片隐写那些事儿/2022-11-28-01-12-16-image.png)

先做反转再添加1，同样能达到上面程序执行的效果：

![](CTF-图片隐写那些事儿/2022-11-28-01-11-44-image.png)

## 5 F5-steganography

![](CTF-图片隐写那些事儿/2022-11-28-01-19-26-image.png)

![](CTF-图片隐写那些事儿/2022-11-28-01-19-48-image.png)

## 6 Jphswin

一款图形化界面的JPHS隐写工具 [下载地址](https://pan.baidu.com/s/1n8rGiHew6U9bxoSAMTT7_w)（提取码：n9ao）
导入图片，加密就点hide输入密码（也可不用密码）然后save一下就好了，解密就点seek输入密码（也可能没密码）

![](CTF-图片隐写那些事儿/2022-11-28-01-33-35-image.png)

## 7 Zsteg（lsb隐写）

![](CTF-图片隐写那些事儿/2022-11-28-01-35-01-image.png)

![](CTF-图片隐写那些事儿/2022-11-28-01-35-47-image.png)

## 8 BlindWaterMark

盲水印脚本-python

![](CTF-图片隐写那些事儿/2022-11-28-01-38-22-image.png)

更多参考[CTF-图片隐写那些事儿 - 腾讯云开发者社区-腾讯云](https://cloud.tencent.com/developer/article/2069964)

## 9 silenteye隐写

![](CTF-图片隐写那些事儿/2022-11-28-01-39-52-image.png)

![](CTF-图片隐写那些事儿/2022-11-28-01-41-18-image.png)

## 10 exiftool（查看图片exif信息）

![](CTF-图片隐写那些事儿/2022-11-28-01-42-49-image.png)

![](CTF-图片隐写那些事儿/2022-11-28-01-43-01-image.png)

## 11 pngcheck （检查IDAT块_win）

![](CTF-图片隐写那些事儿/2022-11-28-01-49-16-image.png)

## 12 WebP（webp文件操作）

![](CTF-图片隐写那些事儿/2022-11-28-01-52-50-image.png)

![](CTF-图片隐写那些事儿/2022-11-28-01-53-19-image.png)

## 13 stegpy（支持多种文件加密）

此种加密支持对PNG、BMP、GIF、WebP和WAV格式加密，同时可以选择有无password

![](CTF-图片隐写那些事儿/2022-11-28-01-55-07-image.png)

![](CTF-图片隐写那些事儿/2022-11-28-01-55-28-image.png)

![](CTF-图片隐写那些事儿/2022-11-28-01-55-46-image.png)

用于解青少年CTF训练赛--光头强小分队2

![](CTF-图片隐写那些事儿/2022-11-28-01-56-16-image.png)

更多音视频隐写请：[Misc工具（22.7.6更） - Ga1@xy's W0r1d](http://www.ga1axy.top/index.php/archives/6/#12pngbmp)
