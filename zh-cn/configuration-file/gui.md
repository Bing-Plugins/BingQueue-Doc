# Gui.yml

{% hint style="success" %}
此文件仅在子服务器可见
{% endhint %}

```yaml
marks:
  - "         "
  - " 1111111 "
  - " 1111111 "
  - " 1111111 "
  - "         "
  - "         "

match-server:
  item: MAP

online-server:
  item: PAPER

offline-server:
  item: REDSTONE

random:
  slot: 40
  item: FIREWORK_ROCKET

previous-page:
  slot: 18
  item: ARROW

next-page:
  slot: 26
  item: ARROW

other:
  back:
    slot: 49
    item: ARROW
    console-command: []
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
