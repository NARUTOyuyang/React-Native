# 讲述如何零基础学 React Native

## 前景：
>我知道当前很多`培训机构`打着`零基础教学`的广告去吸引新手，让 Ta 们花钱去学习；我不能说这机构没用，我能告诉大家的是：`没必要`；想知道`为什么`，请继续往下看。

1. 我就是从`达内培训`4个月出来的一个真正`零基础`的 WEB 前端程序猿，`不是计算机专业出身`甚至之前还是`教动感单车`和`街舞`的一个却又`偏爱画画`的90后`运动爱好者`。
1. 我相信我跨越的宽度应该很大了吧！那么我会从我的`第一视角`去总结出我在成为 IT 男以及学习`技术`包括 RN 遇到的各个`困境`；我不会和大家说在遇到各种各样的问题时，应该如果去处理和面对，我只告诉大家`我是怎么去度过的`。

>那么至今我遇到了哪些问题呢？

* 英语：`看英文文档，编译的时候各种报错看不懂`。
* 心态：`会遇见生无可恋，炸了的时候；甚至还会因为你自己菜而被人看不起`。
* 难学：`写不来，不知道怎么写，尤其是业务逻辑`。
* 易忘：`掌握的知识点，稍微过段时间，概念就模糊了`。
* 无助：`遇到问题，不知道怎么解决，没人能帮你解决`。

>我会把我所有的只要会的都写进来，只要我不挂，我会一直不间断更新；希望可以帮助到更多步入新手的小伙伴，因为我知道新手在职场上是很苦逼的。
>那么为了大家有问题可以更好的交流，以及互相学习和进步，提供QQ群：`631730313`（适合交流）；微信公众号：`阳少小老弟`（方便阅读以下知识点），希望大家可以互相督促，互相进步，在不久的将来都能在当前领域成为重量级人物！如果觉得好，请给个 `star` 支持下。

