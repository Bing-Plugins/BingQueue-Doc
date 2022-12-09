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

### R
