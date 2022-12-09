# 重载插件

{% hint style="success" %}
执行这些命令需要权限：BingQueue.admin
{% endhint %}

| 命令                          | 描述             |
| --------------------------- | -------------- |
| /bingqueue reload           | 重载代理端配置文件      |
| /bingqueue:bingqueue reload | 重载当前所在子服务器配置文件 |

## 重载命令可以重载什么？

它可以重载语言文件，但对于不同的服务端，也有不同的其他重载内容。

### BungeeCord / Velocity

* 重载 `Group.yml` 匹配组。

### 子服务器

* 重载 `Gui.yml` Gui 配置文件。
