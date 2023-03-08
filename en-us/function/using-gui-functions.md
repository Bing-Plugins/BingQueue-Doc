# Using gui functions

{% hint style="info" %}
This feature requires the subserver to also have the plugin installed
{% endhint %}

| Command                            | Description                           |
| ---------------------------------- | ------------------------------------- |
| /queue \<Group Name> gui           | Send an Open Gui request to the agent |
| /bingqueue:queue \<Group Name> gui | Send open Gui request to child server |

## Prerequisites

If you want to use this feature, please make sure that the server that needs to use the menu has BingQueue installed. Otherwise, nothing happens after the command is executed.

## How to modify Gui

Gui configuration files are stored in subserver folders named `Gui.yml`.

You can check it out in the configuration files section of this guide.
