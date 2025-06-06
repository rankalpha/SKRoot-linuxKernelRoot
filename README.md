# SKRoot - SuperKernelRoot - Linux内核级完美隐藏ROOT演示
新一代SKRoot，挑战全网root检测手段，跟面具完全不同思路，摆脱面具被检测的弱点，完美隐藏root功能，实现真正的SELinux 0%触碰，通用性强，通杀所有内核，不需要内核源码，直接patch内核，兼容安卓APP直接JNI调用，稳定、流畅、不闪退。
## 功能列表：
#### 1.测试ROOT权限
#### 2.执行ROOT命令
#### 3.执行原生内核命令
#### 4.安装部署su
#### 5.注入su到指定进程
#### 6.完全卸载清理su
#### 7.寄生目标APP

## 效果：
* **实验设备包括：红米K20\K30\K40\K50\K60、小米8\9\10\11\12\13、小米平板5\6、红魔5\6\7、联想、三星、一加、ROG2\3等，支持型号非常多。测试结果显示，SKRoot能够在所支持设备上非常稳定的运行。**
* **过市面上所有主流APP的ROOT检测，如农业XX、交X12XX3等...**
* **无需厂商提供源代码**
* **愿世界迎来一个美好的ROOT时代！**

![image](https://github.com/abcz316/linuxKernelRoot/blob/master/ScreenCap/1.png)
![image](https://github.com/abcz316/linuxKernelRoot/blob/master/ScreenCap/3.png)
![image](https://github.com/abcz316/linuxKernelRoot/blob/master/ScreenCap/4.png)

## 功能备注：
1. APP应用程序得到ROOT权限的唯一方法就是得到ROOT密匙，此密匙为48位的随机字符串，安全可靠。

2. 其中【**注入su到指定进程**】**只支持授权su到64位的APP**，老式32位APP不再进行支持，因市面上几乎所有APP都是64位，例如MT文件管理器、Root Explorer文件管理器等等。

## 使用流程：
1.将内核文件拖拽置`patch_kernel_root.exe`即可一键自动化流程补丁内核，同时会自动生成ROOT密匙。

2.编译并启动`PermissionManager`或者`testRoot`，输入ROOT密匙值，开始享受舒爽的ROOT环境。

## 更新日志：

2025-5：
  * **1.修复Linux 6.1、6.6及以上无法解析问题**
  * **2.新增内核隐藏su路径（防御安卓漏洞）**
  
2024-9：
  * **1.新增永久授权su功能**

2023-8：
  * **1.新增seccomp补丁代码**
  * **2.新增寄生目标功能**
  * **3.新增一键自动化流程补丁内核功能**
  * **4.修复Linux 3.X老内核兼容问题**
  * **5.修复Linux 5.10、5.15无法开机问题**

## 问题排查：
1、如遇到Linux 6.0以上内核无法开机，请阅读：
* **请不要使用Android.Image.Kitchen进行打包，该工具不支持Linux 6.0以上内核！**
* **可使用magiskboot进行打包。**
* **magiskboot的快速获取方式：使用7z解压Magisk apk，把lib文件夹里的libmagiskboot.so直接改名magiskboot即可使用。因为这是个可执行文件，并不是动态库，不要被名字带so字样所迷惑。**
* **解包命令：./magiskboot unpack boot.img**
* **打包命令：./magiskboot repack boot.img**

2、如发现第三方应用程序依然有侦测行为，请按照以下步骤进行排查：
* **内核必须保证是基于官方原版进行修改，而非自行编译或使用第三方源码编译。**
* **如果你曾经使用过Magisk，你应该先将手机完全刷机，因为Magisk可能会残留日志文件等信息。**
* **不要安装需要ROOT权限的工具，或涉及系统环境检测的应用，如冰箱、黑洞、momo和密匙认证等。这些应用的存在可能会被用作证据，推断你的设备已获取ROOT权限。以冰箱为例，这款应用需要ROOT权限才能运行，如果你的设备上安装了冰箱，那就可能被用来佐证你的设备处于ROOT环境。实际测试中我们发现，"X租号"APP就会进行此类环境检测。因此，我们强烈建议不安装这些工具。若确需使用，请在使用结束后立即卸载，以降低异常环境判断风险。**
* **Android APP应用可能会被检测其特征。这里我们仅提供APP调用的教学，在实际使用中，请尽量隐藏应用。可以考虑使用寄生功能，即将你的应用功能嵌入或附加到另一个无害或常见的应用内，这样可以有效地避免检测。如果这仍然不能满足隐藏的需求，你还可以考虑卸载应用，改用纯命令行方式调用的testRoot.cpp。**
* **在老旧版本的Android系统中，应用程序无需任何权限即可访问/data/local/tmp目录。在这种情况下，你应该升级Android系统版本，或者卸载SU。**
* **如果你的手机在解锁后会发出警报，你需要自行解决这个问题，因为它与SKRoot无关。**
* **检查应用程序是否在检测Bootloader锁，而不是ROOT权限。如果是这样，你应该安装SKRoot的隐藏Bootloader锁模块。**
* **请检查SELinux状态是否被恶意软件禁用。**
