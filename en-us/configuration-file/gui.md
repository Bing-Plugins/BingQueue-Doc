# Gui.yml

{% hint style="success" %}
This file is only visible on child servers
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

## General item expression

Most items contain the following elements.

### slot

{% hint style="info" %}
Some items do not require this option, such as server item.
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

The title of the menu, supports color and placeholder.

### play

The effect is the same as `/queue <Group Name>`, and the matching is performed after clicking.

### server

Click to jump to the server selection menu `server-choose`.

### other

Extra items, support for custom items.

#### console-command

Execute commands as console, support placeholders.

#### player-command

Execute commands as a player, supports placeholders.

## server-choose

{% hint style="success" %}
Only parameters that do not duplicate `main-menu` are included here.
{% endhint %}

### slots

This is a list of slots for subserver items. The sub-server icons will fill in the positions in turn, and the excess content needs to be turned.

### match-server

Available and matching servers that support the use of placeholders.

### online-server

服务器可用，但不满足匹配条件，它支持使用占位符。

#### offline-server

离线服务器，它支持使用占位符。

### random

The option to randomly enter a map is different from the matching rules, here it is true random.

### previous-page/next-page

The buttons for the previous page and the next page support page number placeholders.
