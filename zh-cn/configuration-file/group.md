# Group.yml

{% hint style="success" %}
此文件仅在代理端可见（BungeeCord / Velocity）
{% endhint %}

```yaml
# 组名称
Lobby:
  # 组展示名称
  displayName: "&aLobby"
  # 匹配规则
  # MORE_ONLINE 更多玩家优先
  # LESS_ONLINE 更少玩家优先
  # MOTD 根据 MOTD 匹配
  # MOTD_AND_MORE_ONLINE 根据 MOTD 匹配并人数最多优先
  # MOTD_AND_LESS_ONLINE 根据 MOTD 匹配并人数最少优先
  # MOTD_AND_RANDOM 根据 MOTD 匹配并随机选择
  # RANDOM 随机选择可用服务器
  rule: "MORE_ONLINE"
  motd:
  - "Server Can Join"
  # 延迟匹配上
  delay: 0
  # 发送不可用的服务器, 仅限 MOTD 模式
  show-unavailable-server: false
  # 匹配池
  servers:
    # 与代理端名称一致
    lobby_1:
      # 展示名称
      displayName: "&aLobby #1"
      timeout: 2000
```

## groupName

匹配组的名称。它对应 `Gui.yml` 中的 `%queueName%` 占位符

## displayName

匹配组的显示名称。它对应语言文件中的 `%group%` 占位符和 `Gui.yml` 中的 `%queueDisplayName%`占位符。

## rule

匹配组的规则，它决定了此匹配组是如何工作的。它目前支持七种匹配方式。

{% hint style="success" %}
但他们遵循一个共同的原则：不会让玩家匹配不在线，或者已经满员的服务器。
{% endhint %}

### MORE\_ONLINE

优先选择玩家数量最多的服务器，在线人数相同时随机选择其一。

### LESS\_ONLINE

优先选择玩家数量最少的服务器，在线人数相同时随机选择其一。

### MOTD

根据服务器的 Motd 进行匹配。使用此类型的匹配规则，需要填写 `motd` 。

{% hint style="info" %}
大多数的小游戏插件都支持根据游戏状态修改服务器的 Motd，这些选项可以查看你的小游戏插件。

也可以配合一些其他根据游戏状态修改 Motd 的插件。
{% endhint %}

### MOTD\_AND\_MORE\_ONLINE

在 Motd 匹配通过的前提下，优先选择玩家数量最多的服务器，在线人数相同时随机选择其一。

### MOTD\_AND\_LESS\_ONLINE

在 Motd 匹配通过的前提下，优先选择玩家数量最少的服务器，在线人数相同时随机选择其一。

### MOTD\_AND\_RANDOM

在 Motd 匹配通过的前提下，随机选择满足要求的服务器。

它与 `MOTD` 不同的是，Motd 会优先选择一个服务器，直至它被填满。而此规则每次都会选择随机的服务器。

### RANDOM

随机选择任意在线的服务器，每次都会选择随机的服务器。

## MOTD

{% hint style="info" %}
此选项仅限 `MOTD`、`MOTD_AND_MORE_ONLINE`、`MOTD_AND_LESS_ONLINE`、`MOTD_AND_RANDOM` 规则才需要进行填写。
{% endhint %}

此选项可以填写多个 MOTD，只需要满足其中一个 MOTD 即可。

## delay

人工延迟。匹配的操作大多数只需要几毫秒就可以完成。有的人希望让这个匹配时间不要太短，你可以修改此值，单位为秒。

## show-unavailable-server

{% hint style="info" %}
此选项仅限 `MOTD`、`MOTD_AND_MORE_ONLINE`、`MOTD_AND_LESS_ONLINE`、`MOTD_AND_RANDOM` 规则才需要进行填写。
{% endhint %}

默认情况下，子服务器的 Gui 菜单里是不会显示 Motd 不匹配的服务器。

你可以通过修改此选项，让不符的服务器也显示在 Gui 菜单中。

## servers

这里需要填写此匹配组能够匹配到的所有服务器。这里面的服务器名称为你的 BungeeCord/Velocity 中的服务器名称，而不是 IP 地址和端口。

### displayName

服务器的显示名称。对应语言文件中的 `%server%` 和 `Gui.yml` 中的 `%serverDisplayName%`。

### timeout

ping 服务器时的超时时间。如果代理服务器和子服务器在同一局域网，建议设置此值为 20-60。不在同一局域网根据实际情况而定。

不建议设置过高的值，过高的值会导致匹配因为某个子服务器掉线而等待过长时间。
