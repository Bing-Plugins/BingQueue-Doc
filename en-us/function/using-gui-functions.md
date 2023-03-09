# Using GUI functions

{% hint style="info" %}
This feature requires the subserver to also have the plugin installed
{% endhint %}

<table spaces-before="0">
  <tr>
    <th>
      Command
    </th>
    
    <th>
      Description
    </th>
  </tr>
  
  <tr>
    <td>
      /queue \<Group Name> gui
    </td>
    
    <td>
      Send an Open Gui request to the agent
    </td>
  </tr>
  
  <tr>
    <td>
      /bingqueue:queue \<Group Name> gui
    </td>
    
    <td>
      Send open Gui request to child server
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

## Prerequisites

If you want to use this feature, please make sure that the server that needs to use the menu has BingQueue installed. Otherwise, nothing happens after the command is executed.

## How to modify Gui

~~【在 3.0 版本中移除】Gui 的配置文件保存在了子服务器的文件夹中，以 `Gui.yml` 命名。~~

~~你可以在本指南的配置文件部分查看。~~

主菜单保存在 main-gui 文件夹中，默认名称为 main.yml。地图选择器保存在 area-gui 文件夹中，默认名称为 area.yml。
