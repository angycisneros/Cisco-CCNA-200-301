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

Important! Keyword is a specific parameter defined & arg is not predefined

## First config command on any device: hostname

By default, there is a default name and it should be changed to sth more descriptive. 
Important naming guidelines:

    - Start with a letter
    - No spaces
    - End with a letter or digit
    - Use only letters, digits and dashes
    - Max 64 characters

Example: There are 7 switches spanning seven different floors and they are interconnected together in a network. 

The first one will have this config:

`Switch# conf t`

`Switch(config)# hostname Switch-F1`

`Switch-F1(config)#`

To return to the default prompt, use `no hostname`global config command.
