# Gui.yml

{% hint style="success" %}
此文件仅在子服务器可见
{% endhint %}

```yaml
#Main Menu
main-menu:
  rows: 4
  #%queueName% - Raw queue name
  #%queueDisplayName% - Display name of the queue
  title: "Play%queueDisplayName%"
  play:
    slot: 12
    item: RED_BED
    name: "&a%queueDisplayName%"
    lore: |-
      &7Play%queueDisplayName%
      &7
      &7
      &eClick to start playing
  server:
    slot: 14
    item: OAK_SIGN
    name: "&aMap Selector"
    lore: |-
      &7Choose a map to play in the map selector
      &7
      &eClick to view
  other: {}
server-choose:
  rows: 6
  slots:
    - 10
    - 11
    - 12
    - 13
    - 14
    - 15
    - 16
    - 19
    - 20
    - 21
    - 22
    - 23
    - 24
    - 25
    - 28
    - 29
    - 30
    - 31
    - 32
    - 33
    - 34
  #%queueName% - Raw queue name
  #%queueDisplayName% - Display name of the queue
  title: "%queueDisplayName%"
  #%serverName% - Raw server name
  #%serverDisplayName% - Display name of the server
  #%serverMotd% - MOTD of the server
  #%serverPlayerNum% - Now players number of the server
  #%serverMaxPlayerNum% - Max players number of the server
  match-server:
    item: MAP
    name: "&a%serverDisplayName%"
    lore: |-
      &8%queueDisplayName%
      &7
      &7Current Player: &a%serverPlayerNum%&7 / &a%serverMaxPlayerNum%
      &7Current Status: &a%serverMotd%
      &7
      &eClick to Play
  online-server:
    item: PAPER
    name: "&a%serverDisplayName%"
    lore: |-
      &8%queueDisplayName%
      &7
      &7Current Player: &a%serverPlayerNum%&7 / &a%serverMaxPlayerNum%
      &7Current Status: &a%serverMotd%
      &7
      &eClick to Play
  offline-server:
    item: REDSTONE
    name: "&a%serverDisplayName%"
    lore: |-
      &8%queueDisplayName%
      &7
      &7Current Status: &cOffline
  random:
    slot: 40
    item: FIREWORK_ROCKET
    name: "&aRandom Map"
    lore: |-
      &8%queueDisplayName%
      &7
      &aClick to play
  #%previousPageNum% - Previous page number
  #%nowPageNum% - Now page number
  #%nextPageNum% - Next page number
  previous-page:
    slot: 18
    item: ARROW
    name: "&aPrevious page"
    lore: |-
      &7Page Number: %previous-page%
  next-page:
    slot: 26
    item: ARROW
    name: "&aNext page"
    lore: |-
      &7Page Number: %next-page%
  other:
    back:
      slot: 49
      item: ARROW
      name: "&aReturn"
      lore: |-
        &7Return %queueDisplayName%
      console-command: [ ]
      player-command:
        - queue %queueName% gui

```

## 通用的物品表达方式

大多数的物品均包含以下元素。

### slot

{% hint style="info" %}
部分物品无需此选项，例如服务器图标。
{% endhint %}

物品的槽位，将决定此物品放在什么位置。

### item

{% hint style="warning" %}
错误的物品 ID 会导致插件报错。
{% endhint %}

填入正确的显示物品。1.12 及以下的版本可以通过[此处](https://helpch.at/docs/1.12/org/bukkit/Material.html)查询，1.13 及以上版本通过[此处](https://helpch.at/docs/1.19/org/bukkit/Material.html)查询。

#### name

物品的名称。

### lore

物品的描述信息。

## main-menu

主菜单，是使用 `/queue <Group Name> gui` 打开的页面。它不包含子服务器的页面。

### rows

菜单的行数。请确保其他物品不超出行数。

### title

菜单的标题，支持颜色与占位符。

### play

效果与 `/queue <Group Name>` 相同，点击后执行匹配。

### server

点击后跳转到服务器选择菜单 `server-choose`。

### other

额外的项目，支持自定义物品。

#### console-command

以控制台身份执行命令，支持占位符。

#### player-command

以玩家身份执行命令，支持占位符。

## server-choose

{% hint style="success" %}
此处仅包含与 `main-menu` 不重复的参数。
{% endhint %}

### slots

这是用于放置子服务器物品的槽位列表。子服务器图标将会依次填入其中的位置，超出的内容则需要翻页。

### match-server

可用且符合匹配条件的服务器，它支持使用占位符。

### online-server

服务器可用，但不满足匹配条件，它支持使用占位符。

#### offline-server

离线服务器，它支持使用占位符。

### random

随机进入一张地图的选项，不同于匹配规则，此处为真随机。

### previous-page/next-page

上一页与下一页的按钮，支持页码占位符。
