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

🤓 Example: There are 7 switches spanning seven different floors and they are interconnected together in a network. 

The first one will have this config:

`Switch# conf t`

`Switch(config)# hostname Switch-F1`

`Switch-F1(config)#`

To return to the default prompt, use `no hostname`global config command.

## Config psswd
-  To secure EXEC mode acces, enter this command: 
`Switch(config)# line console 0` 
Zero represents the first console interface
1. Specify the user EXEC mode psswd using the command:
`password`
2. Enable user EXEC access using the command: `login`

`Switch-F1# conf t`

`Switch-F1(config)# line console 0`

`Switch-F1(config-line)# password 1234`

`Switch-F1(config-line)# login`

`Switch-F1(config-line)# end`

`Switch-F1#`

-  To secure privileged EXEC access:
1. Use the `enable secret (here the password)`


`Switch-F1# conf t`

`Switch-F1(config)# enable secret 1234en`

`Switch-F1(config)# exit`

`Switch-F1#`

-  To secure VTY lines:
1. Enter line VTY mode using:
`line vty 0 15`
2. Specify the VTY psswd using: `password`
3. Enable VTY access using `login`


`Switch-F1# conf t`

`Switch-F1(config)# line vty 0 15`

`Switch-F1(config-line)# password 123VTY`

`Switch-F1(config-line)# login`

`Switch-F1(config-line)# end`

`Switch-F1#`

## Encrypt psswd

Security threat: Anyone can discover the psswds if they have access to the startup-config and running-config files, because they display most psswd in plaintext.
Solution: Encryptt all plaintext psswds using `service password-encryption`

`Switch-F1# conf t`

`Switch-F1(config)# service password-encryption`

`Switch-F1#`

Use `show running-config` to verify that they are now encrypted.

## Banner MSG

Banners are an important method for declaring that only authorized personnel should attempt to access.

To create use `banner motd# the message of this banner is ...`

`Switch-F1# conf t`

`Switch-F1(config)# banner motd# Authorized Access Only`


## Router Config

1. Naming

`Router(config)# hostname R1`

2. Secure privileged EXEC mode

`R1(config)# enable secret psswdR1en`

3. Secure user EXEC mode

`R1(config)# line console 0`

`R1(config-line)# password password`

`R1(config-line)# login`

4. Secure remote Telnet / SSH access

`R1(config-line)# line vty 0 4`

`R1(config-line)# password psswd R1remote`

`R1(config-line)# login`

`R1(config-line)# transport input {ssh | telnet}`

For my labs I prefer to use `transport input all


