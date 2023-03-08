# 使用 GUI 功能

{% hint style="info" %}
此功能需要子服务器也安装插件
{% endhint %}

<table spaces-before="0">
  <tr>
    <th>
      命令
    </th>
    
    <th>
      描述
    </th>
  </tr>
  
  <tr>
    <td>
      /queue \<Group Name> gui
    </td>
    
    <td>
      向代理端发送打开 Gui 请求
    </td>
  </tr>
  
  <tr>
    <td>
      /bingqueue:queue \<Group Name> gui
    </td>
    
    <td>
      向子服发送打开 Gui 请求
    </td>
  </tr>
  
  <tr>
    <td>
      /queue \<Group Name> server-gui
    </td>
    
    <td>
      向代理端发送打开地图选择器 Gui 请求
    </td>
  </tr>
  
  <tr>
    <td>
      /bingqueue:queue \<Group Name> server-gui
    </td>
    
    <td>
      向子服发送打开地图选择器 Gui 请求
    </td>
  </tr>
</table>

## 先决条件

如果你希望使用此功能，请确保需要使用菜单的服务器已经安装了 BingQueue。否则会出现执行命令后什么都没有发生的情况。

## 如何修改 Gui

Gui 的配置文件保存在了子服务器的文件夹中，以 `Gui.yml` 命名。

你可以在本指南的配置文件部分查看。
