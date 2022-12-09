# Group.yml

{% hint style="success" %}
此文件仅在代理端可见（BungeeCord / Velocity）
{% endhint %}

```yaml
# Group name
Lobby:
  # Group display name
  displayName: "&aLobby"
  # Match rule
  # MORE_ONLINE
  # LESS_ONLINE
  # MOTD
  # MOTD_AND_MORE_ONLINE
  # MOTD_AND_LESS_ONLINE
  # MOTD_AND_RANDOM
  # RANDOM
  rule: "MORE_ONLINE"
  motd:
  - "Server Can Join"
  # delay match
  delay: 0
  # send unavailable server, only MOTD mode
  show-unavailable-server: false
  # Match pool
  servers:
    # Same as the proxy name
    lobby_1:
      # Display name
      displayName: "&aLobby #1"
      timeout: 2000
```

## groupName

Match group name. It corresponds to the `%queueName%` placeholder in `Gui.yml`

## displayName

The display name of the matching group.It corresponds to the `%group%` placeholder in the language file and the `%queueDisplayName%` placeholder in `Gui.yml`.

## rule

Match group rule, it determines how this match group works. It currently supports seven matching methods.

{% hint style="success" %}
But they follow a common principle: they will not match players with offline or full servers.
{% endhint %}

### MORE\_ONLINE

The server with the largest number of players is selected first, and one of them is randomly selected when there are the same number of players online.

### LESS\_ONLINE

The server with the least number of players is preferred, and one of them is randomly selected when there are the same number of players online.

### MOTD

Match against the server's Motd. Use this type of matching rule, `motd` is required.

{% hint style="info" %}
Most of the mini-game plugins support modifying the server's Motd according to the game state, these options can check your mini-game plugins.

It can also be used with some other plugins that modify Motd according to the game state.
{% endhint %}

### MOTD\_AND\_MORE\_ONLINE

On the premise that the Motd match is passed, the server with the largest number of players will be selected first, and one of them will be randomly selected when the number of online players is the same.

### MOTD\_AND\_LESS\_ONLINE

On the premise that the Motd match is passed, the server with the least number of players will be selected first, and one of them will be randomly selected when the number of online players is the same.

### MOTD\_AND\_RANDOM

On the premise that the Motd match is passed, randomly select a server that meets the requirements.

It differs from `MOTD` in that Motd will prefer a server until it is filled.And this rule chooses a random server every time.

### RANDOM

Randomly select any online server, random server will be selected every time.

## MOTD

{% hint style="info" %}
This option is only required for `MOTD`, `MOTD_AND_MORE_ONLINE`, `MOTD_AND_LESS_ONLINE`, `MOTD_AND_RANDOM` rules.
{% endhint %}

This option can be filled in more than one MOTD, only one MOTD needs to be met.

## delay

Artificial delays. Most matching operations take only a few milliseconds to complete. Some people hope that the matching time will not be too short, you can modify this value, the unit is second.

## show-unavailable-server

{% hint style="info" %}
This option is only required for `MOTD`, `MOTD_AND_MORE_ONLINE`, `MOTD_AND_LESS_ONLINE`, `MOTD_AND_RANDOM` rules.
{% endhint %}

By default, subservers that do not have Motd matches are not displayed in the Gui menu for subservers.

You can modify this option so that non-compliant servers are also displayed in the Gui menu.

## servers

Here you need to fill in all the servers that can be matched by this matching group. The server name is the server name in your BungeeCord/Velocity, not the IP address and port.

### displayName

The display name of the server. Corresponds to `%server%` in the language file and `%serverDisplayName%` in `Gui.yml`.

### timeout

Timeout when pinging the server. If the proxy server and sub-server are in the same LAN, it is recommended to set this value to 20-60. Not in the same LAN depends on the actual situation.

It is not recommended to set a value that is too high. Too high a value will cause the match to wait for a long time because a sub-server is offline.
