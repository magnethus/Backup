---

copyright:
  years: 1994, 2018
lastupdated: "2018-05-31"

---
{:screen: .screen}
{:codeblock: .codeblock}
{:pre: .pre}
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 从同一数据中心内的一个 VSI 到另一个 VSI 的备份和复原

有时，您会希望将数据复原到同一数据中心内的其他服务器上。以下指示信息将帮助您完成此任务。这些步骤仅适用于非操作系统文件的文件级复原。要复原系统映像，请遵循 [Windows BMR](restoring-evault-bmr-system-volume-image.html) 指示信息。

此过程包括在第二个服务器上重新注册 EVault 代理程序以访问第一个服务器的 EVAult 位置，以及执行**从其他计算机复原**操作。


## 先决条件

- Server1 和 Server2 必须具有相同的操作系统。不支持跨平台复原。
- Server1 和 Server2 必须均已配置 EVAult 代理程序。要了解如何配置 EVault 代理程序，请单击[此处](index.html#configuring-evault-agent-in-webcc)
- Server1 的备份作业已在 Server1 EVault 位置生成了备份。

**注**：禁用这两台服务器上的所有调度任务以避免发生任何冲突。 

## 启动 Server2 的 WebCC

**注**：一定要使用 {{site.data.keyword.BluVPN}} 连接来访问 {{site.data.keyword.BluSoftlayer_full}} 专用网络，否则 WebCC 链接将不起作用。

1. 登录到 [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window}，然后单击主菜单中的**存储** > **备份**，以显示具有 EVault Backup 服务的服务器。 
2. 选择 Server2。单击指向右方的展开箭头以显示 WebCC 链接。
3. 单击 **WebCC 登录**，以在浏览器中启动 WebCC 客户机。

## 重新注册 EVault：
1. 单击**所有代理程序**，然后打开要修改的特定代理程序。
2. 单击**编辑**，然后选择“保险库设置”。
3. 单击**重新注册**以将 Server1 连接到 Server2。
4. 在**使用保险库概要文件**条目的**重新注册保险库**屏幕上，选择**输入保险库设置**。
5. 输入保险库名称，该名称与 Server1 的 EVault 名称相同。
6. 输入 Server1 的凭证以登录到 Server1 的 EVault。
7. 单击**装入计算机**，这将显示与保险库位置连接的服务器。
8. 单击**保存更改**。
9. 在出现提示时，单击**是**以确认重新注册 EVault。

## 在 Server2 上将 Server1 的备份作业作为复原作业运行

1. 单击**所有代理程序**。<br/> **注**：您可能需要刷新页面才能在 Server2 的**作业**选项卡下看到 Server1 上定义为可访问/已同步的作业
2. 将鼠标悬停在**高级**上，然后选择**从其他计算机复原**。
3. 在**从其他计算机复原**屏幕上，进行以下选择：
  - 保险库：此条目的缺省值应为 Server1 的 EVault
  - 计算机：选择 Server1 作为要从中进行复原的备份计算机。 
  - 作业：选择 Server1 中的备份作业。
4. 单击**下一步**
5. 确认源信息
  - **安全集合位置**应为 Server1 的保险库位置。
  - 在**选择备份版本**部分中，指定的备份版本应该是来自 Server1 的备份
  - 加密密码应该是在 Server1 上执行备份时使用的密码。
6. 单击**下一步**
7. 数据选择：选择需要从 Server1 备份复原的文件。选中要包含的文件和目录旁边的复选框，然后单击**包含**以保存您的选择。
8. 单击**下一步**以移至复原选项。
9. 在“选项”中：
  - 目标：选择**复原到原始位置**
  - 文件覆盖：选择**覆盖现有文件**
10. 单击**运行复原**。
11. “过程详细信息”屏幕上会显示复原作业的状态。


## 验证复原

1. 通过 SSH 连接到 Server2 的根目录。
2. 以长格式列出文件，包括所有目录条目。
  ```
  ls -la
  ```
  {: pre}
  
3. 对比输出。
  
## 恢复正常的备份调度。

1. 复原完成后，除去从中复原数据的 Server1 的注册信息。 
2. 输入当前 Server2 注册信息并启用调度任务。
 

  

 
 
  
  