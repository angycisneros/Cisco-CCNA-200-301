
## There are two layered models that are used to describe network operations
✔️ Commonly used when referring to protocols at various layers. 

### OSI reference model
![OSI Model](/img/OSI-Model.png)

|**Layer**      | **OSI Model** |**Example Protocols**                     |**Description**                            |
|:--------------|:--------------|:-----------------------------------------|:------------------------------------------|
| L7            | Application   | HTTP, FTP, DNS, SNMP, Telnet, SMTP, POP3 | Network process to application            |           
| L6            | Presentation  | SSL, TLS (To SSH, SFTP, HTTPS)           | Data representation and encrytption       |
| L5            | Session       | NetBios, PPTP                            | Interhost communication                   |   
| L4            | Transport     | TCP, UDP                                 | End-to-end connections and reliability    |    
| L3            | Network       | IP, ARP, ICMP, IPsec                     | Path determination and logical addressing |
| L2            | Data Link     | PPP, ATM, Ethernet, Datagrams            | Physical addressing                       |
| L1            | Physical      | Ethernet, USB, Bluetooth, IEEE, 802.11   | Media, signal and binary transmission     |


🙊 Never forget L8 - User (It's a joke but very useful)

### TCP/IP reference model

|**Layer**      | **TCP/IP Model** |**Example Protocols**                     |**Description**                                                        |
|:--------------|:-----------------|:-----------------------------------------|:----------------------------------------------------------------------|
| L4            | Application      | HTTP, HTTPS, REST, FTP, SFTP, TFTP, DNS, SNMP, Telnet, SMTP, POP3, DHCPv4, DHCPv6, SLAAC, IMAP | Represents data to the user + encoding + dialog control               |           
| L3            | Transport        | Connection-Oriented;TCP <br>Connectionless: UDP</br> | Supports communication between various devices across diverse network |
| L2            | Internet         | IP: IPv4, IPv6, NAT <br>Messaging: ICMPv4, ICMPv6, ICMPv6 ND </br>Routing Protocols: OSPF, EIGRP, BGP                            | Determines the best path through the network                          |
| L1            | Network Access   | Data Link Protocols: Ethernet,WLAN <br>Address Resolution: ARP</br>| Controls the hardware devices and media                               | 



### OSI vs TCP/IP Model
![Diagrammatic comparison](/img/Comparasion-Model.PNG)

|**OSI Layer**  | **TCP/IP Model** |**Description**                                                        |
|:--------------|:-----------------|:----------------------------------------------------------------------|
| L5, L6, L7    | Application      | TCP/IP: Includes several protocols that provide specific functionality to a variety of end user applications. OSI are used as references for application software developers and vendors to produce applications that operate on networks.              |           
| L4            | Transport        | Describes general services and functions that provide ordered and reliable delivery of data between source and destination hosts|
| L3            | Internet         | Describes protocols that address and route messages through an internetwork  |
| L2, L1        | Network Access   | OSI defines routing standards and protocols and TCP/IP only describes the handoff from the internet layer to the physical network protocols      | 

