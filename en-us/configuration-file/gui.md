# Gui.yml

{% hint style="success" %}
This file is only visible on child servers
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
  server:
    item: MAP
    name: "&a%serverDisplayName%"
    lore: |-
      &8%queueDisplayName%
      &7
      &7Current Player: &a%serverPlayerNum%&7 / &a%serverMaxPlayerNum%
      &7Current Status: &a%serverMotd%
      &7
      &eClick to Play
  unavailable-server:
    item: PAPER
    name: "&a%serverDisplayName%"
    lore: |-
      &8%queueDisplayName%
      &7
      &7Current Player: &a%serverPlayerNum%&7 / &a%serverMaxPlayerNum%
      &7Current Status: &a%serverMotd%
      &7
      &eClick to Play
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

## General item expression

Most items contain the following elements.

### slot

{% hint style="info" %}
Some items do not require this option, such as server icons.
{% endhint %}

The item's slot will determine where the item is placed.

### item

{% hint style="warning" %}
Wrong item ID will cause the plugin to report error.
{% endhint %}

Fill in the correct display items. Versions 1.12 and below can be queried through [here](https://helpch.at/docs/1.12/org/bukkit/Material.html), and versions 1.13 and above can be queried through [here](https://helpch.at/docs/1.19/org/bukkit/Material.html).

#### name

The name of the item.

### lore

The description information of the item.

## main-menu

The main menu is the page opened with `/queue <Group Name>gui`.It does not contain pages for subservers.

### rows

Number of lines in menu. Please make sure other items do not exceed the line count.

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

### server

可用且符合匹配条件的服务器，它支持使用占位符。

### unavailable-server

服务器可用，但不满足匹配条件。

### random

随机进入一张地图的选项，不同于匹配规则，此处为真随机。

### previous-page/next-page

上一页与下一页的按钮，支持页码占位符。
