# 全网最全！Termux安装Kali全详细教程！包括常见错误，实现Kali VNC图形化，安装老版本镜像！

## 简介

### Termux

Termux 是一款运行于 Android 系统的开源终端模拟器。该软件提供了 Linux 环境，即使设备不具备 root 权限也可使用。通过自带的包管理器（Pacman、 APT），Termux 可以安装许多现代化的开发和系统维护工具，例如 zsh、Python、Ruby、NodeJS、MySQL 等软件。

![](https://i-blog.csdnimg.cn/direct/1008b2ceb7a447ba92b870ee02a463ca.png)

### Kali NetHunter

Kali NetHunter 是一个基于 Kali Linux 的适用于 Android 设备的免费开源移动渗透测试平台。

![](https://i-blog.csdnimg.cn/direct/1b37c0cd8b674598a5bd848c65862e3d.png)

Kali NetHunter 适用于未 root 设备（NetHunter Rootless）、具有自定义恢复的 root 设备（NetHunter Lite）以及具有自定义恢复且可使用 NetHunter 特定内核的 root 设备（NetHunter）。

Kali NetHunter 的核心包含在所有三个版本中，包括：

  * Kali Linux 容器，包含 Kali Linux 提供的所有工具和应用程序

  * Kali NetHunter 应用商店提供数十款专用安全应用程序

  * Android 客户端访问 Kali NetHunter 应用商店

  * Kali NetHunter 桌面体验 (KeX) 可运行完整的 Kali Linux 桌面会话，并支持通过 HDMI 或无线屏幕投射进行屏幕镜像




![](https://i-blog.csdnimg.cn/direct/870e1048b0284417bb0da990f293d269.png)

可以通过专用客户端应用程序或 Web 界面访问 Kali NetHunter App Store。

![](https://i-blog.csdnimg.cn/direct/3e199935e7c64f318fafc34d8d301718.png)

**两个 root 版本均提供附加工具和服务** 。自定义内核可以通过添加附加网络和 USB 小工具驱动程序以及为选定的 Wi-Fi 芯片提供 Wi-Fi 注入支持来扩展该功能。

![](https://i-blog.csdnimg.cn/direct/ffa83c691d764650958b0440bf76d27c.png)

除了 Kali Linux 中包含的渗透测试工具之外，NetHunter 还支持几个附加类别，例如HID 键盘攻击、BadUSB 攻击、Evil AP MANA 攻击等等。

NetHunter 可以安装在几乎所有的 Android 设备上，使用以下版本之一：

  * NetHunter Rootless：NetHunter 的核心适用于未 root 且未修改的设备
  * NetHunter Lite：完整的 NetHunter 软件包适用于没有自定义内核的 root 手机。
  * NetHunter：完整的 NetHunter 软件包，带有针对支持设备的自定义内核



## 安装Termux

### github安装

可以通过Termux的官方github的Release页面进行下载。

<https://github.com/termux/termux-app/releases>

可以使用最新版本。在展开Assets的三角小箭头，可以看到这里有很多的apk。可以根据自己的需求去选择一个apk安装。

  * arm64-v8a（64位 ARM 处理器）：适用于较新的安卓设备，尤其是 64 位 ARM 设备。
  * armeabi-v7a（32位 ARM 处理器）：适用于大部分较老的安卓设备。
  * x86（32位 Intel 处理器）：适用于少数搭载 Intel 处理器的安卓设备。
  * x86_64（64位 Intel 处理器）：适用于较新的搭载 Intel 处理器的安卓设备。
  * universal ：这是一个适配所有架构的版本，通常是包含多个架构的 APK，适用于各种设备。



**选择安装的 APK**

  * 如果你的设备是现代的安卓设备，并且使用的是 ARM 64位处理器，选择 termux-app_v0.118.1+github-debug_arm64-v8a.apk。
  * 如果你的设备是较老的 32位 ARM 设备，可以选择 termux-app_v0.118.1+github-debug_armeabi-v7a.apk。
  * 如果你不确定设备的架构，或者需要支持多个架构，建议选择 termux-app_v0.118.1+github-debug_universal.apk，它是一个通用版本，应该能够在大多数安卓设备上运行。



![](https://i-blog.csdnimg.cn/direct/2adfe2245a5548e6b8dd9a9e9236156e.png)

### F-Droid安装

可以通过F-Droid去下载Termux的安装包

<https://f-droid.org/en/packages/com.termux/>

![](https://i-blog.csdnimg.cn/direct/189b974c4fd74aa096a8f14c93c07041.png)

往下滑，我们可以在下面看到Termux的一些历史版本。最新的版本是 **0.119.0-beta.1 (1020)** ，更新于 2024-06-21。不过我不太建议下载，因为它是一个beta版。可能会有bug或不稳定。

建议下载版本 **0.118.1(1000)** ，点击下载APK，即可下载安装包。 

![](https://i-blog.csdnimg.cn/direct/b16fdda5f3194e2ca66446c36c1ad95a.png)

## **Kali NetHunter 应用商店**

可以下载安装 **Kali NetHunter App Store** 。

**Kali NetHunter 应用商店** 是一个可安装的 Android 应用程序目录，用于渗透测试和取证。客户端可让您轻松浏览、安装和跟踪设备上的更新。

也可以在 **Kali NetHunter App Store** 里面下载安装Termux **。**

<https://store.nethunter.com/>

![](https://i-blog.csdnimg.cn/direct/127d6a76509346e5b80118f70435ac63.png)

安装apk后是这样的。

![](https://i-blog.csdnimg.cn/direct/55ea7c6d8ae348509e49cb3dbd2faafc.png)![](https://i-blog.csdnimg.cn/direct/457fac477ba74dd49bb9d082463472d5.png)

## 安装Kali NetHunter

可以在未获取root权限的安卓设备上安装 **Kali NetHunter。**

### 先决条件

Android 设备（原装未修改设备，无需 root 或自定义恢复）

### 安装

可以通过NetHunter 商店安装 **Termux** 、 **NetHunter-KeX 客户端** 和 **Hacker 键盘。**

#### **Termux**

![](https://i-blog.csdnimg.cn/direct/23dad4f3badd4d6c88e4f33f50107304.png)

![](https://i-blog.csdnimg.cn/direct/0633fbfe49d34e7b8fbfe4e27d6ea5a1.png)

#### **NetHunter-KeX 客户端**

![](https://i-blog.csdnimg.cn/direct/02b8428111d64eeab5fb8f80959553db.png)

![](https://i-blog.csdnimg.cn/direct/873f7eee55554061817a305915ff0021.png)

#### **Hacker 键盘**

![](https://i-blog.csdnimg.cn/direct/c5ac5bcfcf9e4d788f42f2255290ee9f.png)

![](https://i-blog.csdnimg.cn/direct/eae21fade6224482bdcd28d8de859bc7.png)

打开Hacker‘s Keyboard，设置一下启用Hacker键盘

![](https://i-blog.csdnimg.cn/direct/2f0fd604bf5546d18256e9819a6a2b38.png)

![](https://i-blog.csdnimg.cn/direct/8d370167460546c484c93a367e49f654.png)

### 开始安装

**注意：建议全程开启代理，不然可能后面会出现报错导致安装失败。**
`curl -O --url https://ghproxy.top/https://github.com/luyuanbo793/luyuanbo/releases/download/%E8%84%9A%E6%9C%AC/install_nethunter_script.sh && chmod +x install_nethunter_script.sh && ./install_nethunter_script.sh`一键安装脚本

打开Termux，输入以下命令获取文件存储权限。
    
    
    termux-setup-storage

输入y回车确认

![](https://i-blog.csdnimg.cn/direct/96908d265fa0476bbc5aaa791e1c1eb5.png)

点击允许就获得权限了。

![](https://i-blog.csdnimg.cn/direct/8334d2f13b7e47418d5de33fc72b638e.png)

接下来更新Termux的包管理器。如果后面遇到暂停的选择，只需要按回车键默认就行。后面依次。
    
    
    pkg update

![](https://i-blog.csdnimg.cn/direct/97249352171048ecba4a3da99f65d0b6.png)

下载安装wget工具
    
    
    pkg install wget

![](https://i-blog.csdnimg.cn/direct/873d7c2b8dbb478e8a1e2a28f32b3025.png)

下载kali-nethunter安装包
    
    
    wget -O install-nethunter-termux https://offs.ec/2MceZWr

![](https://i-blog.csdnimg.cn/direct/11f2511d32b54e95bd459f1978072d98.png)

输入ls可以查看我们下载后的安装包
    
    
    ls

![](https://i-blog.csdnimg.cn/direct/f2f4f12b90a44eb788aa531b97955ec0.png)

我们给这个文件进行权限提升，然后再次查看。可以看到这个文件从原来的白色变成绿色，说明文件权限提升成功了。
    
    
    chmod +x install-nethunter-termux

![](https://i-blog.csdnimg.cn/direct/b7bbfe0aae6d46e9878628831bffe95d.png)

输入以下命令开始安装

**注意：这个过程最好建议挂代理下载。下载需要点时间。下载完的安装包有2GB，如果你下载很快的话，大概率没完全下载完毕，可能报错。会影响后面的安装。如果没下载完全的话可以重新运行以下命令。**
    
    
    ./install-nethunter-termux

![](https://i-blog.csdnimg.cn/direct/b2bbdfabc3de4f31936ba0050fbf0893.png)

输入命令后回看到这个界面，我们输入“ **1** ”后回车进行完整安装kali nethunter。 

![](https://i-blog.csdnimg.cn/direct/90eed1fd166642438226de70f2a87cbd.png)

可以看到在下载kali安装包中。

**注意：这里建议最好挂代理进行下载。不然可能下载不完整导致后面的步骤出现报错。**

![](https://i-blog.csdnimg.cn/direct/f1cd4270fd964b0698c8172629e90c8b.png)

安装完成后是这个样子的。安装包大约2GB。

![](https://i-blog.csdnimg.cn/direct/18e313c2285f495fabcdbb7567162fb4.png)

输入 **ls** 命令可以查看到多出来一个名为” **kali-nethunter-rootfs-full-arm64.tar.xz”** 的文件。并且显示2GB左右。

**如果你下载的时候很快的话。那大概率没下载完整。重新运行。确保你下载的安装包大概有2GB才是正确的。**
    
    
    ls -l

![](https://i-blog.csdnimg.cn/direct/6b9aa35507bf4f3da790ca7f492a991d.png)

接下来重新输入以下命令进行安装kali。
    
    
    ./install-nethunter-termux

同样的步骤输入“ **1** ”回车进行完整安装kali。

![](https://i-blog.csdnimg.cn/direct/0527e7c468b14fb0985cb6e1965fde23.png)

到这一步可以直接回车默认。大写的N就是默认的选项。这里的意思是存在的镜像已找到。是否删除并下载一个新的？

我们回车就是不删除我们刚刚下载好的镜像。这里保留着以后要是想重新安装kali就可以用这个镜像直接安装了，不需要重新下载。

![](https://i-blog.csdnimg.cn/direct/15d9761beecc4ba6abab30ef06345ed4.png)

这里就是在解压并安装镜像。 **这个过程非常久** ，取决于你的设备性能。

![](https://i-blog.csdnimg.cn/direct/12e2f7a0790f4ad29a0cb3767374f2a5.png)

这一步意思是是否删除 **rootfs** 文件？直接回车就是选择 **N** ，否。这样就不会删除这个文件了。

![](https://i-blog.csdnimg.cn/direct/ef0fa91aeb3d449699272079ee7affd1.png)

### **注意：如果出现如下图的情况，请跟着步骤来解决。经证实，2024版的 **安装脚本(install-nethunter-termux)** 会出现这个问题，老版本的不会出现这个问题。**
    
    
    [*] Configuring NetHunter for Termux ...
    chmod: cannot access 'chroot/kali-arm64/usr/bin/sudo': No such file or directory

![](https://i-blog.csdnimg.cn/direct/114ffb3fc7624a9ea981eb3a17354827.png)

通过ls命令可以看到我们当前有这些文件。我们需要创建一个名叫“ **chroot** ”的文件夹。并且把” **kali-arm64** “移动到“ **chroot** ”文件夹里面去。
    
    
    #创建chroot文件夹
    mkdir chroot
    #移动kali-arm64文件夹到chroot文件夹
    mv kali-arm64/ chroot/

![](https://i-blog.csdnimg.cn/direct/cb0bd79490664f9ab9c35969cb8bc456.png)

之后重新运行同样的命令完成安装。后面的步骤同上。都是直接回车默认。
    
    
    ./install-nethunter-termux

![](https://i-blog.csdnimg.cn/direct/9bdf40e6c55648a1b6af9ba25f658541.png)

出现这个界面就表示安装成功了。

![](https://i-blog.csdnimg.cn/direct/32aa3d08351e40f3bdd8a9c21332c470.png)

## 使用

### 1\. nethunter

启动 Kali NetHunter 命令行界面。

​​​​`nethunter`命令可以缩写为`nh。`
    
    
    nethunter 或 nh

![](https://i-blog.csdnimg.cn/direct/d49fbaf9f0854ba88b262c65d8474977.png)

出现这个界面就是进入kali的终端界面了。

在kali nethunter安装后首先运行以下命令以更新Kali
    
    
    #先输入nh进入kali终端
    nh 或 nethunter
    
    #更新kali
    sudo apt update && sudo apt upgrade -y
    
    #输入密码,密码是"kali",因为要用到root权限才能运行更新命令

输入exit退出kali终端。
    
    
    exit

![](https://i-blog.csdnimg.cn/direct/45ed11aad75240058db79e88e7101f22.png)

### 2\. nethunter kex passwd

配置 **KeX** 密码（仅在第一次使用前需要）。这个命令可以为后面实现 **kali图形化** 。
    
    
    nethunter kex passwd

要使用 **KeX** ，得设置一个密码，这里的" **Password"** 输入你想要设置的密码。输入密码时是不显示密码的位数的，这是正常的情况。

" **Verify** "是指验证。这里重新输入你刚才输入的密码，确保你两次输入的密码都是一样的。

最后这里提示是：您是否要输入只读密码 (y/n)？我这里输入“y“确认。密码同上。

![](https://i-blog.csdnimg.cn/direct/d42fde1c82a24ca49d45f698637523dc.png)

### 3\. nethunter kex &

启动 Kali NetHunter 桌面体验用户会话
    
    
    nethunter kex &

![](https://i-blog.csdnimg.cn/direct/0c024ef9f04b429dace0d948f12f3a1c.png)

### 4\. nethunter kex stop

停止 Kali NetHunter 桌面体验
    
    
    nethunter kex stop

![](https://i-blog.csdnimg.cn/direct/159f21044b5c4fa9902a9f9316bd6297.png)

### 5\. nethunter <command>

在NetHunter环境中运行命令

例如：在kali里面运行ifconfig命令查看网络状态信息等。
    
    
    nethunter ifconfig

![](https://i-blog.csdnimg.cn/direct/845c7eab4a584b578b2c929875dcbf50.png)

### 6\. nethunter -r

以 root 身份启动 Kali NetHunter cli
    
    
    nethunter -r

![](https://i-blog.csdnimg.cn/direct/4700646b9e7d42e88867203fdac86a2f.png)

### 7\. nethunter -r kex passwd

配置 root 的 KeX 密码，原理同 **nethunter kex passwd** 一样 **。**
    
    
    nethunter -r kex passwd

![](https://i-blog.csdnimg.cn/direct/83140d62a48845069ca0470749a59887.png)

### 8\. nethunter -r kex &

以 root 身份启动 Kali NetHunter 桌面体验
    
    
    nethunter -r kex &

![](https://i-blog.csdnimg.cn/direct/0bc8f6cc434c4ba6b0832c39b1656254.png)

### 9\. nethunter -r kex stop

停止 Kali NetHunter Desktop Experience 根会话
    
    
    nethunter -r kex stop

![](https://i-blog.csdnimg.cn/direct/0c50ed10918e4811a09c3579ba906d7b.png)

### 10\. nethunter -r kex kill

终止所有 KeX 会话
    
    
    nethunter -r kex kill

![](https://i-blog.csdnimg.cn/direct/2c41ead25d6e426aa208f72b8ab56069.png)

### 11\. nethunter -r <command>

以 root 身份在 NetHunter 环境中运行`命令`

`例如:查看passwd文件的内容`
    
    
    nethunter -r cat /etc/passwd

![](https://i-blog.csdnimg.cn/direct/238d1286636449b7b87bfbc1b992796e.png)

## 使用VNC工具实现Kali Linux图形化

确保你有上文提到的的VNC工具，或者其他的VNC工具。

![](https://i-blog.csdnimg.cn/direct/8269c5c189c54344bdae42a27eb2fe07.png)![](https://i-blog.csdnimg.cn/direct/030dd3fa06f046eebe1c0364ebeef61c.png)

### 这里我使用老版本的kali-nethunter镜像，2024版的有问题开启不了kex。后面会教如何下载老版本的kali-nethunter镜像。

### NetHunter Kex

通过上文提到的 **Kali NetHunter App Store** 应用商店下载。

我们先在Termux里面开启 **kex** 服务。如果你是第一次使用的话记得通过以下命令去设置好一个密码。在上文也提到怎么使用，这里不再叙述。
    
    
    nethunter kex passwd

![](https://i-blog.csdnimg.cn/direct/9ed16e9a52bd4de18e261ae8b6ce5c6a.png)在Termux里面开启kex服务。记住这里的端口号，后面会用到，每个人的可能都不一样。
    
    
    nethunter kex 

![](https://i-blog.csdnimg.cn/direct/e3abca7114994f408e05cebfeddcbe93.png)

之后挂着不要关闭Termux，打开NetHunter Kex，点击右上角的+号。

![](https://i-blog.csdnimg.cn/direct/0f328790acb447669cf3617fb826d3e7.png)

地址设置为127.0.0.1，修改端口号为5901，输入我们之前设置好的密码，点击右上角的保存图标。

![](https://i-blog.csdnimg.cn/direct/dcb616a2632044ef921b7f2d3adc05e5.png)

保存好后就会回到主页，此时可以看到我们刚刚设置好的VNC。

![](https://i-blog.csdnimg.cn/direct/b162a943fb2e43d4a0f71193bce36e16.png)

我们点击就可以打开kali-nethunter的图形界面了。

![](https://i-blog.csdnimg.cn/direct/1b96954a76e3405eb9b4474246ed0d77.png)

点击三个点的设置选项。点击切断就可以断开连接了。

![](https://i-blog.csdnimg.cn/direct/4bea3b6f4d4a446ab4cd517aa7b87cb0.png)

![](https://i-blog.csdnimg.cn/direct/e2094b179d6544019aa96d073e97bfac.png)

如何使用鼠标等操作请自行探索。这里不展开叙述。

![](https://i-blog.csdnimg.cn/direct/b91c66011970462f816e3cdae0e6e937.png)

### RVNC Viewer

我们使用第三方的VNC，我这里使用RVNC Viewer。方法也是一样。先在Termux里面开启kex服务。
    
    
    nethunter kex 

然后我们去打开RVNC Viewer。这里要求登陆，我们可以不用管，直接点击+号。

![](https://i-blog.csdnimg.cn/direct/ba98c7158aa241caad8b206402360e88.png)

这里我们地址Address写127.0.0.1:5901，名称Name可以随便起，我这里就写kali-nethunter。然后点击CREATE创建。

![](https://i-blog.csdnimg.cn/direct/a12d0cbdd2eb41d88bc6e943f5b08d01.png)

创建完成后我们来到这个页面。这里可以调整Picture quality(图像质量)，默认Automatic(自动)。可以自己设置。点击Connect（连接）。

![](https://i-blog.csdnimg.cn/direct/3bfb2b11a34b4884bc8fe1d9057e8194.png)

出现这个页面我们不用理会，点击右上角的OK按钮继续。

![](https://i-blog.csdnimg.cn/direct/d4b14a37c30f49ca960ecc3490744c28.png)

这里输入我们设置的密码，下面的Remember password(记住密码)可以开启，这样下次就不用再输入密码了。输入好密码后点击右上角的CONTINUE（继续）。

![](https://i-blog.csdnimg.cn/direct/969f83f70a844084be19d098ede25233.png)

之后我们就进入kali的图形化界面了。关于操作部分，请自行探索。建议画面质量调成High（高画质）比较好。

![](https://i-blog.csdnimg.cn/direct/e93f3b4511ea4ca191453e6ce17107dd.png)

## 额外：安装老版本kali-nethunter

这几天在写教程的时候也遇到了一些问题。安装和vnc这方面一直遇到阻力。特别是安装着一块。不论是换新旧版本的Termux，还是挂与不挂代理下载，都有问题。经过我这几天的实测。原来是安装脚本" **install-nethunter-termux** "出了问题。默认在获取脚本命令的时候它是会下载最新的安装脚本。即2024版的。

2024版的脚本安装会出现我上面写过的一个错误问题。并且运行kex也一直报错。老版本的就不会。

接下来教大家怎么安装老版本的脚本。

通过官方的仓库可以看到有多个历史版本的脚本。

[Files · main · Kali Linux / NetHunter / Build-Scripts / kali-nethunter-rootless · GitLab](https://gitlab.com/kalilinux/nethunter/build-scripts/kali-nethunter-rootless/-/tree/main?ref_type=heads "Files · main · Kali Linux / NetHunter / Build-Scripts / kali-nethunter-rootless · GitLab")

![](https://i-blog.csdnimg.cn/direct/c9206508bea84c8691945b45587f666b.png)

点击这里的main，可以看到一些历史版本的脚本。

![](https://i-blog.csdnimg.cn/direct/51adec3f8cbe47859079cd10fa68d2a6.png)

我演示使用的是2022.4版本的脚本，通过新旧版本的脚本对比，可以发现这里的版本和链接都不一样。

**2024.4版**

![](https://i-blog.csdnimg.cn/direct/f2a6bde44d0b499bbdd05dfcfb98f193.png)

**2022.4版**

![](https://i-blog.csdnimg.cn/direct/bc50e03f36c5453db57f067881a9d275.png)

### 安装

可以直接通过下载到本地，然后传到Termux。

点击这里下载到本地。一般都是下载到 **Download** 文件夹里面去。![](https://i-blog.csdnimg.cn/direct/ac0a6ece077641148e885ac14d4580a9.png)

![](https://i-blog.csdnimg.cn/direct/5047c98aec994405bf86adadb5919a68.png)

![](https://i-blog.csdnimg.cn/direct/a0c562f0940b44ef8fb051e29805f587.png)

![](https://i-blog.csdnimg.cn/direct/71729f60825d4ed19b88b1e85c925d68.png)

打开我们的Termux，把下载好的脚本移动到我们的Termux目录去。
    
    
    #查看当前的目录路径
    pwd
    
    #查看当前有哪些文件。这里可以看到storage文件夹。
    #需要通过termux-setup-storage命令去开启。不开启的话是没有这个文件夹显示的。
    ls
    
    #进入download文件夹目录
    cd storage/downloads
    
    #可以看到install-nethunter-termux脚本
    ls
    

![](https://i-blog.csdnimg.cn/direct/41b88b65a4b64fce8ae71a9f6b848c3b.png)

移动脚本到termux在home目录里面去。
    
    
    #移动脚本到主目录
    mv install-nethunter-termux /data/data/com.termux/files/home
    
    #回到主目录
    cd
    
    #查看当前文件
    ls
    

![](https://i-blog.csdnimg.cn/direct/2d8b6212d9dd4bbcae0f49bfe80f6c49.png)

### 修改代码

在我们使用前需要修改一下代码。不然直接运行是运行不了的。原因是老脚本用的还是老的下载链接。运行的话必会报404的错误，因为链接已经不存在了。所以我们需要去修改一下。

输入以下命令使用nano工具进行修改代码
    
    
    nano install-nethunter-termux

我们要修改一下链接。

![](https://i-blog.csdnimg.cn/direct/468f65dc26e14af39eb48a0944e28b17.png)

通过这个链接我们找到kali-nethunter的历史版本。

<https://kali.download/nethunter-images/current/rootfs/>

![](https://i-blog.csdnimg.cn/direct/6d1f4b990b464a0ca363836fcf5773b8.png)

不过我不下载2024版的，我下载的是2022.4版的kali-nethunter镜像。

通过这个链接可以查看到kali官方的历史版本镜像下载。

**注意这里的链接域名和上面的域名不一样的。都是官方的镜像，注意区分。**

[Index of /nethunter-images/](https://old.kali.org/nethunter-images/ "Index of /nethunter-images/")

![](https://i-blog.csdnimg.cn/direct/ef801696a33f4755a915ae4333a5ff73.png)

找到2022.4版本的镜像地址。我的架构是arm64的。当然你要找其他版本的也是同理。

[Index of /nethunter-images/kali-2022.4/rootfs/](https://old.kali.org/nethunter-images/kali-2022.4/rootfs/ "Index of /nethunter-images/kali-2022.4/rootfs/")

![](https://i-blog.csdnimg.cn/direct/13dbb861cd954e97bd044c2b354cb9ee.png)

回到Termux，进行链接地址的修改。

![](https://i-blog.csdnimg.cn/direct/856e05ae0d9548b4856062c63a512f22.png)

按 **Ctrl + O** 进行保存。提示是否写入到install-nethunter-termux，直接回车。

![](https://i-blog.csdnimg.cn/direct/5c70feea3f2e44729e6bbd6a3b8286cb.png)

接下来按 **Ctrl + X** 退出编辑。

![](https://i-blog.csdnimg.cn/direct/d041354583e54bacbe3453830fa365ed.png)

### 运行

运行以下命令进行运行，后面步骤就和上面的一样。
    
    
    ./install-nethunter-termux

![](https://i-blog.csdnimg.cn/direct/08dde0ef37834995bee00a507b3cb977.png)

可以看到开始在下载老版本的镜像了。

同理也可以使用这个2022.2的脚本去下载其他版本的kali-nethunter镜像。这里不再叙述。

## 总结

  1. 安装后第一件事运行 Kali 更新。如果您有足够的可用存储空间，您可能也希望运行。 
    
        sudo apt update && sudo apt full-upgrade -y 
    sudo apt install -y kali-linux-default

![wAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw==](https://img-home.csdnimg.cn/images/20230724024159.png?origin_url=data%3Aimage%2Fgif%3Bbase64%2CR0lGODlhAQABAPABAP%2F%2F%2FwAAACH5BAEKAAAALAAAAAABAAEAAAICRAEAOw%3D%3D&pos_id=jxrME0ZJ)

  2. 所有渗透测试工具都应该可以工作，但有些工具可能有限制，例如 **metasploit** 可以工作但没有数据库支持。
  3. 某些实用程序（如“ **top** ”）无法在未取得 root 权限的手机上运行。
  4. 非 root 用户仍然在 **chroot** 中具有 root 访问权限。这是 **proot** 的事情。只是要注意这一点。
  5.  **Galaxy** 手机可能会阻止非 root 用户使用 sudo。只需改用 “su -c” 即可。
  6. 通过停止所有 nethunter 会话并在 termux 会话中键入以下内容来执行 **rootfs** 的定期备份： 
    
        tar -cJf kali-arm64.tar.xz kali-arm64 && mv kali-arm64.tar.xz storage/downloads​​​​​​​

这会将备份放入您的 Android 下载文件夹中。注意：在较旧的设备上，将“ **arm64** ”更改为“ **armhf** ”



## 对新手朋友的建议

安装kali-nethunter花了我3天时间去研究，也是好不容易呀。真的好难。

最后是我想对新手朋友们说的话：

**真心不是很推荐使用手机去学习Kali Linux，如果你真想学的话，我还是建议使用电脑Kali Linux去学习，手机kali一般都是小白拿来装逼用。和电脑比的话当然差多了。我也是从一个小白懵懵懂懂一路走来，踩过了不少坑，所以我累积的经验也比较多。遇到问题我大部分都是靠自己解决的。请教他人当然也可以，重要的是要真的懂了才行。**

**扎实的基础加上永不放弃的精神，坚持才会有结果。就如kali linux的那句**

**“ The quieter you become,the more you are able to hear.”**