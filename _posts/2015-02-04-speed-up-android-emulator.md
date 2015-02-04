---
published: false
---

## 让你的Android模拟器加速
最近在极客学院看到一篇教程，可以有效的提高安卓模拟器的速度。
只需要下载 [硬件加速执行管理器](https://software.intel.com/zh-cn/android)，并新建AVD为x86架构的模拟器即可。
<br/>
实际的体验，速度确实提升很多。
<br/>
关于Android Studio的两个小问题
1. 国内很多人下载Android Studio之后首次启动都会停在获取SDK的界面。这个问题只需要添加
	disable.android.first.run=true
这句到bin/idea.properties 即可。
2. 启动Android Studio有可能点击不了创建Android工程。这主要是Android SDK的路径配置问题。点击Configure->Project Defaults->Project Structure 设置好Android SDK的路径即可解决。





