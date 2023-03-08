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

Gui configuration files are stored in subserver folders named `Gui.yml`.

You can check it out in the configuration files section of this guide.
