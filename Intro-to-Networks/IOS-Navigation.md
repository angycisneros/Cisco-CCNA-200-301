## How to navigate Cisco IOS to configure network devices


| Command mode         | Command mode                               | Description                        |
|:---------------------|:-------------------------------------------|:--------------------------------------------------------|
| `Switch>`  `Router>` | User Exec Mode       | Access to only a limited number of basic monitoring commands. For basic operations  |
| `Switch#`  `Router#` |Privileged EXEC Mode aka enable mode | Access to all commands and features. To execute configuration commands |


## How to configure the device

👉🏼 Must enter global config mode e.g. Switch(config)#
- There are two common subconfig modes:
    - Line config mode --> Console, SSH, Telnet
      - Example: `Switch(config)# line console 0`
      
    - Interface config mode --> Switch port or router network interface
      - Example: 
      `Switch(config-if)#` 

## Commands

| Concept        | Description                               |
|:---------------|:------------------------------------------|
| `enable`| To enter Privileged EXEC mode|
| `disable` |Back to user EXEC mode, or exit to a lower privilege level |
| `config t` |To config the switch, it's necessary get to global config |
| `exit` |To exit any config mode or close an active terminal and terminate the EXEC |
| `end` |Back to Privileged mode |
| Ctrl + Z | Same 👆🏼|


## General syntax for a command
`Switch>show ip protocols`
| Switch>      | Prompt            |
|:-------------|:------------------|
| show         | Command           |
| ` `          | Space             |
| ip protocols | Keyword or arg    |
