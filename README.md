# hackintosh-efi-z7ct5na
OpenCore EFI for &lt;神舟z7ct5na> running macOS &lt;12-15>. Includes config, kexts and setup notes.
# 准备工作
## 需要一个u盘且大于16GB以上保证里面没有资料需要格式化
## 所需软件
[python](https://www.python.org/downloads/) 用于协助工具  
  [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) 用于生成机器码  
  [下载macOS恢复镜像](https://mirrors.dtops.co/ISO/MacOS/)  
  [DiskGenius](https://eassos.lanzoue.com/DG64Lite) 用于磁盘分区  
  [R-Drive Image](https://www.drive-image.com/) 恢复镜像使用  
  [ProperTree](https://github.com/corpnewt/propertree) 可视化编辑efi

# 开始阶段
下载ISO
使用 R-Drive Image 恢复镜像到u盘
只需把ISO恢复分区与efi引导分区恢复到u盘即可
再打开DiskGenius 替换efi分区的efi文件即可


# 更换三码
使用GenSMBIOS 生成机型三码
使用 ProperTree 替换信息
替换三码路径为 
PlatformInfo -> Generic 若找不到可 ctrl+f 搜索
· 生成出来的 Serial -> 填到 SystemSerialNumber
· 生成出来的 Board Serial -> 填到 MLB
· 生成出来的 SmUUID -> 填到 SystemUUID
· 机型名字 -> 填到 SystemProductName （填 MacBookPro16,1）

# 启动工作
开机界面狂按f2进入bios
设置u盘为启动项
选择Install macOS
进入恢复模式的情况下 触摸板无法点击的情况下使用触摸板下面的按键长按选择选项
使用tab键来选择选项 空格键表示确定

#注意事项
macOS15可能无法原生驱动Wi-Fi无线网卡
需要使用heliport 或者外置免驱的USB无线网卡