## 目录
* [React Native 模块](https://github.com/NARUTOyuyang/React-Native/blob/master/README#react-native-模块)

***
# React Native 模块
***
### 基础篇之环境搭建（Mac支持 IOS 和 Android，Windows 仅支持 Android，除非你开黑盒子什么之类的工具）：
>在 Windows 下搭建 React Native Android 开发环境：

1. 安装 `Chocolatey` ：它是一个 Windows 上的包管理器,使用Chocolatey 来安装软件的时候，需要以管理员的身份来运行命令提示符窗口, 如果你实在装不上这个工具，也不要紧。下面所需的python2 和 nodejs 你可以分别单独去对应的官方网站下载安装即可。
	* `@powershell -NoProfile -ExecutionPolicy Bypass -Command "iex ((new-object net.webclient).DownloadString('https://chocolatey.org/install.ps1'))" && SET PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin`
	
2. 安装 Python2：打开命令提示符窗口，使用 Chocolatey 来安装 Python2，目前不支持 Python 3
	* `choco install python2`
	
3. 安装 Node：打开命令提示符窗口，使用 Chocolatey 来安装NodeJS 。注意，目前已知 Node 7.1 版本在 Windows 上无法正常工作，请避开这个版本！
	* `choco install nodejs.install`
	
4. 安装 Yarn、React Native 的命令行工具（react-native-cli）:Yarn 是 Facebook 提供的替代npm的工具，可以加速 node模块的下载。React Native 的命令行工具用于执行创建、初始化、更新项目、运行打包服务（packager）等任务。
	* `npm install -g yarn react-native-cli`
	* 如果你遇到 EACCES : `permission denied`权限错误，可以尝试运行下面的命令（限linux系统）： `sudo npm install -g yarn react-native-cli`
	
5. 安装 Android Studio：React Native 目前需要 Android Studio2.0 或更高版本。Android Studio 包含了运行和测试React Native 应用所需的 Android SDK 和模拟器。
	* 除非特别注明，请不要改动安装过程中的选项。比如 Android Studio 默认安装了 `Android Support Repository`，而这也是 React Native 必须的（否则在react-native run-android 时会报 `appcompat-v7` 包找不到的错误）。
	* 确定所有安装都勾选了，尤其是`Android SDK和Android Device Emulator`。
	* 在初步安装完成后，选择 Custom 安装项：
	![](https://github.com/NARUTOyuyang/React-Native/blob/master/Img/constructImage/react-native-android-studio-custom-install-windows.png)￼
	* 检查已安装的组件，尤其是模拟器和 HAXM 加速驱动。
	![](https://github.com/NARUTOyuyang/React-Native/blob/master/Img/constructImage/react-native-android-studio-verify-installs-windows.png)￼
	* 安装完成后，在 Android Studio 的欢迎界面中选择Configure | SDK Manager。
	![](https://github.com/NARUTOyuyang/React-Native/blob/master/Img/constructImage/react-native-android-studio-configure-sdk-windows.png)￼
	* 在 SDK Platforms 窗口中，选择 Show Package Details，然后在 Android 6.0 (Marshmallow) 中勾选Google APIs、Android SDK Platform 23、Intel x86 Atom System Image、Intel x86 Atom_64 System Image 以及 Google APIs Intel x86 Atom_64 System Image。
	![](https://github.com/NARUTOyuyang/React-Native/blob/master/Img/constructImage/react-native-android-studio-android-sdk-build-tools-windows.png)￼
	* 在SDK Tools窗口中，选择 Show Package Details，然后在Android SDK Build Tools中勾选Android SDK Build-Tools 23.0.1。（必须是这个版本）
	![](https://github.com/NARUTOyuyang/React-Native/blob/master/Img/constructImage/react-native-android-studio-android-sdk-platforms-windows.png)￼
	
6. 配置 ANDROID_HOME 环境变量：确保 ANDROID_HOME 环境变量正确地指向了你安装的 Android SDK 的路径。打开控制面板 -> 系统和安全 -> 系统 -> 高级系统设置 -> 高级 -> 环境变量 -> 新建
	* 具体的路径可能和下图不一致，请自行确认。
	![android](https://github.com/NARUTOyuyang/React-Native/blob/master/Img/constructImage/react-native-android-sdk-environment-variable-windows.png)￼
	* 你需要关闭现有的命令符提示窗口然后重新打开，这样新的环境变量才能生效。
	
7. 安装最新的 [JDK](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
	* Android Studio 需要 Java Development Kit [JDK] 1.8或更高版本。
	
8. 创建项目
	* `react-native init Pis`
	
9. 运行 packager 进去工程目录
	* `react-native start`
	
10. 准备真机或者模拟机，运行 Android
 	* `react-native run-android`
 	
11. 调试 APP 
	* 菜单 reload js
	
>可能会遇到的问题：

* 找不到 sdk 或者无法正常化 sdk 路径：检查环境变量。
* failed to find target with hash string 'android-23' in: F:\Android_SDK：更新23版本的sdk。
* build成功后是红色的页面：没有连接服务器 `js server`，ip 地址+8081端口，比如：`192.168.255.227:8081`。
* 还有些不知名的错误：重新跑一遍，实在不行关掉所有的终端窗口，`重启再跑一遍`，就可能好了（因为windows上跑android就是会出现各种这样的情况，我也用这个办法解决了很多看不懂的错误），最终还不行的话，就拿错误信息去搜吧！

***
>在 Mac 下搭建 React Native Ios 和 Android 开发环境：

1. 安装 Homebrew：它是一个 Mac 系统的包管理器，用于安装NodeJS 和一些其他必需的工具软件。
	* `/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"`
	* 译注：在Max OS X 10.11（El Capitan)版本中，homebrew在安装软件时可能会碰到 /usr/local 目录。

2. 安装 Node：使用 Homebrew 来安装 Node.js。
	* `brew install node`
	
3. 安装安装 Yarn、React Native 的命令行工具（react-native-cli）:Yarn 是 Facebook 提供的替代npm的工具，可以加速node模块的下载。React Native的命令行工具用于执行创建、初始化、更新项目、运行打包服务（packager）等任务。
	* `npm install -g yarn react-native-cli`
	* 如果你看到 EACCES: permission denied 这样的权限报错，那么请参照上文的 homebrew 译注，修复 /usr/local目录的所有权：`sudo chown -R `whoami` /usr/local`
	
4. 安装 Xcode：React Native 目前需要 Xcode 7.0 或更高版本。你可以通过 App Store 或是到 Apple 开发者官网上下载。这一步骤会同时安装 Xcode IDE 和 Xcode 的命令行工具。
   * 	`brew install watchman`
   
5. 安装 Android Studio：React Native 目前需要 Android Studio2.0 或更高版本。Android Studio 包含了运行和测试React Native 应用所需的 Android SDK 和模拟器。
	* 除非特别注明，请不要改动安装过程中的选项。比如 Android Studio 默认安装了 Android Support Repository，而这也是React Native 必须的（否则在 react-native run-android 时会报 appcompat-v7 包找不到的错误）。
	* 安装过程中有一些需要改动的选项：选择 Custom 选项：
	![](https://github.com/NARUTOyuyang/React-Native/blob/master/Img/constructImage/react-native-android-studio-custom-install.png)￼
	* 勾选 `Performance` 和 `Android Virtual Device`
	![](https://github.com/NARUTOyuyang/React-Native/blob/master/Img/constructImage/react-native-android-studio-additional-installs.png)￼
	* 安装完成后，在 Android Studio 的启动欢迎界面中选择Configure | SDK Manager。
	![](https://github.com/NARUTOyuyang/React-Native/blob/master/Img/constructImage/react-native-android-studio-configure-sdk.png)￼
	* 在 SDK Platforms 窗口中，选择 Show Package Details，然后在 Android 6.0 (Marshmallow) 中勾选Google APIs、Android SDK Platform 23、Intel x86 Atom System Image、Intel x86 Atom_64 System Image 以及 Google APIs Intel x86 Atom_64 System Image。
	  ![](https://github.com/NARUTOyuyang/React-Native/blob/master/Img/constructImage/react-native-android-studio-android-sdk-platforms.png)￼
	* 在 SDK Tools 窗口中，选择 `Show Package Details` ，然后在 `Android SDK Build Tools` 中勾选 `Android SDK Build-Tools 23.0.1`。（必须是这个版本）
	![](https://github.com/NARUTOyuyang/React-Native/blob/master/Img/constructImage/react-native-android-studio-android-sdk-build-tools.png)￼
		
6. 配置ANDROID_HOME环境变量
	* 确保 ANDROID_HOME 环境变量正确地指向了你安装的 Android SDK 的路径。具体的做法是把下面的命令加入到~/.bash_profile 文件中：(译注：~表示用户目录，即/Users/你的用户名/，而小数点开头的文件在 Finder 中是隐藏的，并且这个文件有可能并不存在。
	* 打开和关闭隐藏文件的命令：
	  `defaults write com.apple.finder AppleShowAllFiles -boolean true ; killall Finder`
	  `defaults write com.apple.finder AppleShowAllFiles -boolean false ; killall Finder`
	  
	* 
	  1. 启动终端 Terminal
	     `~/.bash_profile`
	     `No such file or directory`
	  2. 进入当前用户的home目录
	     `输入cd ~`
	  3. 创建.bash_profile
	      `输入touch .bash_profile`
	  4. 编辑.bash_profile文件
	 		`输入open -e .bash_profile`
	 		`export ANDROID_HOME=~/Library/Android/sdk`
	  5. 保存文件，关闭.bash_profile
	  6. 更新刚配置的环境变量
	      `输入source .bash_profile`
7. 创建项目
  * `react-native init Pis`
8. 运行packager 进去工程目录
  * `react-native start`
9. 准备真机或者模拟机，运行 IOS
  * `react-native run-ios`
10. 调试 APP
  * `菜单 reload js`
