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

### server

Available and matching servers that support the use of placeholders.

### unavailable-server

The server is available, but does not meet the matching rule.

### random

The option to randomly enter a map is different from the matching rules, here it is true random.

### previous-page/next-page

The buttons for the previous page and the next page support page number placeholders.
