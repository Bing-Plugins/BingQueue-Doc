# Group.yml

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

但他们遵循一个共同的原则：不会让玩家匹配不在线，或者已经满员的服务器。

### MORE\_ONLINE

优先选择玩家数量最多的服务器，在线人数相同时随机选择其一。

### LESS\_ONLINE

优先选择玩家数量最少的服务器，在线人数相同时随机选择其一。

### MOTD

根据服务器的 MOTD 进行匹配。使用此类型的匹配规则，需要填写 `motd` 。

大多数的小游戏插件都支持根据游戏状态修改服务器的 MOTD，这些选项可以查看你的小游戏插件。

也可以配合一些其他根据游戏状态修改 MOTD 的插件。

### MOTD\_AND\_MORE\_ONLINE

在 MOTD 匹配通过的前提下，优先选择玩家数量最多的服务器，在线人数相同时随机选择其一。

### MOTD\_AND\_LESS\_ONLINE

