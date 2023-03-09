# 使用 GUI 功能

{% hint style="info" %}
此功能需要子服务器也安装插件
{% endhint %}

| 命令                                        | 描述                   |
| ----------------------------------------- | -------------------- |
| /queue \<Group Name> gui                  | 向代理端发送打开 Gui 请求      |
| /bingqueue:queue \<Group Name> gui        | 向子服发送打开 Gui 请求       |
| /queue \<Group Name> server-gui           | 向代理端发送打开地图选择器 Gui 请求 |
| /bingqueue:queue \<Group Name> server-gui | 向子服发送打开地图选择器 Gui 请求  |

## 先决条件

如果你希望使用此功能，请确保需要使用菜单的服务器已经安装了 BingQueue。否则会出现执行命令后什么都没有发生的情况。

## 如何修改 Gui

~~【在 3.0 版本中移除】Gui 的配置文件保存在了子服务器的文件夹中，以 `Gui.yml` 命名。~~

~~你可以在本指南的配置文件部分查看。~~

主菜单保存在 main-gui 文件夹中，默认名称为 main.yml。地图选择器保存在 area-gui 文件夹中，默认名称为 area.yml。
