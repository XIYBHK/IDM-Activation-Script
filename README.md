# IDM 激活脚本
用于激活和重置 [Internet Download Manager](https://www.internetdownloadmanager.com/) 试用的开源工具

# 功能特性
* 使用注册表锁定方法冻结 IDM 试用和激活
* 安装 IDM 更新后激活和试用状态保持不变
* IDM 试用重置
* 完全开源
* 基于透明的批处理脚本

# 下载 / 如何使用 ⬇️
首先全新安装 [Internet Download Manager](https://www.internetdownloadmanager.com/)。确保已删除/卸载之前的破解/补丁（如果有）。
然后按照以下步骤激活。

# 方法 1 - PowerShell（推荐）

* 右键点击 Windows 开始菜单，选择 PowerShell 或终端（不是 CMD）。
* 复制粘贴以下代码并按回车
  ```bash
   irm "https://raw.githubusercontent.com/XIYBHK/IDM-Activation-Script/main/IAS.ps1" | iex
  ```

* 你将看到激活选项，按照屏幕提示操作。
* 完成。

# 截图 📸
![截图1](Screenshort/1.png)

![截图2](Screenshort/2.png)

# 说明 ℹ️
## 冻结试用 🥶
* IDM 提供 30 天试用期，你可以使用脚本中的此选项永久锁定此试用期，无需重置试用，试用期也不会过期。
* 此方法在应用该选项时需要网络连接。
* 可以直接安装 IDM 更新，无需再次冻结。

## 激活 ✅

* 此脚本使用注册表锁定方法激活 Internet Download Manager (IDM)。
* 此方法在激活时需要网络连接。
* 可以直接安装 IDM 更新，无需再次激活。
* 激活后，如果 IDM 出现激活提示，只需再次运行激活选项，无需使用重置选项。

## 重置 IDM 激活 / 试用 ®️
* Internet Download Manager 提供 30 天试用期，你可以使用此脚本随时重置激活/试用期。
* 如果 IDM 报告假序列号密钥或其他类似错误，此选项也可用于恢复状态。

## 系统要求
* 支持 Windows 7/8/8.1/10/11 及其服务器版本。
* PowerShell 运行 IAS 的方法支持 Windows 8 及更高版本。

## 高级选项
* 无值守模式激活：运行脚本时使用 `/act` 参数
* 无值守模式冻结试用：运行脚本时使用 `/frz` 参数
* 无值守模式重置：运行脚本时使用 `/res` 参数

# 工作原理
* IDM 将与试用和激活相关的数据存储在各种注册表键中。其中一些键被锁定以防止篡改，数据以特定模式存储以跟踪假序列号问题和剩余试用天数。为了激活它，此脚本通过在 IDM 中触发几次下载来生成这些注册表键，识别这些注册表键，并锁定它们，使 IDM 无法编辑和查看它们。这样 IDM 就不会显示使用假序列号密钥激活的警告。
