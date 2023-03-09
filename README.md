# Sagemcom F@st 5370e | <small>TeliaCompany AB</small>
<p align="center">
  <img src="https://user-images.githubusercontent.com/26827453/202126278-d97264f9-64a4-461e-a97b-fc7daec40487.png" /><br>
 </p>

### Small notice for all TeliaSonera AB customers:

Have you received a Sagemcom F@st 5370e from TeliaSonera 2022/2023 or later, this small intro notice is for you (2023-03-09)

TeliaSonera AB is offering this router for customers still but it is not exactly the same board as earlier, the two differnet versions looks *exactly* the same on the outside but it's not the same board as before on the current Sagemcom F@st 5370e routers.. The new board looks different and have disable serial console so it' s not possible to connect as I show in this readme on the new boards, the only message you will see is "GO!" if you connect to serial console on the pins as before when we boot the device. 

You can see the difference in two ways of the earlier verison and current version of this router.

Either by disassemble the router and (it is unnecessary if you are not an expert, in which if you are and find something awesome that can help us all please share your find, however the other way is you can compare the old/new board except under the "alliumnium" shell and contact that is gone, is the number on board. If you look really really close you will see the new board is written as "V3.2" with gold color on the hw board

In addition to the serial console, they have removed the contact I have shown in this repo (located at the bottom of the page where you can see that there are contacts under the allumium shell) and the "new" version does not use http://192.168.1.1/2.0/gui , they moved back to http://192.168.1.1/1.0/gui but with very limited settings. Besides all these "hardware changes" on the new board it is almost the same as the old version, that means all commands in this repository still works on latest board: 2023 from TeliaSonera AB, that's all for now.

And btw.

Just fyi, I searched around the web for find some info about all this mystery and they really not want to share their code so let me share all what I can tie to telia > sagemcom, they are under a pack called "C1".. It is some old verison I think, same as Tele2/Comhem uses for COAX(they are all exposed on the web btw)

```
Details Pack Telia C1
Pack Telia C1
Consult the EU declaration of conformity for the Pack Telia C1 Gateway on the Sagemcom official support website
Details Pack Telia C1\n\nConsult the EU declaration of conformity for the Pack Telia C1 Gateway on the Sagemcom official support website.\n\n\n\nDiscover all product
```

Also I found this

```
DCIW387 UHD GET / DCIW387 UHD TELIA
https://46.105.164.134/fr/decodeurs-son/dciw387-uhd-get-dciw387-uhd-telia?language_content_entity=fr
../../en/set-top-boxes-and-sound-products/dciw387-uhd-get-dciw387-uhd-telia
https://46.105.164.134/en/gateways/pack-telia-c1?language_content_entity=en
https://46.105.164.134/sites/default/files/2021-09/UE-2021-1571_DOC_PACK%20TELIA%20C1_253900775_20210720.pdf
```

AND FINALLY

```
haut-debit/fst-5370e-telia-wifi-router
..... but not much info, just
https://46.105.164.134/sites/default/files/2021-06/UE-2021-1369_Telia%20WiFi%20router%20F%40st%205370e_253760395.pdf
```

It was signed 2021-06. So I guess the new board is from early 2022.

That's all I know for now about thew new board. I may update this repo later if I find somehing usdeful, this was just for help new customers/users of telia


## Sagemcom Fast 5370e 

Firmware `v3.42.3` was sent to all customers that has this router worldwide (`Sagemcom` Models Affected: `57**x`)

!!! Info "License Info"
    This wiki and **all** scripts that will be added under this repo has been made by wuseman and is licensed under GPL Version 3.

This is the first wiki online that will help you to bring the power back from `TeliaSonera Company AB` and `Sagemcom` 
developers via _`ssh`_ `OR` _`telnet`_ and for being very clear in `=` No `intrusion` on `TeliaSonera Company AB` or `Sagemcom's` 
servers has occurred and **`NO`** damage on hardware has been done and im a _`non-profit`_ hacker that is doing this without any 
interests in _`politics`_ or to harm any companies and I have been in contact the developers of this firmware them for those who 
are wondering, `hacking` is my passion, for real. `NOT` a *wannabe* _criminal_ *black hat* _hacker_ because for me hacking is for 
fun and without any profits at all for education and sharing knowledge for fun!

this repository is all about extremely poor security in the firmware. I wanted to share what I found without report anything on 
this device to ALL out there because for me its all about fun and without any profits at all and I don't care for getting status. 

As usual, I do this for `YOU` completely free and you can share and change this wiki as much as you want, it would be appreciated 
 you added a url to this original readme to help us all for sharing knowledge and contribute to a safer internet if you want 
 - You are certainly not forced to this, of course ;)

## Find hidden settings in latest firmware (`v3.42.`)

![Screenshot](misc/hidden-settings.gif)

```javascript
$.xmo.getValuesTree("*")
$.xmo.getValuesTree("*/*")
$.xmo.getValuesTree("*/*/*")
$.xmo.getValuesTree("*/*/*/*")
$.xmo.getValuesTree("*/*/*/*/*")
$.xmo.getValuesTree("*/*/*/*/*/*")
$.xmo.getValuesTree("*/*/*/*/*/*/*")
and so on.. 
```

## For list more things like attributes wich above command wont list, use `getCapability` instead

```javascript
$.xmo.getCapability("*")
$.xmo.getCapability("*/*")
$.xmo.getCapability("*/*/*")
and so on..
```

## List configurations 

Where you can list `allowedUsers`, `blockedUsers` and other configurations

```javascript
$.config
$.config.allowedUsers
$.config.modules
$.config.reinitializeWithFactory
and so on..
```

## For list all features that has been disable from default

```javascript
$.config.showedpages
```

```
BoBStatus: {enable: false}
CPULoadField: {enable: false}
DHCPv6Server: {enable: false}
DLNA: {enable: true}
DTMFTransmissionMode: {enable: false}
GUIupgrade: {enable: false}
IAPDEnable: {enable: false}
MTU: {enable: false}
```

## Proof for the shell access, as `root`

![68747470733a2f2f6e72312e6e752f617263686976652f736167656d636f6d2d6861636b696e672f74656c69612d74656c6e65742e676966](https://user-images.githubusercontent.com/26827453/202030223-e06b7207-0c80-4f49-b1ad-be6cada5761f.gif)

As on earlier devices and configurations from `Telia Company AB` they still adding access 
wich is a kind of backdoor access **without** letting us know and I would never do this if 
things was done correct and being polite corect. So let me first say i'm not against what they do here 
if they have done it right. The "backdoor" access if for giving customers support efter their needs
remotely they told me _after_ 10 different answers from 10 differente people and all lied to me about this
so then it was of course not an option to NOT letting all know via this readme (be happy that i never did a bigger thing of this shit) 
so, here is the proof that we have backdoors in our device without getting any info at all from our ISP:

![68747470733a2f2f6e72312e6e752f617263686976652f736167656d636f6d2d6861636b696e672f736167656d2d6261636b646f6f722e706e67](https://user-images.githubusercontent.com/26827453/202030284-39c5ce37-9d9f-4264-b8dd-bb7899a0f22a.png)

It's not only `TeliaSonera Company` that got backdoors on our devices without letting us know, 
also `Sagemcom` that can use our network and sniff traffic, 
here is a proof for how to find info about all settings they have configured

![68747470733a2f2f6e72312e6e752f617263686976652f736167656d636f6d2d6861636b696e672f736167656d2d6f776e6564322e706e67](https://user-images.githubusercontent.com/26827453/202030335-0645ff31-23c8-4b0f-85e7-fbf6eba433cf.png)

## Stop/Start LXC From TelialXC Rootfs

```bash
lxc-stop -n teliaLxc -F
lxc-start -n teliaLxc -F
```

## UCI Settings

```bash
uci show network
uci show dhcp
uci show system
```

## Login as another user

```javascript
var x = $.xmo;
$.xmo.init();
$.xmo.login("username", "password");
$.dosomethingherewithoutloginongui
```

## Route info

```javascript
$.xmo.getValuesTree("Device/Routing/RouteInformation/Enable");
$.xmo.setValuesTree("true", "Device/Routing/RouteInformation/Enable");
```

## Enable ADVANCED Mode

```javascript
$.xmo.getValuesTree("Device/UserInterface/AdvancedMode");
$.xmo.setValuesTree("true", "Device/UserInterface/AdvancedMode");
```

## Set user settings for `Administrator`/`admin`/`internal`

```javascript
$.xmo.getValuesTree("Device/UserAccounts/Users/User[@uid='1']");
$.xmo.getValuesTree("Device/UserAccounts/Users/User[@uid='1']/Role");
$.xmo.setValuesTree("SuperUser", "Device/UserAccounts/Users/User[@uid='1']/Role");
$.xmo.setValuesTree("true", "Device/UserAccounts/Users/User[@uid='1']/CurrentlyRemoteAccess");
$.xmo.setValuesTree("wuseman@nr1.nu", "Device/UserAccounts/Users/User[@uid='1']/Email");
$.xmo.setValuesTree("Sweden", "Device/UserAccounts/Users/User[@uid='1']/Country");
$.xmo.setValuesTree("wuseman", "Device/UserAccounts/Users/User[@uid='1']/Lastname");
$.xmo.setValuesTree("true", "Device/UserAccounts/Users/User[@uid='1']/OwnPass");
$.xmo.getValuesTree("Device/UserAccounts/Users/User[@uid='1']/RemoteAccesses/RemoteAccess[@uid='1']");
$.xmo.getValuesTree("Device/UserAccounts/Users/User[@uid='2']/RemoteAccesses/RemoteAccess[@uid='1']");
$.xmo.getValuesTree("Device/UserAccounts/Users/User[@uid='3']/RemoteAccesses/RemoteAccess[@uid='1']");
$.xmo.getValuesTree("Device/UserAccounts/Users/User[@uid='2']/RemoteAccesses/RemoteAccess[@uid='1']");
```

## TeliaCompany AB: `backdoor`

```javascript
$.xmo.getValuesTree("Device/UserAccounts/Users/User[@uid='3']/RemoteAccesses/RemoteAccess[@uid='2']/Enabled"); # SSH FOR TELIA ENABLE BY DEFAULT
$.xmo.setValuesTree("false", "Device/UserAccounts/Users/User[@uid='3']/RemoteAccesses/RemoteAccess[@uid='3']/Enabled");
$.xmo.setValuesTree("false", "Device/UserAccounts/Users/User[@uid='3']/RemoteAccesses/RemoteAccess[@uid='4']/Enabled");
```

## Response to ping

```javascript
$.xmo.getValuesTree("$.xmo.getValuesTree("Device/Firewall/RespondToPing");");
$.xmo.setValuesTree("", "");
```

## Print/Set dyndns settings

```javascript
$.xmo.getValuesTree("Device/Services/DynamicDNS/Clients/Client[@uid='1']/Enable");
$.xmo.getValuesTree("Device/Services/DynamicDNS/Clients/Client[@uid='1']/Status");
$.xmo.getValuesTree("Device/Services/DynamicDNS/Clients/Client[@uid='1']/Username");
$.xmo.getValuesTree("Device/Services/DynamicDNS/Clients/Client[@uid='1']/Password");
```

## Storageservices get info 

```javascript
$.xmo.getValuesTree("Device/Services/StorageServices/StorageService[@uid='1']/Capabilities/SFTPCapable");
$.xmo.getValuesTree("Device/Services/StorageServices/StorageService[@uid='1']/Capabilities/FTPCapable");
$.xmo.getValuesTree("Device/Services/StorageServices/StorageService[@uid='1']/Capabilities/HTTPWritable");
```

## Storageservices set info

```javascript
$.xmo.setValuesTree("true", "Device/Services/StorageServices/StorageService[@uid='1']/Capabilities/SFTPCapable");
$.xmo.setValuesTree("true", "Device/Services/StorageServices/StorageService[@uid='1']/Capabilities/FTPCapable");
$.xmo.setValuesTree("true", "Device/Services/StorageServices/StorageService[@uid='1']/Capabilities/HTTPWritable");
$.xmo.setValuesTree("true", "Device/Services/StorageServices/StorageService[@uid='1']/Capabilities/VolumeEncryptionCapable");
$.xmo.getValuesTree("Device/Services/StorageServices/StorageService[@uid='1']/Capabilities/VolumeEncryptionCapable");
$.xmo.getValuesTree("Device/Services/StorageServices/StorageService[@uid='1']/Capabilities/SupportedNetworkProtocols");
$.xmo.getValuesTree("SMB,SSH,TELNET,HTTP", Device/Services/StorageServices/StorageService[@uid='1']/Capabilities/SupportedNetworkProtocols");
$.xmo.setValuesTree("true", "Device/Services/StorageServices/StorageService[@uid='1']/FTPServer/Enable");
$.xmo.getValuesTree("Device/Services/StorageServices/StorageService[@uid='1']/FTPServer/Enable");
$.xmo.getValuesTree("Device/Services/StorageServices/StorageService[@uid='1']/FTPServer/Status");
```

## Print IPv4 addresses

```javascript
$.xmo.getValuesTree("Device/IP/Interfaces/Interface[Alias=\"IP_DATA\"]/IPv4Addresses/IPv4Address[Alias=\"IP_DATA_ADDRESS\"]/IPAddress");
```

## Print IPv6 addresses

```javascript
$.xmo.getValuesTree("Device/IP/Interfaces/Interface[@uid='1']/IPv6Addresses/IPv6Address[@uid='1']/IPAddress");
```

## Enable telnet

```javascript
$.xmo.setValuesTree("ACCESS_ENABLE_ALL", "Device/UserAccounts/Users/User[@uid='1']/RemoteAccesses/RemoteAccess[@uid='4']/LANRestriction");
```

## Enable ssh on 

```javascript
$.xmo.setValuesTree("ACCESS_ENABLE_ALL", "Device/UserAccounts/Users/User[@uid='1']/RemoteAccesses/RemoteAccess[@uid='4']/LANRestriction");
```

## Print current hardware version

```javascript
$xmo.setValuesTree("Device/DeviceInfo/HardwareVersion");
```

## Remove blacklisted ports

```javascript
$.xmo.setValuesTree("", "Device/Managers/NetworkData/BlacklistedPorts");
$.xmo.getValuesTree("", "Device/Managers/NetworkData/BlacklistedPorts");
```

## Enable sftp

```javascript
$.xmo.getValuesTree("Device/ServicesStorageService[1]/Enable");
$.xmo.getValuesTree("Device/Services/StorageServices/StorageService[@uid='1']/Enable");
$.xmo.setValuesTree('true', "Device/Services/StorageServices/StorageService[@uid='1']/SFTPServer/Enable");
```

## Enable ftp

```javascript
$.xmo.getValuesTree("Device/Services/StorageServices/StorageService[@uid='1']/FTPServer");
$.xmo.setValuesTree("true", "Device/Services/StorageServices/StorageService[@uid='1']/FTPServer/Enable");
$.xmo.getValuesTree("Device/Services/StorageServices/StorageService[@uid='1']/FTPServer/Enable"); 
```

## Edit first connection

```javascript
$.xmo.getValuesTree("Device/DeviceInfo/FirstConnection");
```

## WAN Interface 

```javascript
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Role='WAN']");
```

## Print hw address address

```javascript
$.xmo.getValuesTree("Device/DeviceInfo/MACAddress");
```

## UPNP Settings

```javascript
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/UPnPMediaServerPort");
$.xmo.setValuesTree("wusemans home", "Device/UPnP/Settings/UPnPMediaServer/FriendlyName");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/FriendlyName");
$.xmo.setValuesTree("https://nr1.nu", "Device/UPnP/Settings/UPnPMediaServer/PresentationUrl");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/PresentationUrl");
$.xmo.setValuesTree("/", "Device/UPnP/Settings/UPnPMediaServer/RootFolder");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/RootFolder");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/UPnPNMCServer");
$.xmo.setValuesTree("true", "Device/UPnP/Settings/UPnPMediaServer/UPnPNMCServer");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/UploadEnabled");
$.xmo.setValuesTree("1", "Device/UPnP/Settings/UPnPMediaServer/UploadEnabled");
```

## Enable more accessControl settings

```javascript
$.xmo.getValuesTree("Device/Managers/NetworkLan/AccessControlEnable");
$.xmo.setValuesTree('true', "Device/Managers/NetworkLan/AccessControlEnable");
$.xmo.setValuesTree("true", "Device/Managers/NetworkLan/GuestAccessControlEnable");
$.xmo.getValuesTree("Device/Managers/NetworkLan/GuestAccessControlEnable");
```

## Enable advanced mode

```javascript
$.xmo.setValuesTree("true", "Device/UserInterface/AdvancedMode");
```

## Get status for advanced mode

```javascript
$.xmo.getValuesTree("Device/UserInterface/AdvancedMode");  
```

## Configure syslog to send logs to remote server

* Browser Developer Console

```javascript
$.xmo.setValuesTree("192.168.1.104", "Device/DeviceInfo/Logging/Syslog/Server/IPv4Address");
$.xmo.setValuesTree(".*", "Device/DeviceInfo/Logging/Syslog/Server/SyslogConfig");
```

## Configure syslog to from commandline

```bash
sed -i 's/81.236.57.18/192.168.1.104/g' /etc/syslog-ng/syslog-ng.conf 
sed -i 's/1.1.1.1/192.168.1.104/g' /telia/lxc/rootfs/etc/syslog-ng/syslog-ng.conf
```

## Play with css (theme) colors

```javascript
$.xmo.setValuesTree("#000000", "Device/UserInterface/BackgroundColor")
$.xmo.setValuesTree("white", "Device/UserInterface/ButtonTextColor")
$.xmo.setValuesTree("magenta", "Device/UserInterface/ButtonColor")
$.xmo.setValuesTree("white", "Device/UserInterface/TextColor")
```

## Disable upcomming firmware upgrades

```
Telia ACS Server: https://acs.telia.com:7575/ACS-server/ACS"
```

```javascript
$.xmo.setValuesTree("", "Device/Managers/NetworkData/MultiVlanUrl");
$.xmo.setValuesTree("",  "Device/Managers/NetworkData/SingleModeUrl");
$.xmo.setValuesTree("",  "Device/ManagementServer/ConnectionRequestURL");
$.xmo.setValuesTree(false", "Device/ManagementServer/PeriodicInformEnable");
$.xmo.setValuesTree("", "Device/ManagementServer/URL");
$.xmo.getValuesTree("Device/Managers/NetworkData")
```

## Print serial number of device

```javascript
$.xmo.getValuesTree("Device/GatewayInfo/SerialNumber");
```

## Configure hostname/dns

```javascript
$.xmo.getValuesTree("Device/DNS/Client/HostName");
$.xmo.getValuesTree("Device/DNS/Client/LocalDomains");
$.xmo.setValuesTree("router, "Device/DNS/Client/LocalDomains");
$.xmo.setValuesTree("router", "Device/DNS/Client/HostName");
$.xmo.getValuesTree("Device/DNS/Client/Servers[0]/DNSServer")"; # NOT WORK
$.xmo.getValuesTree("Device/Services/DynamicDNS/Clients/Client[1]/Enable");

```

## Print current dns server in use

```javascript
$.xmo.getValuesTree("Device/DNS/Client/Servers/Server[1]/DNSServer");
$.xmo.getValuesTree("Device/DNS/Client/Servers/Server[2]/DNSServer");

```

## Print time/date for router

```javascript
$.xmo.getValuesTree("Device/Time/Enable");
$.xmo.getValuesTree("Device/Time/Status");
```

## QOS Settings

```javascript
$.xmo.getValuesTree("Device/QoS/DefaultDSCPMark");
```

## Dump current status for usb

```javascript
$.xmo.getValuesTree("Device/USB/Enable");

```

## Dump info about interfaces

```javascript
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY1"]/Stats/BroadcastPacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY1"]/Stats/BroadcastPacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY1"]/Stats/BytesReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY1"]/Stats/BytesSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY1"]/CurrentBitRate");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY1"]/Diagnostics/CurrentBitRate");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY1"]/Stats/DiscardPacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY1"]/Stats/DiscardPacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY1"]/Diagnostics/CurrentDuplexMode");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY1"]/Stats/ErrorsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY1"]/Stats/ErrorsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY1"]/Stats/MulticastPacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY1"]/Stats/MulticastPacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY1"]/Stats/PacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY1"]/Stats/PacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY1"]/Status");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY1"]/Stats/UnicastPacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY1"]/Stats/UnicastPacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY2"]/Stats/BroadcastPacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY2"]/Stats/BroadcastPacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY2"]/Stats/BytesReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY2"]/Stats/BytesSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY2"]/CurrentBitRate");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY2"]/Diagnostics/CurrentBitRate");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY2"]/Stats/DiscardPacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY2"]/Stats/DiscardPacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY2"]/Diagnostics/CurrentDuplexMode");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY2"]/Stats/ErrorsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY2"]/Stats/ErrorsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY2"]/Stats/MulticastPacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY2"]/Stats/MulticastPacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY2"]/Stats/PacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY2"]/Stats/PacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY2"]/Status");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY2"]/Stats/UnicastPacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY2"]/Stats/UnicastPacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY3"]/Stats/BroadcastPacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY3"]/Stats/BroadcastPacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY3"]/Stats/BytesReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY3"]/Stats/BytesSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY3"]/CurrentBitRate");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY3"]/Diagnostics/CurrentBitRate");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY3"]/Stats/DiscardPacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY3"]/Stats/DiscardPacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY3"]/Diagnostics/CurrentDuplexMode");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY3"]/Stats/ErrorsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY3"]/Stats/ErrorsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY3"]/Stats/MulticastPacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY3"]/Stats/MulticastPacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY3"]/Stats/PacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY3"]/Stats/PacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY3"]/Status");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY3"]/Stats/UnicastPacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY3"]/Stats/UnicastPacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY4"]/Stats/BroadcastPacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY4"]/Stats/BroadcastPacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY4"]/Stats/BytesReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY4"]/Stats/BytesSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY4"]/CurrentBitRate");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY4"]/Diagnostics/CurrentBitRate");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY4"]/Stats/DiscardPacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY4"]/Stats/DiscardPacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY4"]/Diagnostics/CurrentDuplexMode");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY4"]/Stats/ErrorsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY4"]/Stats/ErrorsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY4"]/Stats/MulticastPacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY4"]/Stats/MulticastPacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY4"]/Stats/PacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY4"]/Stats/PacketsSent");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY4"]/Status");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY4"]/Stats/UnicastPacketsReceived");
$.xmo.getValuesTree("Device/Ethernet/Interfaces/Interface[Alias="PHY4"]/Stats/UnicastPacketsSent");
```

## Disable blacklists

```javascript
$.xmo.getValuesTree("Device/Hosts/Hosts/Host[@uid='1']");
$.xmo.setValuesTree('false', "Device/Hosts/Hosts/Host[@uid='1']/BlacklistEnable");
$.xmo.setValuesTree('false', "Device/Hosts/Hosts/Host[@uid='1']/BlacklistedAccordingToSchedule");
$.xmo.getValuesTree("Device/Hosts/Hosts");
```

## Configure and control various rules

```css
sboxApp.controller("AntennaSettingsController", ["$scope", "$rootScope", "$timeout", "AntennaSettings", function($scope, $rootScope, $timeout, AntennaSettings) {
    $scope.populate = function() {
        $scope.antennaTypes = $.constants.antennaTypes;
        var data = AntennaSettings.populate();
        data.autoDetectionAntenna ? $scope.antennaType = 1 : data.enableExtMainAntenna || data.enableExtRXAntenna ? data.enableExtMainAntenna && !data.enableExtRXAntenna ? $scope.antennaType = 3 : data.enableExtMainAntenna && data.enableExtRXAntenna && 
($scope.antennaType = 4) : $scope.antennaType = 2
    }
    ,
    $scope.populate(),
    $scope.save = function() {
        var dataToSave = {};
        switch ($scope.antennaType) {
        case 1:
            dataToSave.autoDetectionAntenna = !0;
            break;
        case 2:
            dataToSave.autoDetectionAntenna = !1,
            dataToSave.enableExtMainAntenna = !1,
            dataToSave.enableExtRXAntenna = !1;
            break;
        case 3:
            dataToSave.autoDetectionAntenna = !1,
            dataToSave.enableExtMainAntenna = !0,
            dataToSave.enableExtRXAntenna = !1;
            break;
        case 4:
            dataToSave.autoDetectionAntenna = !1,
            dataToSave.enableExtMainAntenna = !0,
            dataToSave.enableExtRXAntenna = !0
        }
        AntennaSettings.save(dataToSave, {
            success: function() {
                $rootScope.globalWait = !1,
                $rootScope.showMessage = !0,
                $timeout(function() {
                    $rootScope.$digest()
                })
            },
            error: function() {
                $rootScope.globalWait = !1,
                $rootScope.showMessage = !1,
                $timeout(function() {
                    $rootScope.$digest()
                })
            }
        })
    }
     }
     ]),
     sboxApp.controller("ExtendedMenuController", function($scope, $rootScope) {
         $scope.checkUrlPath = function() {
        $scope.active = "",
        "user.home" === $rootScope.currentRouteName ? $scope.active = "home" : $rootScope.currentRouteName.indexOf("user.internetConnectivity") > -1 ? $scope.active = "connectivity" : $rootScope.currentRouteName.indexOf("user.mysagemcombox") > -1 ? $scope.active 
= "router" : $rootScope.currentRouteName.indexOf("user.accessControl") > -1 ? $scope.active = "access" : $rootScope.currentRouteName.indexOf("user.wifi") > -1 && ($scope.active = "wifi")
    }
    ,
    $scope.checkUrlPath()
     });
```

## Change values to true after changes

```javascript
$.xmo.addChild($.xpaths.advanced.remoteManagement.usersUpdate.enable = "true")
```

## VOIP settings

```javascript
$.xmo.getValuesTree("Device/Services/VoiceServices/VoiceService[@uid=1]/VoiceProfiles/VoiceProfile[@uid=1]/Enable");
$.xmo.getValuesTree("Device/Services/VoiceServices/VoiceService[@uid='1']/PhyInterfaces/PhyInterface/OutGoingLine");
```

## RIP settings

```javascript
$.xmo.getValuesTree("Device/Routing/RIP/Enable");
$.xmo.setValuesTree('true', "Device/Routing/RIP/Enable");
```

## Print pre-configured country for device

```javascript
$.xmo.getValuesTree("Device/DeviceInfo/Country");
```

## Configure cwpd settings

```javascript
$.xmo.setValuesTree("", "Device/ManagementServer/TR69InternalData/Settings/Port");
$.xmo.getValuesTree("Device/ManagementServer/TR69InternalData/Settings/Port")
```

## Dump password for any user (by username)

```javascript
$.xmo.client.getPassword('username')
```

## UPNP/Twonky settings

```javascript
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/AllName");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/AllPictures");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/AllRadio");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/AllTracks");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/AllVideos");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/InternetRadio");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/MusicNodes/MusicNode[@uid='1']/Attributes");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/MusicNodes/MusicNode[@uid='2']/Attributes");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/MusicNodes/MusicNode[@uid='3']/Attributes");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/MusicNodes/MusicNode[@uid='4']/Attributes");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/MusicNodes/MusicNode[@uid='5']/Attributes");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/PictureNodes/PictureNode[@uid='1']/Attributes");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/PictureNodes/PictureNode[@uid='2']/Attributes");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/PictureNodes/PictureNode[@uid='3']/Attributes");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/PlaylistLastPlayed");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/PlaylistMostPlayed");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/Playlists");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/RootMusic");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/RootPicture");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/RootVideo");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/TagsPicture");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/VideoNodes/VideoNode[@uid='1']/Attributes");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/VideoNodes/VideoNode[@uid='2']/Attributes");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/VideoNodes/VideoNode[@uid='3']/Attributes");
$.xmo.getValuesTree("Device/UPnP/Settings/UPnPMediaServer/Language");
```

## Print wireless settings

```javascript
$.xmo.getValuesTree("Device/WiFi/SSIDs");
```

## Configure portscan detection

```javascript
$.xmo.getValuesTree("Device/Firewall/PortScanDetection");
$.xmo.setValuesTree('true', "Device/Firewall/PortScanDetection");
```

## Print password hash for any user (by username)

```javascript
$.xmo.client.hashPassword('username')
```

## Login another user

```javascript
$.xmo.client.authenticate('username')
```

## Save cookies with password

```javascript
$.xmo.client.saveToCookie
```

## Info about authentications

```javascript
$.xmo.client._options
```

## List pending requests
```javascript
$.xmo.client._pendingRequests
```

## Find your UID or SESSION ID wich is needed for set settings permanent

```javascript
$.xmo.client._sessionId
```

## List and set different name on any setting, you can use your own js script for example

```javascript
$.xmo.client.__proto__
```

## Gather info about your device (included plain text passwords)

```javascript
$.xmo.getValuesTree('Device')
```

![68747470733a2f2f6e72312e6e752f617263686976652f736167656d636f6d2d6861636b696e672f6465766963652d696e666f2e706e67](https://user-images.githubusercontent.com/26827453/202030518-29097da5-0f17-4001-bffa-c6b30ec630ce.png)


## Gather info for users

```javascript
$.xmo.getValuesTree("Device/UserAccounts/Users");
```
    
![68747470733a2f2f6e72312e6e752f617263686976652f736167656d636f6d2d6861636b696e672f75736572706173732e706e67](https://user-images.githubusercontent.com/26827453/202030581-6590f509-cf99-49a2-968a-480d739e52a9.png)

## Dump deviceInfo

```javascript
$.xmo.getValuesTree($.xpaths.mySagemcomBox);
```

![68747470733a2f2f6e72312e6e752f617263686976652f736167656d636f6d2d6861636b696e672f736167656d636f6d626f782e706e67 (1)](https://user-images.githubusercontent.com/26827453/202043519-048b294a-3491-45cb-b4bc-96df82796078.png)

## Reboot device via developer console

```javascript
$.xmo.reboot = function() {
        if (!$.xmo.loggedin())
        throw new $.xmo.NotLoggedInError("reboot error: Not logged in");
         var a = $.xmo.client.newRequest();
         a.remoteCall($.xpaths.trafficStats.rpc, "reboot", {
         source: "GUI"
     }),
         a.send();
```

## Set runlevel for device

| Level      | Description     |
|------------|-----------------|
| Runlevel 1 | Lock most modem functions including wifi |
| Runlevel 2 | The same as above with the wifi unlocked |
| Runlevel 3 | The USB is unlocked. It is not possible to change the IP of the gateway nor to activate the BRIDGE mode |
| Runlevel 4 | All GVT firmware functions are unlocked. All of the above mentioned in the 3 + change of gateway ip |

```javascript
$.xmo.setValuesTree(4, $.xpaths.runlevel);
```

## For set settings it is required to have knowledge about xpaths, grab them by type

```javascript
$.xpaths
```

## So for example to use everything from xpaths we can print our IP as an example by command

```javascript
$.xmo.getValuesTree("Device.IP.Interfaces.Interface[Alias=\"IP_DATA\"].IPv4Addresses.IPv4Address[Alias=\"IP_DATA_ADDRESS\"].IPAddress");
```

There is plenty of configuration files on the router and for download all these 
we need use newRequest and we also will use a function for this, 
edit the filename if you found another conf or file you want to download

```javascript
$.config.modules.backupConfigurationAllBackup === !0 ? a.downloadSpecificFile($.xpaths.mySagemcomBox.maintenance.saveRestore.save, "device.cfg", 1, function() {}, function(a) {}) : 
$.xmo.client.newRequest..downloadFile($.xpaths.mySagemcomBox.maintenance.saveRestore.save, function() {}, function(a) {}), $.xmo.client.newRequest.send;
```
![68747470733a2f2f6e72312e6e752f617263686976652f736167656d636f6d2d6861636b696e672f646f776e6c6f61642d66696c65732e676966 (1)](https://user-images.githubusercontent.com/26827453/202043295-4d8ca9ee-69fc-45a2-9db2-1d5e76b68b9d.gif)

## Disable autologout after X seconds idle

![68747470733a2f2f6e72312e6e752f617263686976652f736167656d636f6d2d6861636b696e672f616e6e6f79696e672d6c6f676f75742e706e67 (2)](https://user-images.githubusercontent.com/26827453/202043345-6e3f433f-8b0f-466b-ae9a-1b688c9297ec.png)
    
* Method 1

```javascript
$.xmo.setValuesTree(0, "Device.UserInterface.Httpd.SessionTimeout"); 
```

* Method 2

```javascript
$.xmo.sessionTimeOut = 0;
```

## Print device model

```javascript
$.xmo.getValuesTree($.xpaths.mySagemcomBox.deviceInfo.modelNumber);
```

## Change password for any user

```javascript
$.xmo.changePassword("<userrnameToEditPasswordFor>","<changethistourPassword");
```

## Dumps wizard settings

```javascript
$.xpaths.wizard
```

## List all features available

```javascript
$.xpaths.checkFeaturesAvailable
```

* Of course you can use them one by one aswell but the trick is to NOT include checkFeaturesAvailable: 
  
```javascript 
$.xmo.getValuesTree($.xpaths.myCloud);
$.xmo.getValuesTree($.xpaths.Device);
$.xmo.getValuesTree($.xpaths.adminAdvanced);
$.xmo.getValuesTree($.xpaths.accessControl);
$.xmo.getValuesTree($.xpaths.accessControl.firewall);
$.xmo.getValuesTree($.xpaths.accessControl.serviceCapability); 
```

```css
showedpages.dhcpEnable
showedpages.comhem
showedpages.certificates.enable
showedpages.bell.enable
showedpages.VPN.enable
showedpages.VPN
modules.myBox.dhcp.blacklistedIps
modules.myBox.dhcp.defaultValues
.....and so on

```

## Enable masstorage via samba

```javascript
$.xmo.setValuesTree('true', "massStorage.samba.enable");
```

## Enable walletgarden

```javascript
$.xmo.setValuesTree('true', "walledGarden.enable");
```

## Save edited settings (must be used before reboot)

```javascript
$.xmo.setValuesTree('true', "maintenance.saveRestore.save");
```

## Configure dropbear via router shell

```bash
mkdir -p /tmp/dropbear
/usr/bin/dropbearkey -t rsa -f 
/tmp/dropbear/dropbear_rsa_host_key 2>&- >&-
/usr/bin/dropbearkey -t dss -f 
/tmp/dropbear/dropbear_dss_host_key 2>&- >&-
vim /etc/dropbear/authorized_keys
chmod 600 authorized_keys
```

## LXC - Telia 

```bash
lxc-start -n teliaLxc -F
```

## LXC files/paths

```bash
/usr/share/lxs/userns.conf
/usr/share/lxs/ubuntu-cloud.userns.conf
/usr/share/lxs/plamo.common.conf
/usr/share/lxs/opensuse.userns.conf
/usr/share/lxs/gentoo.common.conf
/usr/share/lxs/debian.common.conf
/usr/share/lxs/centos.userns.conf
/usr/share/lxs/ubuntu.userns.conf
/usr/share/lxs/ubuntu-cloud.lucid.conf
/usr/share/lxs/oracle.userns.conf
/usr/share/lxs/opensuse.common.conf
/usr/share/lxs/fedora.userns.conf
/usr/share/lxs/common.seccomp
/usr/share/lxs/centos.common.conf
/usr/share/lxs/ubuntu.lucid.conf
/usr/share/lxs/ubuntu-cloud.common.conf
/usr/share/lxs/oracle.common.conf
/usr/share/lxs/gentoo.userns.conf
/usr/share/lxs/fedora.common.conf
/usr/share/lxs/common.conf.d
/usr/share/lxs/archlinux.userns.conf
/usr/share/lxs/ubuntu.common.conf
/usr/share/lxs/plamo.userns.conf
/usr/share/lxs/openwrt.common.conf
/usr/share/lxs/gentoo.moresecure.conf
/usr/share/lxs/debian.userns.conf
/usr/share/lxs/common.conf
/usr/share/lxs/archlinux.common.conf

```

## Userinfo

USER/1 = admin - edit all values here (if you want)

```javascript
$.xmo.getValuesTree("Device/UserAccounts/Users/User[@uid='1']");
$.xmo.getValuesTree("Device/UserAccounts/Users/User[@uid='1']/Role");
$.xmo.setValuesTree("SuperUser", "Device/UserAccounts/Users/User[@uid='1']/Role");
$.xmo.setValuesTree("true", "Device/UserAccounts/Users/User[@uid='1']/CurrentlyRemoteAccess");
$.xmo.setValuesTree("wuseman@nr1.nu", "Device/UserAccounts/Users/User[@uid='1']/Email");
$.xmo.setValuesTree("Sweden", "Device/UserAccounts/Users/User[@uid='1']/Country");
$.xmo.setValuesTree("wuseman", "Device/UserAccounts/Users/User[@uid='1']/Lastname");
$.xmo.setValuesTree("true", "Device/UserAccounts/Users/User[@uid='1']/OwnPass");
$.xmo.getValuesTree("Device/UserAccounts/Users/User[@uid='1']/RemoteAccesses/RemoteAccess[@uid='1']");
$.xmo.getValuesTree("Device/UserAccounts/Users/User[@uid='2']/RemoteAccesses/RemoteAccess[@uid='1']");
$.xmo.getValuesTree("Device/UserAccounts/Users/User[@uid='3']/RemoteAccesses/RemoteAccess[@uid='1']");
$.xmo.getValuesTree("Device/UserAccounts/Users/User[@uid='2']/RemoteAccesses/RemoteAccess[@uid='1']");
```

## Firmware info

```
Source....: http://MASKED.for.safety
Username..: MASKED.for.safety
Password..: MASKED.for.safety
```

```javascript
$.xmo.getValuesTree("Device/ManagementServer/Username");
$.xmo.setValuesTree("", "Device/ManagementServer/Username");
$.xmo.getValuesTree("Device/ManagementServer/Password");
$.xmo.setValuesTree("", "Device/ManagementServer/Password");
```

## Disable all remote acccess for ISP, copy and paste

```javascript
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="IP_MNGT"]/LowerLayers')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="IP_MNGT"]/Router')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="IP_VOIP"]/Enabled')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="IP_VOIP"]/IPv4Addresses/IPv4Address[Alias="IP_VOIP_ADDRESS"]/IPAddress')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="IP_VOIP"]/IPv4Addresses/IPv4Address[Alias="IP_VOIP_ADDRESS"]/Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="IP_VOIP"]/IPv4Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="IP_VOIP"]/IPv6Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="IP_VOIP"]/IPv4Addresses/IPv4Address[Alias="IP_VOIP_ADDRESS"]/Enable')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="IP_VOIP"]/Name')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="IP_VOIP"]/LowerLayers')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="IP_VOIP"]/Router')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="IP_IPTV"]/IPv4Addresses/IPv4Address[Alias="IPTV_ADDRESS"]/IPAddress')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="IP_IPTV"]/IPv4Addresses/IPv4Address[Alias="IPTV_ADDRESS"]/Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="IP_IPTV"]/IPv4Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="IP_IPTV"]/IPv6Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="IP_IPTV"]/IPv4Addresses/IPv4Address[Alias="IPTV_ADDRESS"]/Enable')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="IP_IPTV"]/Name')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="IP_IPTV"]/LowerLayers')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="IP_IPTV"]/Router')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="IP_BR_GUEST"]/IPv4Addresses/IPv4Address[Alias="IP_BR_GUEST_ADDRESS"]/IPAddress')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="IP_BR_GUEST"]/IPv4Addresses/IPv4Address[Alias="IP_BR_GUEST_ADDRESS"]/Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="IP_BR_GUEST"]/IPv4Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="IP_BR_GUEST"]/IPv6Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="IP_BR_GUEST"]/IPv4Addresses/IPv4Address[Alias="IP_BR_GUEST_ADDRESS"]/Enable')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="IP_BR_GUEST"]/Name')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="IP_BR_GUEST"]/LowerLayers')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="IP_BR_GUEST"]/Router')
$.xmo.setValuesTree("HEY1", 'Device/IP/Interfaces/Interface[Alias="IP_MNGT"]/Alias')
$.xmo.setValuesTree("HEY2", 'Device/IP/Interfaces/Interface[Alias="IP_VOIP"]/Alias')
$.xmo.setValuesTree("HEY3", 'Device/IP/Interfaces/Interface[Alias="IP_IPTV"]/Alias')
$.xmo.setValuesTree("HEY4", 'Device/IP/Interfaces/Interface[Alias="IP_BR_GUEST"]/Alias')
$.xmo.setValuesTree("HEY5", 'Device/IP/Interfaces/Interface[Alias="IP_BR_GUEST"]/Alias')
$.xmo.setValuesTree("HEY6", 'Device/IP/Interfaces/Interface[Alias="IP_BR_GUEST_ADDRESS"]/Alias')
$.xmo.setValuesTree("HEY7", 'Device/IP/Interfaces/Interface[Alias="IP_VOIP_ADDRESS"]/Alias')
$.xmo.setValuesTree("HEY8", 'Device/IP/Interfaces/Interface[Alias="IP_MNGT_ADDRESS"]/Alias')
$.xmo.setValuesTree("hey", 'Device/IP/Interfaces/Interface[Alias="IP_VOIP"]/Alias')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY"]/Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY1"]/Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY2"]/Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY3"]/Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY4"]/Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY5"]/Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY6"]/Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY7"]/Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY8"]/Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY"]/IPv4Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY1"]/IPv4Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY2"]/IPv4Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY3"]/IPv4Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY4"]/IPv4Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY5"]/IPv4Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY6"]/IPv4Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY7"]/IPv4Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY8"]/IPv4Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY"]/IPv6Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY1"]/EIPv6Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY2"]/IPv6Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY3"]/IPv6Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY4"]/IPv6Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY5"]/IPv6Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY6"]/IPv6Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY7"]/IPv6Enable')
$.xmo.setValuesTree("false", 'Device/IP/Interfaces/Interface[Alias="HEY8"]/IPv6Enable')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY1"]/LowerLayers')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY2"]/LowerLayers')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY3"]/LowerLayers')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY4"]/LowerLayers')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY5"]/LowerLayers')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY6"]/LowerLayers')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY7"]/LowerLayers')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY8"]/LowerLayers')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY1"]/Name')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY2"]/Name')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY3"]/Name')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY4"]/Name')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY5"]/Name')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY6"]/Name')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY7"]/Names')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY8"]/Name')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY1"]/Router')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY2"]/Router')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY3"]/Router')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY4"]/Router')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY5"]/Router')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY6"]/Router')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY7"]/Router')
$.xmo.setValuesTree("", 'Device/IP/Interfaces/Interface[Alias="HEY8"]/Router');
```

## Dump leds values

```javascript
$.xmo.getValuesTree("Device/Managers/Led/LedPowerBlink");
$.xmo.setValuesTree("true", "Device/Managers/Led/LedPowerBlink");
```

## AccessControl

```javascript
$.xmo.getValuesTree("Device/Managers/NetworkLan/AccessControlEnable");
$.xmo.setValuesTree("true", "Device/Managers/NetworkLan/AccessControlEnable");
```

## Flush device logs

```javascript
$.xmo.getValuesTree("Device/DeviceInfo/FlushDeviceLog");
$.xmo.getValuesTree("true", "Device/DeviceInfo/FlushDeviceLog");
```

## Cwmpd settings

```javascript
$.xmo.getValuesTree("Device/ManagementServer/EnableCWMP")
$.xmo.setValuesTree(false, "Device/ManagementServer/EnableCWMP")
```

## Print masstorage data

```javascript
$.xmo.setValuesTree("wuseman", $.xpaths.mySagemcomBox.massStorage.dlnaMediaName)
```

## Route info

```javascript
$.xmo.getValuesTree("Device/Routing/RouteInformation/Enable");
$.xmo.setValuesTree("true", "Device/Routing/RouteInformation/Enable");
```

## Dump passwprd commandline interface (serial console)

```javascript
$.xmo.getValuesTree("Device/Services/CLIPassword");
$.xmo.setValuesTree("odemnn", "Device/Services/CLIPassword");
```

## Parent control settings

```javascript
$.xmo.getValuesTree("Device/Services/ParentalControl/Enable");
$.xmo.setValuesTree("true", "Device/Services/ParentalControl/Enable");
```

## Random stuff

```javascript
$.xmo.getValuesTree($.xpaths.management);
$.xmo.getValuesTree($.xpaths.main);
$.xmo.getValuesTree($.xpaths.rpc);
$.xmo.getValuesTree($.xpaths.technicalLogFast);
$.xmo.getValuesTree($.xpaths.adminAdvanced);
$.xmo.getValuesTree($.xpaths.internetConnectivity);
$.xmo.getValuesTree($.xpaths.trafficStats); < SSH HERE
$.xmo.getValuesTree("Device/Routing/RIP/X_SAGEMCOM_RIPIPPrefix/X_SAGEMCOM_RIPIPPrefix/RIPDefaultGateway");
$.xmo.getValuesTree($.xpaths.mySagemcomBox)
```

```css
ipSecEnable: "Device/NAT/IPSecPassthroughEnable"
portScanDetection: "Device/Firewall/PortScanDetection"
pptpEnable: "Device/NAT/PPTPPassthroughEnable"
remoteConfig: "Device/UserAccounts/Users/User[@uid="#uid#"]/RemoteAccesses/RemoteAccess[@uid="#uidRemoteAccess#"]/WANRestriction"
remoteIPAddress: "Device/IP/Interfaces/Interface[Alias='IP_DATA']/IPv4Addresses/IPv4Address[Alias='IP_DATA_ADDRESS']/IPAddress"
remoteServicePort: "Device/UserAccounts/Users/User[@uid='3']/RemoteAccesses/RemoteAccess[@uid='3']/Port"
sipAlgEnable: "Device/NAT/SIPALGEnable"
upnpEnable: "Device/UPnP/Device/Enable"
users: "Device/UserAccounts/Users"
wanBlockingEnable: "Device/Firewall/WanBlocking"
```

## Go visit 192.168.1.1:9000 to enjoy the hidden Twonky interface

![68747470733a2f2f6e72312e6e752f617263686976652f736167656d636f6d2d6861636b696e672f74776f6e6b792d736167656d636f6d2e706e67](https://user-images.githubusercontent.com/26827453/202127484-bdc3c13a-9515-4df1-9f9b-7f42371cbf2c.png)

```bash
curl 192.168.1.1:9000/rpc/reset
> reset to defaults!
```

## Check webconfig/config.js for more rpc files, few examples
```bash
curl 192.168.1.1:9000/nmc/rpc
curl 192.168.1.1:9000/webconfig/config.js
```

![68747470733a2f2f6e72312e6e752f617263686976652f736167656d636f6d2d6861636b696e672f736167656d636f6d2d35333730652e706e67](https://user-images.githubusercontent.com/26827453/202127510-ff1f1ddc-daa5-46ce-9212-7c8f1d4d74d4.png)

## List folders by an exploit

```bash
curl http://192.168.1.1:9000/rpc/dir?=path=/bin/ls
001D/
003D/lxc
004D/run
005D/usr
006D/www
007D/root
008D/Music
009D/Video
010D/telia
011D/Picture
012D/twonky
016D/mnt
018D/overlay
020D/rom
023D/tmp
024D/var
```

## Response and settings for `Twonky`

```bash
curl http://192.168.1.1:9000/rpc/get_all
```
```css
    friendlyname=myTwonky Library at mynetwork
    ip=
    nicrestart=1
    v=0
    platform=UNIX
    httpport=
    ininame=twonkyvision-mediaserver.ini
    inipath=/usr/local/mediaserver
    read_only=0
    ssdpttl=4
    ssdpheartbeattimeout=100
    appdata=/var/twonky
    clearclientsonrestart=0
    disablelocalssdp=1
    enabletls=1
    nmcmode=1
    vlevel=4
    stack_size=196608
    language=en
    mediafusionserverurl=
    userid=
    portalusername=
    twonkyinfo=
    reportdevice=1
    enablenmcwebapi=1
    followlinks=1
    flushlogmsg=0
    webdavport=
    ignoreip=
    mediatypefilter=A
    accessuser=
    accesspwd=
    cachedir=/var/twonky/db/cache
    cachemaxsize=
    cdkey=
    clientautoenable=1
    codepage=932
    compilationsdir=Compilations,Sampler
    contentbase=/
    contentdir=
    dbdir=/var/twonky/db
    dyndns=
    enableweb=2
    httpremoteport=
    ignoredir=AppleDouble,AppleDB,AppleDesktop,TemporaryItems,.fseventsd,.Spotlight-            V100,.Trashes,.Trash,RECYCLED,RECYCLER,RECYCLE.BIN
    ituneslib=default
    scantime=-1
    streambuffer=16384
    uploadenabled=1
    servermanagedmusicdir=/twonky/music/Twonky
    servermanagedpicturedir=/twonky/pictures/Twonky
    servermanagedvideodir=/twonky/videos/Twonky
    mediastatisticsenabled=0
    mediastatisticsdir=/var/twonky/media-statistics/
    defaultview=advanceddefault
    bgtrans=
    rmdrives=
    rmhomedrive=/var/twonky/db
    rmautoshare=0
    maxitems=0
    suppressmenu=
    aggregation=0
    aggmode=0
    secure_folder_path=
    autoupdateinstall=0
    remoteaccess=0
    remoteaccessflash=0
    dtcpsessionlimit=8
    dtcpsessioncount=
    uploaddestinationfriendlyname=UploadDestination
    uploadrestrictedprofiles=
    disablefrontends=
    upnpuploadlimit=0
    disablesleepmode=0
    uploadmaxfilesize=0,0,0
    httpsessionlimit=
    clearcacheonrestart=
    scalermaxpixels=
    hdrlnextreadyvalue=180
    enablenonkeyframetstgen=0
    importdir=
    disablemytwonky=0
    includefolder=0
    rmadditunes=0
    rmupload=0
    contentdiscoverymode=7
    enableruiserver=0
    disabletimeseek=0
    albumartdir=
    disableduplicateremoval=0
    ignoredirwithfile=.nomedia,.ignorethis
    clearclientsonnicchange=0
    forceinitialscan=0
    classifiedaccessuser=
    classifiedaccesspwd=
    importscantime=
    limittranscodingperclient=0
    disablepmscaling=0
    ........
```

## All sections for device settings

```javascript
$.xmo.getValuesTree($.xpaths.Device)
$.xmo.getValuesTree($.xpaths.XORCryptKey)
$.xmo.getValuesTree($.xpaths.accessControl)
$.xmo.getValuesTree($.xpaths.adminAdvanced)
$.xmo.getValuesTree($.xpaths.advanced) # HOW TO CHANGE NULL TO 1 ?
$.xmo.getValuesTree($.xpaths.availability)
$.xmo.getValuesTree($.xpaths.broadband)
$.xmo.getValuesTree($.xpaths.ipv6Status)
$.xmo.getValuesTree($.xpaths.cableModem)
$.xmo.getValuesTree($.xpaths.checkFeaturesAvailable)
$.xmo.getValuesTree($.xpaths.myMedia)
$.xmo.getValuesTree($.xpaths.dect)
$.xmo.getValuesTree($.xpaths.dhcpLeases)
$.xmo.getValuesTree($.xpaths.ethernet)
$.xmo.getValuesTree($.xpaths.ethernetDevice)
$.xmo.getValuesTree($.xpaths.firstConnection)
$.xmo.getValuesTree($.xpaths.forbiddenIps)
$.xmo.getValuesTree($.xpaths.gateway)
$.xmo.getValuesTree($.xpaths.gpon)
$.xmo.getValuesTree($.xpaths.greTunnel)
$.xmo.getValuesTree($.xpaths.healthCheck)
$.xmo.getValuesTree($.xpaths.internetConnectivity)
$.xmo.getValuesTree($.xpaths.leds)
$.xmo.getValuesTree($.xpaths.main)
$.xmo.getValuesTree($.xpaths.management)
$.xmo.getValuesTree($.xpaths.accountSettings)
$.xmo.getValuesTree($.xpaths.myCloud)
$.xmo.getValuesTree($.xpaths.mySagemcomBox)
$.xmo.getValuesTree($.xpaths.mymedia)
$.xmo.getValuesTree($.xpaths.neighborAps)
$.xmo.getValuesTree($.xpaths.rpc)
$.xmo.getValuesTree($.xpaths.runlevel)
$.xmo.getValuesTree($.xpaths.scheduling)
$.xmo.getValuesTree($.xpaths.singleLine)
$.xmo.getValuesTree($.xpaths.splashScreen)
$.xmo.getValuesTree($.xpaths.ssidCreation)
$.xmo.getValuesTree($.xpaths.stats)
$.xmo.getValuesTree($.xpaths.technicalLogFast)
$.xmo.getValuesTree($.xpaths.trafficStats)
$.xmo.getValuesTree($.xpaths.voice)
$.xmo.getValuesTree($.xpaths.wan)
$.xmo.getValuesTree($.xpaths.wifi)
$.xmo.getValuesTree($.xpaths.wifiBandSteering)
$.xmo.getValuesTree($.xpaths.wifiRestoreDefault)
$.xmo.getValuesTree($.xpaths.wizard)
```

Some other intresting links without any required login you can visit 
there is tons of settings to enable to get a really powerful router. 

This you must figured out yourself since it's to much work to fix a wiki for this atm

```javascript
$.xmo.getValuesTree("Device\/DeviceInfo\/GUIFirmwareVersion/*")
$.xmo.getValuesTree("Device\/DeviceInfo\/HardwareVersion/*")
$.xmo.getValuesTree("Device\/DeviceInfo\/MACAddress/*")
$.xmo.getValuesTree("Device\/DeviceInfo\/SerialNumber/*")
$.xmo.getValuesTree("Device\/DeviceInfo\/SoftwareVersion/*")
$.xmo.getValuesTree("Device\/DeviceInfo\/UpTime/*")
$.xmo.getValuesTree("Device\/DHCPv4\/Clients\/Client[@uid='1']\/*")
$.xmo.getValuesTree("Device\/DHCPv4\/Server\/Enable/*")
$.xmo.getValuesTree("Device\/DHCPv4\/Server\/Pools\/*")
$.xmo.getValuesTree("Device\/DNS\/Client\/HostName/*")
$.xmo.getValuesTree("Device\/DNS\/Client\/LocalDomains/*")
$.xmo.getValuesTree("Device\/DNS\/Relay\/Forwardings\/*")
$.xmo.getValuesTree("Device\/Ethernet\/Interfaces\/Interface[PHY1]/*")
$.xmo.getValuesTree("Device\/Ethernet\/Interfaces\/Interface[PHY4]/*")
$.xmo.getValuesTree("Device\/Ethernet\/Interfaces\/Interface[@uid='1']/*")
$.xmo.getValuesTree("Device\/Ethernet\/Interfaces\/Interface[@uid='1']\/*")
$.xmo.getValuesTree("Device\/Ethernet\/Interfaces\/Interface[@uid='2']\/*")
$.xmo.getValuesTree("Device\/Ethernet\/Interfaces\/Interface[@uid='3']\/*")
$.xmo.getValuesTree("Device\/Ethernet\/Interfaces\/Interface[@uid='4']/*")
$.xmo.getValuesTree("Device\/Ethernet\/Interfaces\/Interface[@uid='4']\/*")
$.xmo.getValuesTree("Device\/Ethernet\/Interfaces\/Interface[@uid='7']\/*")
$.xmo.getValuesTree("Device\/Ethernet\/Links\/Link[ETHLNK_BR_DATA]/*")
$.xmo.getValuesTree("Device\/Ethernet\/Links\/Link[ETHLNK_BR_GUEST]/*")
$.xmo.getValuesTree("Device\/Ethernet\/Links\/Link[ETHLNK_BR_LAN]/*")
$.xmo.getValuesTree("Device\/Ethernet\/Links\/Link[@uid='1']\/*")
$.xmo.getValuesTree("Device\/Ethernet\/Links\/Link[@uid='2']\/*")
$.xmo.getValuesTree("Device\/Ethernet\/Links\/Link[@uid='3']\/*")
$.xmo.getValuesTree("Device\/Ethernet\/VLANTerminations\/VLANTermination[VLAN_IPTV_CISCO]/*")
$.xmo.getValuesTree("Device\/Ethernet\/VLANTerminations\/VLANTermination[VLAN_MNGT]/*")
$.xmo.getValuesTree("Device\/Ethernet\/VLANTerminations\/VLANTermination[VLAN_TV_UNTAGGED]/*")
$.xmo.getValuesTree("Device\/Ethernet\/VLANTerminations\/VLANTermination[VLAN_VOIP_CISCO]/*")
$.xmo.getValuesTree("Device\/Firewall\/Chains\/Chain[@uid='2']\/*")
$.xmo.getValuesTree("Device\/Firewall\/Chains\/Chain[@uid='3']\/*")
$.xmo.getValuesTree("Device\/Firewall\/Chains\/Chain[@uid='4']\/*")
$.xmo.getValuesTree("Device\/Firewall\/Config/*")
$.xmo.getValuesTree("Device\/Firewall\/RespondToPing/*")
$.xmo.getValuesTree("Device\/Hosts\/Hosts/*")
$.xmo.getValuesTree("Device\/Hosts\/Hosts\/Host[@uid='1']/*")
$.xmo.getValuesTree("Device\/Hosts\/Hosts\/Host[@uid='2']/*")
$.xmo.getValuesTree("Device\/IP\/Interfaces/*")
$.xmo.getValuesTree("Device\/IP\/Interfaces\/Interface[IP_BR_GUEST]/*")
$.xmo.getValuesTree("Device\/IP\/Interfaces\/Interface[IP_BR_LAN]/*")
$.xmo.getValuesTree("Device\/IP\/Interfaces\/Interface[IP_BR_LAN]\/*")
$.xmo.getValuesTree("Device\/IP\/Interfaces\/Interface[IP_DATA]/*")
$.xmo.getValuesTree("Device\/IP\/Interfaces\/Interface[IP_DATA]\/*")
$.xmo.getValuesTree("Device\/IP\/Interfaces\/Interface[IP_IPTV]/*")
$.xmo.getValuesTree("Device\/IP\/Interfaces\/Interface[IP_MNGT]/*")
$.xmo.getValuesTree("Device\/IP\/Interfaces\/Interface[IPTV_UNTAGED]/*")
$.xmo.getValuesTree("Device\/IP\/Interfaces\/Interface[IP_VOIP]/*")
$.xmo.getValuesTree("Device\/IP\/Interfaces\/Interface[@uid='1']\/*")
$.xmo.getValuesTree("Device\/IP\/Interfaces\/Interface[@uid='2']\/*")
$.xmo.getValuesTree("Device\/IP\/Interfaces\/Interface[@uid='3']\/*")
$.xmo.getValuesTree("Device\/IP\/Interfaces\/Interface[@uid='7']\/*")
$.xmo.getValuesTree("Device\/IP\/IPv4Status/*")
$.xmo.getValuesTree("Device\/IP\/IPv6Enable/*")
$.xmo.getValuesTree("Device\/IP\/IPv6Status/*")
$.xmo.getValuesTree("Device\/ManagementServer\/ConnectionRequestPassword/*")
$.xmo.getValuesTree("Device\/ManagementServer\/Password/*")
$.xmo.getValuesTree("Device\/Managers\/NetworkData\/BridgedMode/*")
$.xmo.getValuesTree("Device\/NAT\/InterfaceSettings\/InterfaceSetting[@uid='1']\/*")
$.xmo.getValuesTree("Device\/NAT\/InterfaceSettings\/InterfaceSetting[@uid='2']\/*")
$.xmo.getValuesTree("Device\/NAT\/InterfaceSettings\/InterfaceSetting[@uid='3']\/*")
$.xmo.getValuesTree("Device\/NAT\/PortMappings/*")
$.xmo.getValuesTree("Device\/Routing\/Routers\/Router[DEFAULT]/*")
$.xmo.getValuesTree("Device\/Se/*")
$.xmo.getValuesTree("Device\/Serv/*")
$.xmo.getValuesTree("Device\/Services\/Bandsteering\/Enable/*")
$.xmo.getValuesTree("Device\/Services\/VoiceServices\/VoiceService[@uid='1']\/*")
$.xmo.getValuesTree("Device\/TELIA\/Led\/DimmedMode/*")
$.xmo.getValuesTree("Device\/Time\/CurrentLocalTime/*")
$.xmo.getValuesTree("Device\/Time\/Enable/*")
$.xmo.getValuesTree("Device\/Time\/LocalTimeZone/*")
$.xmo.getValuesTree("Device\/Time\/LocalTimeZoneName/*")
$.xmo.getValuesTree("Device\/Time\/NTPServer1/*")
$.xmo.getValuesTree("Device\/Time\/NTPServer2/*")
$.xmo.getValuesTree("Device\/Time\/Status/*")
$.xmo.getValuesTree("Device\/UPnP\/Device\/UPnPIGD/*")
$.xmo.getValuesTree("Device\/UPnP\/Device\/UPnPMediaServer/*")
$.xmo.getValuesTree("Device\/UPnP\/Settings\/UPnPIGD\/*")
$.xmo.getValuesTree("Device\/UPnP\/Settings\/UPnPMediaServer\/*")
$.xmo.getValuesTree("Device\/USB\/Enable/*")
$.xmo.getValuesTree("Device\/USB\/USBHosts\/Hosts\/*")
$.xmo.getValuesTree("Device\/UserAccounts\/Users\/User[@uid='1']\/*")
$.xmo.getValuesTree("Device\/UserAccounts\/Users\/User[@uid='2']\/*")
$.xmo.getValuesTree("Device\/UserAccounts\/Users\/User[@uid='3']\/*")
$.xmo.getValuesTree("Device\/UserAccounts\/Users\/User[@uid='4']\/*")
$.xmo.getValuesTree("Device\/UserAccounts\/Users\/User[@uid='5']\/*")
$.xmo.getValuesTree("Device\/WebAccesses\/PortTrigger/*")
$.xmo.getValuesTree("Device\/WebAccesses\/WebRestriction/*")
$.xmo.getValuesTree("Device\/WiFi\/AccessPoints\/AccessPoint[@uid='1']/*")
$.xmo.getValuesTree("Device\/WiFi\/AccessPoints\/AccessPoint[@uid='1']\/*")
$.xmo.getValuesTree("Device\/WiFi\/AccessPoints\/AccessPoint[@uid='2']/*")
$.xmo.getValuesTree("Device\/WiFi\/AccessPoints\/AccessPoint[@uid='2']\/*")
$.xmo.getValuesTree("Device\/WiFi\/AccessPoints\/AccessPoint[@uid='3']/*")
$.xmo.getValuesTree("Device\/WiFi\/AccessPoints\/AccessPoint[@uid='3']\/*")
$.xmo.getValuesTree("Device\/WiFi\/AccessPoints\/AccessPoint[@uid='4']/*")
$.xmo.getValuesTree("Device\/WiFi\/AccessPoints\/AccessPoint[@uid='4']\/*")
$.xmo.getValuesTree("Device\/WiFi\/Radios\/Radio[@uid='1']\/*")
$.xmo.getValuesTree("Device\/WiFi\/Radios\/Radio[@uid='2']\/*")
$.xmo.getValuesTree("Device\/WiFi\/SSIDs\/*")
$.xmo.getValuesTree("Device\/WiFi\/SSIDs\/SSID[@uid='1']\/*")
$.xmo.getValuesTree("Device\/WiFi\/SSIDs\/SSID[@uid='2']\/*")
$.xmo.getValuesTree("Device\/WiFi\/SSIDs\/SSID[@uid='3']\/*")
$.xmo.getValuesTree("Device\/WiFi\/SSIDs\/SSID[@uid='4']\/*")
$.xmo.getValuesTree("Device\/WiFi\/SSIDs\/SSID[WL_GUEST]/*")
$.xmo.getValuesTree("Device\/WiFi\/SSIDs\/SSID[WL_GUEST_5G]/*")
$.xmo.getValuesTree("Device\/WiFi\/SSIDs\/SSID[WL_PRIV]/*")
$.xmo.getValuesTree("Device\/WiFi\/SSIDs\/SSID[WL_VIDEO_5G]/*")
$.xmo.setValuesTree("8213d162ea32a3fcfec2aae5538c48e5", "Device/UserAccounts/Users/User[@uid='1']/Password");
$.xmo.setValuesTree("8213d162ea32a3fcfec2aae5538c48e5", "Device/UserAccounts/Users/User[@uid='2']/Password");
$.xmo.setValuesTree("8213d162ea32a3fcfec2aae5538c48e5", "Device/UserAccounts/Users/User[@uid='3']/Password");
$.xmo.setValuesTree("8213d162ea32a3fcfec2aae5538c48e5", "Device/UserAccounts/Users/User[@uid='4']/Password");
$.xmo.setValuesTree("assist", "Device/UserAccounts/Users/User[@uid='1']/ClearTextPassword");
$.xmo.setValuesTree("assist", "Device/UserAccounts/Users/User[@uid='2']/ClearTextPassword");
$.xmo.setValuesTree("assist", "Device/UserAccounts/Users/User[@uid='3']/ClearTextPassword");
$.xmo.setValuesTree("assist", "Device/UserAccounts/Users/User[@uid='4']/ClearTextPassword");
$.xmo.setValuesTree("assist", "Device/UserAccounts/Users/User[@uid='4']/ClearTextPassword");
$.xmo.setValuesTree("true", "Device/UserAccounts/Users/User[@uid='1']/Functionalities[@uid='0']/Writable");
$.xmo.setValuesTree("wuseman", "Device/UserAccounts/Users/User[@uid='1']/SecretQuery");
$.xmo.setValuesTree("wuseman", "Device/UserAccounts/Users/User[@uid='1']/ClearTextPassword");
$.xmo.setValuesTree("true", "Device/UserAccounts/Users/User[@uid='1']/CurrentlyRemoteAccess);
$.xmo.setValuesTree('SuperUser', "Device/UserAccounts/Users/User[@uid='1']/Role");
$.xmo.setValuesTree("internal", "Device/UserAccounts/Users/User[@uid='1']/Profiles/Profile[@uid='1']/Name");
$.xmo.getValuesTree("Device\/WiFi\/AccessPoints\/AccessPoint[@uid='3']\/Security\/ModeEnabled");
$.xmo.getValuesTree("Device\/WiFi\/AccessPoints\/AccessPoint[@uid='3']\/Security\/WEPKey");
$.xmo.getValuesTree("Device\/USB\/USBHosts\/Hosts\/Host[@uid='1']\/Devices");
$.xmo.getValuesTree("Device\/USB\/USBHosts\/Hosts\/Host[@uid='2']\/Devices");
$.xmo.getValuesTree("Device\/WiFi\/SSIDs\/SSID[@uid='3']\/Status");
$.xmo.getValuesTree("Device\/WiFi\/Radios\/Radio[@uid='1']\/OperatingChannelBandwidth");
$.xmo.getValuesTree("Device/WiFi/AccessPoints/AccessPoint[@uid='1']/Security/KeyPassphrase");
$.xmo.getValuesTree("Device/DHCPv4/Server/Pools/Pool[@uid='1']/SubnetMask");
```

## Main configurations is stored in LXC `Telia` dir

```
/telia/lxc/rootfs/etc/hosts
```

## JQuery

```javascript
jQuery.gui = {};
jQuery.gui.api = {};
jQuery.gui.opt = {
  GUI_VERSION_OPT: "0.1",
  GUI_LANGUAGES_OPT: "da:en",
  GUI_DEFAULT_DATAMODEL_OPT: "gtw",
  GUI_DEFAULT_LANG_OPT: "fr",
  GUI_I18N_CGI_OPT: false,
  GUI_SAVE_LOGIN_OPT: true,
  XMO_REMOTE_HOST: "",
  GUI_AJAX_TIMEOUT_OPT: 30,
  GUI_ACTIVATE_GUI_CONSOLE_OPT: false,
  GUI_ACTIVATE_SHA512ENCODE_OPT: 0
};
```


## Serial Console (Bootlog)

![Screnshot](.pics/sagemcim_bootlaoder.gif)

```

----
BTRM
V1.6
PMCS
AFEL
PWRZ
MEML
PMCD
MEMP
CODE
ZBSS
MAIN
CACH
OTP?
OTPP
ROTB
SCBT
NAND
IMG?
IMGL
HDR?
HDRP
MCV?
KEY?
KEYA
MID?
MIDP
MCVA
SBI?
SBIA
PASS
----
HELO
CPU0
PMCM
PMCS
PMCD
CODE
L1CD
MMUI
ZBBS
MAIN
5.0204-1.0.38-162.76
Boot Strap Register:  0x7dfffc2f
DRAM
NVRAM memcfg 0x427
MCB chksum 0xf67f5b05
DDR3-1600 CL11 512MB
PASS
Version cfe-rom: 0.14.12-sec
FPS0
KEY1
BTL?
BTLA
PASS
J2EP


Base: 5.2_04
CFE version 1.0.38-162.76 for BCM963138 (32bit,SP,LE)
Build Date: mardi 7 août 2018, 13:54:07 (UTC+0200) (g601671@rmm-p200156.femto.urd1.local)
Copyright (C) 2000-2015 Broadcom Corporation.
Version cfe-ram: 0.14.12-sec

Boot Strap Register:  0x7dfffc2f
Chip ID: BCM63139_B0, ARM Cortex A9 Dual Core: 1000MHz
Total Memory: 536870912 bytes (512MB)
NAND ECC BCH-4, page size 0x800 bytes, spare size used 64 bytes
NAND flash device: , id 0xadda block 128KB size 262144KB
pmc_init:PMC using DQM mode
ERROR!!! Data pointer greater than total entry size
Board IP address                  : 192.168.1.1
Host IP address                   : 192.168.1.100
Gateway IP address                :
Run from flash/host/tftp (f/h/c)  : f
Default host run file name        : vmlinux
Default host flash file name      : bcm963xx_fs_kernel
Boot delay (0-9 seconds)          : 1
Default host ramdisk file name    :
Default ramdisk store address     :
Default DTB file name             :
Board Id                          : FAST5370e
Number of MAC Addresses (1-64)    : 10
Base MAC Address                  : f8:08:4f:84:21:38
PSI Size (1-128) KBytes           : 128
Enable Backup PSI [0|1]           : 0
System Log Size (0-256) KBytes    : 0
Auxillary File System Size Percent: 0
MC memory allocation (MB)         : 4
TM memory allocation (MB)         : 44
DHD 0 memory allocation (MB)      : 14
DHD 1 memory allocation (MB)      : 7
DHD 2 memory allocation (MB)      : 0
WLan Feature                      : 0x00
Partition 1 Size (MB)             : 0M
Partition 2 Size (MB)             : 0M
Partition 3 Size (MB)             : 0M
Partition 4 Size (MB) (Data)      : 4MB

Initalizing switch low level hardware.
pmc_switch_power_up: Rgmii Tx clock zone1 enable 0 zone2 enable 0.
Software Resetting Switch ... Done.
Waiting MAC port Rx/Tx to be enabled by hardware ...Done
Disable Switch All MAC port Rx/Tx
Initializing UBI and starting U-Boot...
Looking for UBI...
Looking for U-Boot...
Found valid GSDF
We got aes_key1
We got aes_key2 enc
Starting U-Boot from UBI at 0x00080000


U-Boot 2017.09@sc-0.26.2 (Aug 07 2018 - 13:47:19 +0200) sc_f5370e

CPU:   BCM63xx
Model: Sagemcom FAST5370e
DRAM:  512 MiB
NAND:  256 MiB
Using default environment

In:    serial
Out:   serial
Err:   serial

Version: 2017.09@sc-0.26.2-sec

Board: FAST5370e
Mode: secure
ubi0: attaching mtd1
ubi0: scanning is finished
ubi0: attached mtd1 (name "mtd=2", size 8 MiB)
ubi0: PEB size: 131072 bytes (128 KiB), LEB size: 126976 bytes
ubi0: min./max. I/O unit sizes: 2048/2048, sub-page size 2048
ubi0: VID header offset: 2048 (aligned 2048), data offset: 4096
ubi0: good PEBs: 70, bad PEBs: 0, corrupted PEBs: 0
ubi0: user volume: 7, internal volumes: 1, max. volumes count: 128
ubi0: max/mean erase counter: 2/0, WL threshold: 4096, image sequence number: 511933537
ubi0: available PEBs: 28, total reserved PEBs: 42, PEBs reserved for bad PEB handling: 20
ERROR: sc: invalid LAN base MAC address in PP
Net:   brcm_rddeth
sb3: booting 'operational'
coe-aes: Using AES key2.
ubi0: detaching mtd1
ubi0: mtd1 is detached
ubi0: attaching mtd1
ubi0: scanning is finished
ubi0: attached mtd1 (name "mtd=2", size 8 MiB)
ubi0: PEB size: 131072 bytes (128 KiB), LEB size: 126976 bytes
ubi0: min./max. I/O unit sizes: 2048/2048, sub-page size 2048
ubi0: VID header offset: 2048 (aligned 2048), data offset: 4096
ubi0: good PEBs: 70, bad PEBs: 0, corrupted PEBs: 0
ubi0: user volume: 7, internal volumes: 1, max. volumes count: 128
ubi0: max/mean erase counter: 2/0, WL threshold: 4096, image sequence number: 511933537
ubi0: available PEBs: 28, total reserved PEBs: 42, PEBs reserved for bad PEB handling: 20
ubi0: detaching mtd1
ubi0: mtd1 is detached
ubi0: attaching mtd1
ubi0: scanning is finished
ubi0: attached mtd1 (name "mtd=3", size 141 MiB)
ubi0: PEB size: 131072 bytes (128 KiB), LEB size: 126976 bytes
ubi0: min./max. I/O unit sizes: 2048/2048, sub-page size 2048
ubi0: VID header offset: 2048 (aligned 2048), data offset: 4096
ubi0: good PEBs: 1130, bad PEBs: 0, corrupted PEBs: 0
ubi0: user volume: 3, internal volumes: 1, max. volumes count: 128
ubi0: max/mean erase counter: 4456/2898, WL threshold: 4096, image sequence number: 541134384
ubi0: available PEBs: 81, total reserved PEBs: 1049, PEBs reserved for bad PEB handling: 20
sb3: loaded image 'operational' (31262720 bytes) at 0x01000000
sb3: image 'operational' type is 'gsdf'
sb3: image 'operational' signature is OK
## Booting kernel from Legacy Image at 01001000 ...
   Image Name:   scOS SG4T1E000606C (10.333.0)
   Image Type:   ARM Linux Kernel Image (gzip compressed)
   Data Size:    2686976 Bytes = 2.6 MiB
   Load Address: 00008000
   Entry Point:  00008000
   Verifying Checksum ... OK
   Uncompressing Kernel Image ... OK

Starting kernel ...

Booting Linux on physical CPU 0
Initializing cgroup subsys cpuset
Initializing cgroup subsys cpu
Linux version 3.4.11-4.16L.05 (rmm-svce-urd2int04@compil-atr-2) (gcc version 4.6.2 (GCC) ) #1 SMP PREEMPT Thu Sep 10 18:26:17 CET 2020
CPU: ARMv7 Processor [414fc091] revision 1 (ARMv7), cr=10c53c7d
CPU: PIPT / VIPT nonaliasing data cache, VIPT aliasing instruction cache
Machine: BCM963138
Configured DHD pools size (in Bytes): [0]=0xe00000 [1]=0x700000 [2]=0x0
bootconsole [earlycon0] enabled
Memory policy: ECC disabled, Data cache writealloc
creating a MT_MEMORY_NONCACHED device at physical address of 0x0fd00000 to virtual address at 0xcfd00000 with size of 0x300000 byte for DSL
creating a MT_MEMORY_NONCACHED device at physical address of 0x0d000000 to virtual address at 0xcd000000 with size of 0x2c00000 byte for RDPA tm
creating a MT_MEMORY_NONCACHED device at physical address of 0x0cc00000 to virtual address at 0xccc00000 with size of 0x400000 byte for RDPA mc
creating a MT_MEMORY_NONCACHED device at physical address of 0x0be00000 to virtual address at 0xcbe00000 with size of 0xe00000 byte for DHD dhd0
creating a MT_MEMORY_NONCACHED device at physical address of 0x0b600000 to virtual address at 0xcb600000 with size of 0x700000 byte for DHD dhd1
On node 0 totalpages: 112640
free_area_init_node: node 0, pgdat c04ec760, node_mem_map c1000000
  DMA zone: 32 pages used for memmap
  DMA zone: 0 pages reserved
  DMA zone: 4064 pages, LIFO batch:0
  Normal zone: 992 pages used for memmap
  Normal zone: 107552 pages, LIFO batch:31
pmc_init:PMC using DQM mode
pmc_init:4b 3450346 4b004b
L310 cache controller enabled
l2x0: 16 ways, CACHE_ID 0x410000c9, AUX_CTRL 0x6a450000, Cache size: 524288 B
PERCPU: Embedded 7 pages/cpu @c1405000 s5792 r8192 d14688 u32768
pcpu-alloc: s5792 r8192 d14688 u32768 alloc=8*4096
pcpu-alloc: [0] 0 [0] 1
Built 1 zonelists in Zone order, mobility grouping on.  Total pages: 111616
Kernel command line: root=mtd:rootfs earlyprintk debug init=/etc/preinit ro rootfstype=squashfs console=ttyS0,115200 rootfs_offset=0x291800 rootfs_size=0x1b3f000  mtdparts=nand.0:128k(nvram),640k(cfe),8960k(boot),144640k(ubi),-(data) ubi.mtd=ubi,0 part_main=ubi part_boot=boot image_ubivol=operational secure board_type=00030090 oek=04005578 oiv=040056b8
UBI image volume: "operational"
PID hash table entries: 2048 (order: 1, 8192 bytes)
Dentry cache hash table entries: 65536 (order: 6, 262144 bytes)
Inode-cache hash table entries: 32768 (order: 5, 131072 bytes)
allocated 1048576 bytes of page_cgroup
please try 'cgroup_disable=memory' option if you don't want memory cgroups
Memory: 182MB 1MB 1MB 256MB = 440MB total
Memory: 439684k/439684k available, 84604k reserved, 0K highmem
Virtual kernel memory layout:
    vector  : 0xffff0000 - 0xffff1000   (   4 kB)
    fixmap  : 0xfff00000 - 0xfffe0000   ( 896 kB)
    vmalloc : 0xe0800000 - 0xff000000   ( 488 MB)
    lowmem  : 0xc0000000 - 0xe0000000   ( 512 MB)
    modules : 0xbf000000 - 0xc0000000   (  16 MB)
      .text : 0xc0008000 - 0xc048b694   (4622 kB)
      .init : 0xc048c000 - 0xc04ae6a0   ( 138 kB)
      .data : 0xc04b0000 - 0xc04ed2e0   ( 245 kB)
       .bss : 0xc04ed304 - 0xc0523144   ( 216 kB)
Preemptible hierarchical RCU implementation.
        Dump stacks of tasks blocking RCU-preempt GP.
NR_IRQS:256
Cortex A9 MPCORE GIC init
DIST at fc01f000, CPU_IF at fc01e100
map_hw_timer_interrupt,132: interrupt_id 96
map_hw_timer_interrupt,132: interrupt_id 97
map_hw_timer_interrupt,132: interrupt_id 98
map_hw_timer_interrupt,132: interrupt_id 99
sched_clock: 32 bits at 1kHz, resolution 1000000ns, wraps every 4294967295ms
console [ttyS0] enabled, bootconsole disabled
console [ttyS0] enabled, bootconsole disabled
Calibrating delay loop... 1990.65 BogoMIPS (lpj=995328)
pid_max: default: 32768 minimum: 301
Mount-cache hash table entries: 512
--Kernel Config--
  SMP=1
  PREEMPT=1
  DEBUG_SPINLOCK=0
  DEBUG_MUTEXES=0
Initializing cgroup subsys cpuacct
Initializing cgroup subsys memory
Initializing cgroup subsys devices
Initializing cgroup subsys freezer
Initializing cgroup subsys blkio
CPU: Testing write buffer coherency: ok
Broadcom Logger v0.1 Sep 10 2020 18:22:06
Setting up static identity map for 0x36da40 - 0x36da74
CPU1: Booted secondary processor
CPU1: Unknown IPI message 0x1
Brought up 2 CPUs
SMP: Total of 2 processors activated (3981.31 BogoMIPS).
devtmpfs: initialized
NET: Registered protocol family 16
++++ Powering up USB blocks
bcm63xx_pcie: setting resistor calibration value to 0xa
bcm63xx_pcie: applying serdes parameters
PCIE port 0 power-down
bcm63xx_pcie: setting resistor calibration value to 0xa
bcm63xx_pcie: applying serdes parameters
PCIE port 1 link-up
PCI host bridge to bus 0001:00
pci_bus 0001:00: root bus resource [mem 0xa0000000-0xafffffff]
pci 0001:00:00.0: [14e4:6313] type 01 class 0x060400
pci 0001:00:00.0: PME# supported from D0 D3hot
PCI: bus0: Fast back to back transfers disabled
pci 0001:01:00.0: [14e4:4365] type 00 class 0x028000
pci 0001:01:00.0: reg 10: [mem 0x00000000-0x00007fff 64bit]
pci 0001:01:00.0: reg 18: [mem 0x00000000-0x007fffff 64bit]
pci 0001:01:00.0: reg 20: [mem 0x00000000-0x000fffff 64bit pref]
pci 0001:01:00.0: supports D1 D2
pci 0001:00:00.0: Checking PCIe ASPM for vendor 14e4 device 4365
pci 0001:00:00.0: Disabling PCIe ASPM for vendor 14e4 device 4365
PCI: bus1: Fast back to back transfers disabled
pci 0001:00:00.0: BAR 8: assigned [mem 0xa0000000-0xa0bfffff]
pci 0001:00:00.0: BAR 9: assigned [mem 0xa0c00000-0xa0cfffff 64bit pref]
pci 0001:01:00.0: BAR 2: assigned [mem 0xa0000000-0xa07fffff 64bit]
pci 0001:01:00.0: BAR 4: assigned [mem 0xa0c00000-0xa0cfffff 64bit pref]
pci 0001:01:00.0: BAR 0: assigned [mem 0xa0800000-0xa0807fff 64bit]
pci 0001:00:00.0: PCI bridge to [bus 01-01]
pci 0001:00:00.0:   bridge window [mem 0xa0000000-0xa0bfffff]
pci 0001:00:00.0:   bridge window [mem 0xa0c00000-0xa0cfffff 64bit pref]
PCI: enabling device 0001:00:00.0 (0140 -> 0143)
bio: create slab <bio-0> at 0
SCSI subsystem initialized
usbcore: registered new interface driver usbfs
usbcore: registered new interface driver hub
usbcore: registered new device driver usb
bcmhs_spi bcmhs_spi.1: master is unqueued, this is deprecated
skb_free_task created successfully
gbpm_do_work scheduled
BLOG v3.0 Initialized
BLOG Rule v1.0 Initialized
Broadcom IQoS v0.1 Sep 10 2020 18:25:05 initialized
Broadcom GBPM v0.1 Sep 10 2020 18:25:05 initialized
NET: Registered protocol family 8
NET: Registered protocol family 20
Switching to clocksource timer_cs
NET: Registered protocol family 2
IP route cache hash table entries: 4096 (order: 2, 16384 bytes)
TCP established hash table entries: 16384 (order: 5, 131072 bytes)
TCP bind hash table entries: 16384 (order: 5, 196608 bytes)
TCP: Hash tables configured (established 16384 bind 16384)
TCP: reno registered
UDP hash table entries: 256 (order: 1, 8192 bytes)
UDP-Lite hash table entries: 256 (order: 1, 8192 bytes)
NET: Registered protocol family 1
squashfs: version 4.0 (2009/01/31) Phillip Lougher
Registering unionfs 2.6 (for 3.4.103)
jffs2: version 2.2. (NAND) © 2001-2006 Red Hat, Inc.
msgmni has been set to 858
io scheduler noop registered (default)
brd: module loaded
loop: module loaded
Broadcom NAND controller (BrcmNand Controller)
mtd->oobsize=0, mtd->eccOobSize=0
NAND_CS_NAND_XOR=00000000
B4: NandSelect=20000000, nandConfig=26152300, chipSelect=0
brcmnand_read_id: CS0: dev_id=adda9095
After: NandSelect=00000100, nandConfig=26152300
Block size=00020000, erase shift=17
NAND Config: Reg=26152300, chipSize=256 MB, blockSize=128K, erase_shift=11
busWidth=1, pageSize=2048B, page_shift=11, page_mask=000007ff
BrcmNAND mfg ad da Hynix HY27UF082G2A 256MB on CS0

Found NAND on CS0: ACC=c3840010, cfg=26152300, flashId=adda9095, tim1=65424458, tim2=80000e55
BrcmNAND version = 0x80000700 256MB @00000000
brcmnand_scan: B4 nand_select = 00000100
brcmnand_scan: After nand_select = 00000100
handle_acc_control: default CORR ERR threshold  3 bits
ACC: 16 OOB bytes per 512B ECC step; from ID probe: 16
page_shift=11, bbt_erase_shift=17, chip_shift=28, phys_erase_shift=17
Brcm NAND controller version = 7.0 NAND flash size 256MB @10000000
ECC layout=brcmnand_oob_bch4_2k
brcmnand_scan:  mtd->oobsize=64
brcmnand_scan: oobavail=35, eccsize=512, writesize=2048
brcmnand_scan, eccsize=512, writesize=2048, eccsteps=4, ecclevel=4, eccbytes=7
-->brcmnand_default_bbt
brcmnand_default_bbt: bbt_td = bbt_slc_bch4_main_descr
Bad block table Bbt0 not found for chip on CS0
Bad block table 1tbB not found for chip on CS0
Scanning device for bad blocks, options=00008000
brcmnand_reset_corr_threshold: default CORR ERR threshold  3 bits for CS0
-->brcmnand_isbad_raw(offs=ffe0000
Bad block table written to 0x0ffe0000, version 0x01
-->brcmnand_isbad_raw(offs=ffc0000
Bad block table written to 0x0ffc0000, version 0x01
Master size=10000000
rootfs_ofs=0xffffffff, part1ofs=0x00000080, part2ofs=0x0001f600
Part[0] name=bcmfs, size=20000, ofs=0
Part[1] name=bcmfs_update, size=a0000, ofs=20000
Part[2] name=ubi, size=fa40000, ofs=c0000
Part[3] name=data, size=400000, ofs=fb00000
Part[4] name=nvram, size=20000, ofs=0
5 cmdlinepart partitions found on MTD device nand.0
Creating 5 MTD partitions on "nand.0":
0x000000000000-0x000000020000 : "nvram"
0x000000020000-0x0000000c0000 : "cfe"
0x0000000c0000-0x000000980000 : "boot"
0x000000980000-0x0000096c0000 : "ubi"
0x0000096c0000-0x000010000000 : "data"
UBI: attaching mtd3 to ubi0
UBI: physical eraseblock size:   131072 bytes (128 KiB)
UBI: logical eraseblock size:    126976 bytes
UBI: smallest flash I/O unit:    2048
UBI: VID header offset:          2048 (aligned 2048)
UBI: data offset:                4096
UBI: max. sequence number:       3274662
UBI: attached mtd3 to ubi0
UBI: MTD device name:            "ubi"
UBI: MTD device size:            141 MiB
UBI: number of good PEBs:        1130
UBI: number of bad PEBs:         0
UBI: number of corrupted PEBs:   0
UBI: max. allowed volumes:       128
UBI: wear-leveling threshold:    4096
UBI: number of internal volumes: 1
UBI: number of user volumes:     3
UBI: available PEBs:             90
UBI: total number of reserved PEBs: 1040
UBI: number of PEBs reserved for bad PEB handling: 11
UBI: max/mean erase counter: 4456/2898
UBI: image sequence number:  541134384
UBI: background thread "ubi_bgt0d" started, PID 241
Add UBI volume partitions: name=filesystem1
Add UBI volume partitions: name=operational
Creating 3 MTD partitions on "operational":
0x000000000000-0x00000001f000 : "firm_header"
0x00000001f000-0x0000002b0800 : "kernel"
mtd: partition "kernel" doesn't end on an erase block -- force read-only
0x000000291800-0x000001dd0800 : "rootfs"
mtd: partition "rootfs" doesn't start on an erase block boundary -- force read-only
Add UBI volume partitions: name=rescue
tun: Universal TUN/TAP device driver, 1.6
tun: (C) 1999-2004 Max Krasnyansky <maxk@qualcomm.com>
PPP generic driver version 2.4.2
PPP BSD Compression module registered
PPP Deflate Compression module registered
NET: Registered protocol family 24
ehci_hcd: USB 2.0 'Enhanced' Host Controller (EHCI) Driver
ehci_hcd: block sizes: qh 64 qtd 96 itd 160 sitd 96
ehci-platform ehci-platform.0: Generic Platform EHCI Controller
drivers/usb/core/inode.c: creating file 'devices'
drivers/usb/core/inode.c: creating file '001'
ehci-platform ehci-platform.0: new USB bus registered, assigned bus number 1
ehci-platform ehci-platform.0: reset hcs_params 0x1212 dbg=0 cc=1 pcc=2 ordered ports=2
ehci-platform ehci-platform.0: reset hcc_params a026 thresh 2 uframes 256/512/1024 park
ehci-platform ehci-platform.0: park 0
ehci-platform ehci-platform.0: reset command 0080b02  park=3 ithresh=8 period=1024 Reset HALT
ehci-platform ehci-platform.0: irq 105, io mem 0x8000c300
ehci-platform ehci-platform.0: init command 0010005 (park)=0 ithresh=1 period=512 RUN
ehci-platform ehci-platform.0: USB 2.0 started, EHCI 1.00
usb usb1: default language 0x0409
usb usb1: udev 1, busnum 1, minor = 0
usb usb1: New USB device found, idVendor=1d6b, idProduct=0002
usb usb1: New USB device strings: Mfr=3, Product=2, SerialNumber=1
usb usb1: Product: Generic Platform EHCI Controller
usb usb1: Manufacturer: Linux 3.4.11-4.16L.05 ehci_hcd
usb usb1: SerialNumber: ehci-platform.0
usb usb1: usb_probe_device
usb usb1: configuration #1 chosen from 1 choice
usb usb1: adding 1-0:1.0 (config #1, interface 0)
hub 1-0:1.0: usb_probe_interface
hub 1-0:1.0: usb_probe_interface - got id
hub 1-0:1.0: USB hub found
hub 1-0:1.0: 2 ports detected
hub 1-0:1.0: standalone hub
hub 1-0:1.0: individual port power switching
hub 1-0:1.0: individual port over-current protection
hub 1-0:1.0: power on to power good time: 20ms
hub 1-0:1.0: local power source is good
hub 1-0:1.0: enabling power on all ports
drivers/usb/core/inode.c: creating file '001'
ohci_hcd: USB 1.1 'Open' Host Controller (OHCI) Driver
ohci_hcd: block sizes: ed 64 td 64
ohci-platform ohci-platform.0: Generic Platform OHCI Controller
drivers/usb/core/inode.c: creating file '002'
ohci-platform ohci-platform.0: new USB bus registered, assigned bus number 2
ohci-platform ohci-platform.0: created debug files
ohci-platform ohci-platform.0: irq 104, io mem 0x8000c400
ohci-platform ohci-platform.0: OHCI controller state
ohci-platform ohci-platform.0: OHCI 1.0, NO legacy support registers, rh state running
ohci-platform ohci-platform.0: control 0x083 HCFS=operational CBSR=3
ohci-platform ohci-platform.0: cmdstatus 0x00000 SOC=0
ohci-platform ohci-platform.0: intrstatus 0x00000004 SF
ohci-platform ohci-platform.0: intrenable 0x8000005a MIE RHSC UE RD WDH
ohci-platform ohci-platform.0: hcca frame #0027
ohci-platform ohci-platform.0: roothub.a 02000202 POTPGT=2 NPS NDP=2(2)
ohci-platform ohci-platform.0: roothub.b 00000000 PPCM=0000 DR=0000
ohci-platform ohci-platform.0: roothub.status 00008000 DRWE
ohci-platform ohci-platform.0: roothub.portstatus [0] 0x00000100 PPS
ohci-platform ohci-platform.0: roothub.portstatus [1] 0x00000100 PPS
usb usb2: default language 0x0409
usb usb2: udev 1, busnum 2, minor = 128
usb usb2: New USB device found, idVendor=1d6b, idProduct=0001
usb usb2: New USB device strings: Mfr=3, Product=2, SerialNumber=1
usb usb2: Product: Generic Platform OHCI Controller
usb usb2: Manufacturer: Linux 3.4.11-4.16L.05 ohci_hcd
usb usb2: SerialNumber: ohci-platform.0
usb usb2: usb_probe_device
usb usb2: configuration #1 chosen from 1 choice
usb usb2: adding 2-0:1.0 (config #1, interface 0)
hub 2-0:1.0: usb_probe_interface
hub 2-0:1.0: usb_probe_interface - got id
hub 2-0:1.0: USB hub found
hub 2-0:1.0: 2 ports detected
hub 2-0:1.0: standalone hub
hub 2-0:1.0: no power switching (usb 1.0)
hub 2-0:1.0: global over-current protection
hub 2-0:1.0: power on to power good time: 4ms
hub 2-0:1.0: local power source is good
hub 2-0:1.0: no over-current condition exists
hub 2-0:1.0: trying to enable port power on non-switchable hub
drivers/usb/core/inode.c: creating file '001'
uhci_hcd: USB Universal Host Controller Interface driver
xhci-hcd xhci-hcd.0: xHCI Host Controller
drivers/usb/core/inode.c: creating file '003'
xhci-hcd xhci-hcd.0: new USB bus registered, assigned bus number 3
xhci-hcd xhci-hcd.0: irq 106, io mem 0x8000d000
hub 1-0:1.0: state 7 ports 2 chg 0000 evt 0000
usb usb3: default language 0x0409
usb usb3: udev 1, busnum 3, minor = 256
usb usb3: New USB device found, idVendor=1d6b, idProduct=0002
usb usb3: New USB device strings: Mfr=3, Product=2, SerialNumber=1
usb usb3: Product: xHCI Host Controller
usb usb3: Manufacturer: Linux 3.4.11-4.16L.05 xhci-hcd
usb usb3: SerialNumber: xhci-hcd.0
usb usb3: usb_probe_device
usb usb3: configuration #1 chosen from 1 choice
xHCI xhci_add_endpoint called for root hub
xHCI xhci_check_bandwidth called for root hub
usb usb3: adding 3-0:1.0 (config #1, interface 0)
hub 3-0:1.0: usb_probe_interface
hub 3-0:1.0: usb_probe_interface - got id
hub 3-0:1.0: USB hub found
hub 3-0:1.0: 0 ports detected
hub 3-0:1.0: standalone hub
hub 3-0:1.0: individual port power switching
hub 3-0:1.0: individual port over-current protection
hub 3-0:1.0: Single TT
hub 3-0:1.0: TT requires at most 8 FS bit times (666 ns)
hub 3-0:1.0: power on to power good time: 20ms
hub 3-0:1.0: local power source is good
hub 3-0:1.0: enabling power on all ports
drivers/usb/core/inode.c: creating file '001'
xhci-hcd xhci-hcd.0: xHCI Host Controller
drivers/usb/core/inode.c: creating file '004'
xhci-hcd xhci-hcd.0: new USB bus registered, assigned bus number 4
usb usb4: skipped 1 descriptor after endpoint
usb usb4: default language 0x0409
usb usb4: udev 1, busnum 4, minor = 384
usb usb4: New USB device found, idVendor=1d6b, idProduct=0003
usb usb4: New USB device strings: Mfr=3, Product=2, SerialNumber=1
usb usb4: Product: xHCI Host Controller
usb usb4: Manufacturer: Linux 3.4.11-4.16L.05 xhci-hcd
usb usb4: SerialNumber: xhci-hcd.0
usb usb4: usb_probe_device
usb usb4: configuration #1 chosen from 1 choice
xHCI xhci_add_endpoint called for root hub
xHCI xhci_check_bandwidth called for root hub
usb usb4: adding 4-0:1.0 (config #1, interface 0)
hub 4-0:1.0: usb_probe_interface
hub 4-0:1.0: usb_probe_interface - got id
hub 4-0:1.0: USB hub found
hub 4-0:1.0: 2 ports detected
hub 4-0:1.0: standalone hub
hub 4-0:1.0: individual port power switching
hub 4-0:1.0: individual port over-current protection
hub 4-0:1.0: TT requires at most 8 FS bit times (666 ns)
hub 4-0:1.0: power on to power good time: 20ms
hub 4-0:1.0: local power source is good
hub 4-0:1.0: enabling power on all ports
drivers/usb/core/inode.c: creating file '001'
usbcore: registered new interface driver cdc_acm
cdc_acm: USB Abstract Control Model driver for USB modems and ISDN adapters
Initializing USB Mass Storage driver...
usbcore: registered new interface driver usb-storage
USB Mass Storage support registered.
usbcore: registered new interface driver usbserial
usbserial: USB Serial Driver core
brcmboard: brcm_board_init entry
hub 2-0:1.0: state 7 ports 2 chg 0000 evt 0000
DYING GASP IRQ Initialized and Enabled
Serial: BCM63XX driver $Revision: 3.00 $
Magic SysRq with Auxilliary trigger char enabled (type ^ h for list of supported commands)
ttyS0 at MMIO 0xfffe8600 (irq = 64) is a BCM63XX
ttyS1 at MMIO 0xfffe8620 (irq = 65) is a BCM63XX
BPM: tot_mem_size=536870912B (512MB), buf_mem_size <8%> =42949672B (40MB), num of buffers=21304, buf size=2016
Broadcom BPM Module Char Driver v0.1 Sep 10 2020 18:24:15 Registered<244>
GACT probability NOT on
Mirror/redirect action on
u32 classifier
    input device check on
    Actions configured
TCP: cubic registered
Initializing XFRM netlink socket
NET: Registered protocol family 10
IPv6 over IPv4 tunneling driver
NET: Registered protocol family 17
NET: Registered protocol family 15
Initializing MCPD Module
Ebtables v2.0 registered
ebt_time registered
ebt_ftos registered
ebt_wmm_mark registered
L2TP core: blog_l2tp_rcv_check
L2TP core driver, V2.0
PPPoL2TP kernel driver, V2.0
8021q: 802.1Q VLAN Support v1.8
hub 3-0:1.0: state 7 ports 0 chg 0000 evt 0000
VFS: Mounted root (squashfs filesystem) readonly on device 31:9.
devtmpfs: mounted
Freeing init memory: 136K
hub 4-0:1.0: state 7 ports 2 chg 0000 evt 0000
kernel.hotplug = /sbin/mdev
- preinit -
- regular preinit -
- init -
UBIFS: recovery needed
UBIFS: recovery completed
UBIFS: mounted UBI device 0, volume 0, name "filesystem1"
UBIFS: file system size:   40886272 bytes (39928 KiB, 38 MiB, 322 LEBs)
UBIFS: journal size:       2031616 bytes (1984 KiB, 1 MiB, 16 LEBs)
UBIFS: media format:       w4/r0 (latest is w4/r0)
UBIFS: default compressor: lzo
UBIFS: reserved for root:  1931159 bytes (1885 KiB)
UBI: attaching mtd2 to ubi1
UBI: physical eraseblock size:   131072 bytes (128 KiB)
UBI: logical eraseblock size:    126976 bytes
UBI: smallest flash I/O unit:    2048
UBI: VID header offset:          2048 (aligned 2048)
UBI: data offset:                4096
UBI: max. sequence number:       7
UBI: attached mtd2 to ubi1
UBI: MTD device name:            "boot"
UBI: MTD device size:            8 MiB
UBI: number of good PEBs:        70
UBI: number of bad PEBs:         0
UBI: number of corrupted PEBs:   0
UBI: max. allowed volumes:       128
UBI: wear-leveling threshold:    4096
UBI: number of internal volumes: 1
UBI: number of user volumes:     7
UBI: available PEBs:             46
UBI: total number of reserved PEBs: 24
UBI: number of PEBs reserved for bad PEB handling: 2
UBI: max/mean erase counter: 2/0
UBI: image sequence number:  511933537
UBI: background thread "ubi_bgt1d" started, PID 455
Add UBI volume partitions: name=secondaryboot
Add UBI volume partitions: name=secondaryboot-secure
Add UBI volume partitions: name=uboot
Add UBI volume partitions: name=permanent_param
Add UBI volume partitions: name=aes_key1
Add UBI volume partitions: name=aes_key2
Add UBI volume partitions: name=aes_key_operator
unionfs: new lower inode mtime (bindex=1, name=tmp)
bsp_gpio_data: module license 'Proprietary' taints kernel.
Disabling lock debugging due to kernel taint
Driver LED and BUTTON init .....
[HAL-BSP]: kSysButtonManaged[41]: WARNING -> Button name >= Max(9)
[HAL-BSP]: kSysButtonManaged[41]: WARNING -> Button name >= Max(9)
[HAL-BSP]: kSysButtonManaged[41]: WARNING -> Button name >= Max(9)
[HAL-BSP]: kSysButtonManaged[41]: WARNING -> Button name >= Max(9)
[HAL-BSP]: kSysButtonManaged[41]: WARNING -> Button name >= Max(9)
[HAL-BSP]: kSysButtonManaged[41]: WARNING -> Button name >= Max(9)
[HAL-BSP]: kSysButtonManaged[41]: WARNING -> Button name >= Max(9)
[HAL-BSP]: kSysButtonManaged[41]: WARNING -> Button name >= Max(9)
[HAL-BSP]: kSysButtonManaged[41]: WARNING -> Button name >= Max(9)
[HAL-BSP]: kSysButtonManaged[41]: WARNING -> Button name >= Max(9)
[HAL-BSP]: kSysButtonManaged[41]: WARNING -> Button name >= Max(9)
[HAL-BSP]: kSysButtonManaged[41]: WARNING -> Button name >= Max(9)
[HAL-BSP]: kSysButtonManaged[41]: WARNING -> Button name >= Max(9)
[HAL-BSP]: kSysButtonManaged[41]: WARNING -> Button name >= Max(9)
[HAL-BSP]: kSysButtonManaged[41]: WARNING -> Button name >= Max(9)
 Driver LED and BUTTON ok .....
sgcnet: Unknown symbol sgc_on_send_igmp_leave_cb (err 0)
sgcnet: Unknown symbol sgc_on_send_igmp_join_cb (err 0)
sgcnet: Unknown symbol sgc_on_recv_igmp_query_cb (err 0)
Endpoint: endpoint_init entry ( MS 4.16L.04 )
Endpoint: HAL-BSP : bsp board  found ... Fast5370e_TELIA
Endpoint: Try to find table matching with : [BaseBoardId=F@ST_5370 / VoiceBoardId=SI32176] ...
 SUCCESS
Endpoint: endpoint_init COMPLETED
tm_base_addr 0xcd000000, size 46137344, tm_base_addr_phys 0x0d000000
mc_base_addr 0xccc00000, size 4194304, mc_base_addr_phys 0x0cc00000

 RDP TM memory = 44MB, MC memory = 4MB : Max Possible Bufs <15359> of size <2560>; Allocating <7680> bufs; RDP enum <2>
WARNING!RDP reserved memories are wasting 22MB of memory, please adjust your reserved memory size
++++Runner gso_desc_pool created successfully
brcmchipinfo: brcm_chipinfo_init entry
bcmxtmrt: Broadcom BCM3139B0 ATM/PTM Network Device v0.9 Sep 10 2020 17:59:35
Creating CPU ring for queue number 5 with 256 packets descriptor=0xbf7bcef4
 Done initializing Ring 5 Base=0xffdee000 End=0xffdef000 calculated entries= 256 RDD Base=0x00c06000 descriptor=0xbf7bcef4
Creating CPU ring for queue number 6 with 256 packets descriptor=0xbf7bcf40
 Done initializing Ring 6 Base=0xffde6000 End=0xffde7000 calculated entries= 256 RDD Base=0x00c0c000 descriptor=0xbf7bcf40
NBUFF v1.0 Initialized
Initialized fcache state
Broadcom Packet Flow Cache  Char Driver v3.0 Sep 10 2020 17:56:30 Registered<242>
Created Proc FS /procfs/fcache
Broadcom Packet Flow Cache registered with netdev chain
Broadcom Packet Flow Cache learning via BLOG enabled.
[FHW]  pktDbgLvl[0xbf822da4]=0
[FHW]  fhw_construct:
Initialized Fcache HW accelerator layer state
flwStatsThread created
Constructed Broadcom Packet Flow Cache v3.0 Sep 10 2020 17:56:30
bcmxtmcfg: bcmxtmcfg_init entry
adsl: adsl_init entry
pmc_switch_power_up: Rgmii Tx clock zone1 enable 0 zone2 enable 0.

 LINK DOWN IMP Port
Runner Port#0 (Internal MUX Port#2) connects to Crossbar Port#1
Switch Port#3 (Internal MUX Port#0) connects to Crossbar Port#4
Unused MUX Internal Port#1 connects to Crossbar External Port#0
Cross Bar MUX Config : Internal Port 00 maps to External Port 04 <reg_val : 0x0000000c>
Cross Bar MUX Config : Internal Port 01 maps to External Port 00 <reg_val : 0x00000004>
Cross Bar MUX Config : Internal Port 02 maps to External Port 01 <reg_val : 0x00000044>
Broadcom BCM63139B0 Ethernet Network Device v0.1 Sep 10 2020 17:59:29
dgasp: kerSysRegisterDyingGaspHandler: bcmsw registered
++++ disabling GSO on logical_port=0 dev=eth0
eth0: <Int sw port: 0> <Logical : 00> PHY_ID <0x0007f00c : 0x0c> MAC : 00:00:00:00:00:01
eth1: <Ext sw port: 0> <Logical : 08> PHY_ID <0x0007f008 : 0x08> MAC : 00:00:00:00:00:01
eth2: <Ext sw port: 1> <Logical : 09> PHY_ID <0x0007f009 : 0x09> MAC : 00:00:00:00:00:01
eth3: <Ext sw port: 2> <Logical : 10> PHY_ID <0x0007f00a : 0x0a> MAC : 00:00:00:00:00:01
eth4: <Ext sw port: 3> <Logical : 11> PHY_ID <0x0007f00b : 0x0b> MAC : 00:00:00:00:00:01
Ethernet Auto Power Down and Sleep: Enabled
Cross bar port 1 of Int switch port 0; Adv capability change : MII=0x01e1, GMII=0x0f00
Ext switch port 0; Adv capability change : MII=0x01e1, GMII=0x0f00
Ext switch port 1; Adv capability change : MII=0x01e1, GMII=0x0f00
Ext switch port 2; Adv capability change : MII=0x01e1, GMII=0x0f00
Cross bar port 4 of Ext switch port 3; Adv capability change : MII=0x01e1, GMII=0x0f00
All Port Bit Map: 0x0f01: eth0,eth1,eth2,eth3,eth4
   Chip WAN Only Ports 0001, Defined WAN Only Ports 0000, WAN Only Port Result: 0x0001:eth0
   Chip WAN Preffered Ports 0000, Defined WAN Preffered Ports 0000, WAN Preffered Port Result: 0x0000:
   Chip LAN Only Ports 0f00, Defined LAN Only Ports 0000, LAN Only Port Result: 0x0f00:eth1,eth2,eth3,eth4
   WAN/LAN Both Capable Ports 0x0000:
Creating Enet CPU ring for queue number 1 with 512 packets,Descriptor base=ffde0000
 Creating Enet CPU ring for queue number 0 with 512 packets,Descriptor base=ffddc000
 Initialized Runner Host Layer
Initialized Runner Unicast Layer
Initialized Runner L2 Unicast Layer
Initialized Runner Multicast Layer
Broadcom Packet Flow Cache HW acceleration enabled.
Enabled Runner binding to Flow Cache
Initialized Runner Protocol Layer (700)
Broadcom Runner Blog Driver Char Driver v0.1 Sep 10 2020 17:56:31 Registered <3009>
Wifi Forwarding Driver is initialized!
DHD_FKB_POOL size is:1280 and entry size:2016
fkbpool address range: d9c00000 <-> d9e76000
DHD_PKTTAG POOL size is:1280 and entry size:64
dhd_module_init in
dhd_queue_budget = 256
dhd_sta_threshold = 2048
dhd_if_threshold = 65536
no wifi platform data, skip
PCI_PROBE:  bus 1, slot 0,vendor 14E4, device 4365(good PCI location)
dhdpcie_init: can't find adapter info for this chip
PCI: enabling device 0001:01:00.0 (0140 -> 0142)
DHD: dongle ram size is set to 1835008(orig 1835008) at 0x200000
dhd:0: fw path:/etc/wlan/dhd nv path:(null)
Creating CPU ring for queue number 7 with 128 packets descriptor=0xbf7bcf8c
 Done initializing Ring 7 Base=0xffdf3000 End=0xffdf3800 calculated entries= 128 RDD Base=0x00c17000 descriptor=0xbf7bcf8c
RDPA returned tx wakeup reg = <0x80299004>, val = <0x10000000>
RDPA returned rx wakeup reg = <0x8029a004>, val = <0x26000000>
dhd_runner_attach: Rx Offload - Enabled, Ring Size = 1024
dhd_attach: wl0: pre-allocated buffer mode is disabled (allocskbsz=0)
dhd_attach(): thread:dhd_watchdog_thread:2f4 started
dhd_deferred_work_init: work queue initialized
Creating CPU ring for queue number 0 with 1024 packets descriptor=0xbf982714
 Creating CPU ring for queue number 1 with 1024 packets descriptor=0xbf982730
  wfd_bind: Dev wl%d wfd_idx 0 wl_radio_idx 0 Type fkb configured WFD thread wfd0-thrd minQId/maxQId (8/9), status (0) qmask 0x3
Instantiating WFD 0 thread
dhd:0: fw path:/etc/wlan/dhd nv path:(null)
dhd_bus_download_firmware: firmware path=/etc/wlan/dhd, nvram path=
dhdpcie_ramsize_adj: Enter
dhdpcie_ramsize_adj: Adjust dongle RAMSIZE to 0x240000
dhdpcie_download_code_file: download firmware /etc/wlan/dhd/4366c0/rtecdc.bin
wl:srom/otp not programmed, using main memory mapped srom info(wombo board)
wl: ID=pci/1/1/0/
wl: ID=pci/1/1/0/
wl: loading /etc/wlan/bcm43664_map.bin
wl: reading /etc/wlan/bcmcmn_nvramvars.bin, file size=20
wl: reading /etc/wlan/bcm43664_nvramvars.bin, file size=20
Replace or append with internal Mac Address
dhdpcie_bus_write_vars: Download, Upload and compare of NVRAM succeeded.
Unhandled fault: imprecise external abort (0x1406) at 0xe2000000
Internal error: : 1406 [#1] PREEMPT SMP ARM
Modules linked in: dhd(+) init_addr(bfa0b000 - bfa0b2bc), core_addr(bf9a1000 - bf9dbf0c)
 wlemf(P) init_addr(  (null) -   (null)), core_addr(bf98b000 - bf995814)
 wlcsm(P) init_addr(  (null) -   (null)), core_addr(bf986000 - bf986bdc)
 wfd init_addr(  (null) -   (null)), core_addr(bf97f000 - bf98173c)
 nciTMSkmod(P) init_addr(  (null) -   (null)), core_addr(bf931000 - bf94d090)
 pktrunner(P) init_addr(  (null) -   (null)), core_addr(bf8fd000 - bf907208)
 bcm_enet init_addr(  (null) -   (null)), core_addr(bf8d1000 - bf8e8c8c)
 adsldd(P) init_addr(  (null) -   (null)), core_addr(bf843000 - bf8783d4)
 bcmxtmcfg(P) init_addr(  (null) -   (null)), core_addr(bf829000 - bf8334b8)
 pktflow(P) init_addr(  (null) -   (null)), core_addr(bf805000 - bf819f44)
 bcmxtmrtdrv init_addr(  (null) -   (null)), core_addr(bf7fa000 - bf7feee4)
 chipinfo(P) init_addr(  (null) -   (null)), core_addr(bf7f6000 - bf7f6138)
 rdpa_mw init_addr(  (null) -   (null)), core_addr(bf7ed000 - bf7f09ec)
 rdpa(P) init_addr(  (null) -   (null)), core_addr(bf6e0000 - bf742910)
 rdpa_gpl init_addr(  (null) -   (null)), core_addr(bf6d6000 - bf6d73d8)
 bdmf init_addr(  (null) -   (null)), core_addr(bf6aa000 - bf6c0f50)
 endpointdd(PO) init_addr(  (null) -   (null)), core_addr(bf26d000 - bf3c1804)
 fuse init_addr(  (null) -   (null)), core_addr(bf254000 - bf25efd0)
 xt_SKIPLOG init_addr(  (null) -   (null)), core_addr(bf250000 - bf25001c)
 nf_conntrack_netlink init_addr(  (null) -   (null)), core_addr(bf246000 - bf2488d8)
 ip6t_REJECT init_addr(  (null) -   (null)), core_addr(bf242000 - bf242524)
 ip6t_rpfilter init_addr(  (null) -   (null)), core_addr(bf23e000 - bf23e1bc)
 ip6table_raw init_addr(  (null) -   (null)), core_addr(bf23a000 - bf23a0b0)
 ip6_queue init_addr(  (null) -   (null)), core_addr(bf236000 - bf2369cc)
 ip6table_mangle init_addr(  (null) -   (null)), core_addr(bf232000 - bf2321a4)
 ip6table_filter init_addr(  (null) -   (null)), core_addr(bf22e000 - bf22e0cc)
 ip6_tables init_addr(  (null) -   (null)), core_addr(bf228000 - bf229fcc)
 nf_conntrack_ipv6 init_addr(  (null) -   (null)), core_addr(bf223000 - bf223ac4)
 nf_defrag_ipv6 init_addr(  (null) -   (null)), core_addr(bf21e000 - bf21eca0)
 arptable_filter init_addr(  (null) -   (null)), core_addr(bf21a000 - bf21a0b0)
 arpt_mangle init_addr(  (null) -   (null)), core_addr(bf216000 - bf216164)
 arp_tables init_addr(  (null) -   (null)), core_addr(bf210000 - bf211ad8)
 nfnetlink init_addr(  (null) -   (null)), core_addr(bf20c000 - bf20c3c8)
 nf_nat_sip init_addr(  (null) -   (null)), core_addr(bf207000 - bf20805c)
 nf_conntrack_sip init_addr(  (null) -   (null)), core_addr(bf1fe000 - bf200dfc)
 nf_nat_rtsp init_addr(  (null) -   (null)), core_addr(bf1fa000 - bf1fa790)
 nf_conntrack_rtsp init_addr(  (null) -   (null)), core_addr(bf1f5000 - bf1f6114)
 nf_nat_pptp init_addr(  (null) -   (null)), core_addr(bf1f1000 - bf1f13d4)
 nf_conntrack_pptp init_addr(  (null) -   (null)), core_addr(bf1ed000 - bf1ed8e8)
 nf_nat_h323 init_addr(  (null) -   (null)), core_addr(bf1e8000 - bf1e8e28)
 nf_conntrack_h323 init_addr(  (null) -   (null)), core_addr(bf1dc000 - bf1df710)
 nf_nat_proto_gre init_addr(  (null) -   (null)), core_addr(bf1d8000 - bf1d813c)
 nf_conntrack_proto_gre init_addr(  (null) -   (null)), core_addr(bf1d4000 - bf1d46d0)
 nf_nat_tftp init_addr(  (null) -   (null)), core_addr(bf1d0000 - bf1d0058)
 nf_conntrack_tftp init_addr(  (null) -   (null)), core_addr(bf1cc000 - bf1cc17c)
 nf_nat_irc init_addr(  (null) -   (null)), core_addr(bf1c8000 - bf1c8128)
 nf_nat_ftp init_addr(  (null) -   (null)), core_addr(bf1c4000 - bf1c41dc)
 nf_conntrack_irc init_addr(  (null) -   (null)), core_addr(bf1c0000 - bf1c0454)
 nf_conntrack_ftp init_addr(  (null) -   (null)), core_addr(bf1bb000 - bf1bba6c)
 xt_policy init_addr(  (null) -   (null)), core_addr(bf1b7000 - bf1b7500)
 xt_mark init_addr(  (null) -   (null)), core_addr(bf1af000 - bf1af0a8)
 xt_DSCP init_addr(  (null) -   (null)), core_addr(bf1ab000 - bf1ab234)
 xt_dscp init_addr(  (null) -   (null)), core_addr(bf1a7000 - bf1a7118)
 ipt_REDIRECT init_addr(  (null) -   (null)), core_addr(bf19f000 - bf19f0e4)
 ipt_MASQUERADE init_addr(  (null) -   (null)), core_addr(bf19b000 - bf19b4fc)
 iptable_nat init_addr(  (null) -   (null)), core_addr(bf197000 - bf1975d4)
 nf_nat init_addr(  (null) -   (null)), core_addr(bf191000 - bf192b78)
 xt_conntrack init_addr(  (null) -   (null)), core_addr(bf18d000 - bf18d5d8)
 ipt_REJECT init_addr(  (null) -   (null)), core_addr(bf189000 - bf189428)
 xt_TCPMSS init_addr(  (null) -   (null)), core_addr(bf185000 - bf185664)
 xt_LOG init_addr(  (null) -   (null)), core_addr(bf17f000 - bf180904)
 xt_multiport init_addr(  (null) -   (null)), core_addr(bf17b000 - bf17b2a4)
 xt_mac init_addr(  (null) -   (null)), core_addr(bf177000 - bf1770a8)
 xt_limit init_addr(  (null) -   (null)), core_addr(bf173000 - bf17326c)
 iptable_raw init_addr(  (null) -   (null)), core_addr(bf16f000 - bf16f0ec)
 iptable_mangle init_addr(  (null) -   (null)), core_addr(bf16b000 - bf16b184)
 iptable_filter init_addr(  (null) -   (null)), core_addr(bf167000 - bf167108)
 ip_tables init_addr(  (null) -   (null)), core_addr(bf161000 - bf162db4)
 drv_gpio(O) init_addr(  (null) -   (null)), core_addr(bf156000 - bf157428)
 hard_watchdog(PO) init_addr(  (null) -   (null)), core_addr(bf152000 - bf152794)
 bsp_gpio_lkm(O) init_addr(  (null) -   (null)), core_addr(bf127000 - bf12a248)
 ext2 init_addr(  (null) -   (null)), core_addr(bf117000 - bf11ec74)
 xt_state init_addr(  (null) -   (null)), core_addr(bf113000 - bf1130a8)
 nf_conntrack_ipv4 init_addr(  (null) -   (null)), core_addr(bf10c000 - bf10d664)
 nf_defrag_ipv4 init_addr(  (null) -   (null)), core_addr(bf108000 - bf1080d0)
 nf_conntrack init_addr(  (null) -   (null)), core_addr(bf0f7000 - bf0fec94)
 xfs init_addr(  (null) -   (null)), core_addr(bf085000 - bf0dc938)
 hfsplus init_addr(  (null) -   (null)), core_addr(bf06e000 - bf07824c)
 hfs init_addr(  (null) -   (null)), core_addr(bf060000 - bf067c90)
 ext4 init_addr(  (null) -   (null)), core_addr(bf01b000 - bf04c15c)
 jbd2 init_addr(  (null) -   (null)), core_addr(bf009000 - bf0118b8)
 nls_utf8 init_addr(  (null) -   (null)), core_addr(bf005000 - bf005080)
 mbcache init_addr(  (null) -   (null)), core_addr(bf000000 - bf000cb0)

CPU: 0    Tainted: P           O  (3.4.11-4.16L.05 #1)
PC is at dhdpci_bus_read_frames+0x1084/0x1810 [dhd]
LR is at dhdpci_bus_read_frames+0xfd4/0x1810 [dhd]
pc : [<bf9cbb58>]    lr : [<bf9cbaa8>]    psr: 20000013
sp : dc5f9ce8  ip : fc078070  fp : bf9f0c38
r10: 00000000  r9 : 00000003  r8 : 00000000
r7 : 0043fffc  r6 : da059d20  r5 : deaddead  r4 : da6b8000
r3 : f7c5083a  r2 : 000003e8  r1 : 0043fffc  r0 : deaddead
Flags: nzCv  IRQs on  FIQs on  Mode SVC_32  ISA ARM  Segment user
Control: 10c53c7d  Table: 1a5b004a  DAC: 00000015
Process insmod (pid: 754, stack limit = 0xdc5f8270)
Stack: (0xdc5f9ce8 to 0xdc5fa000)
9ce0:                   00000080 00000000 00000001 60000013 df895600 18103000
9d00: 18103000 bf9b18a8 da553200 18103000 00000070 00000000 da059de0 00000070
9d20: da059de0 bf9b18ec 18103000 da070000 004c4b40 00000200 000001ff 000003e8
9d40: 00000001 da6b8000 da07800c bf9f0c38 da07800c 00000000 00000003 00000000
9d60: bf9f0c38 bf9ce828 bf9f0c40 da078000 bf9f0c38 da07800c da07800c bf9c0b84
9d80: bf9f1454 df899000 00000000 bf9f0c38 da059d80 da059de0 da6b8000 bf9dbc3c
9da0: 00004365 c00eae80 df9129a0 da05a848 da05a848 00000000 dc5f9dd0 c00ebb10
9dc0: df8ba3c8 00000000 da059f00 df899060 df899000 00000000 bf9f51e8 bf9f51b8
9de0: c0054318 00000024 bf9f5358 c018f2ac c050b570 bf9f51e8 df899060 00000000
9e00: bf9f51e8 c01a9640 df899060 bf9f51e8 df899094 00000000 bf9f0c38 c01a983c
9e20: bf9f51e8 00000000 c01a97b0 c01a7f9c df8b9e20 df890338 bf9f51e8 c04cfc30
9e40: da059f00 c01a8eac bf9ed5f4 c016fbd8 df8b9dc0 bf9f51e8 bf9f51e8 c04cfc30
9e60: bfa0b000 bf9f0c38 00000024 c01a9acc bf9f51b8 bf9f51e8 c04cfc30 bfa0b000
9e80: bf9f0c38 c018f6f8 00000000 00000003 bf9f51b8 bf9fefa4 bfa0b000 bf9d1550
9ea0: bf9fefa4 00000000 bf9f0c38 00000003 bf9f53a0 bfa0b1b4 dc5f8000 bf9f53a0
9ec0: c04ed320 bfa0b000 00000000 c0008630 00000000 c0094148 dc5f9ed8 bf9f5358
9ee0: bf9f5358 bf9f53a0 00000001 da5aa8a0 00000001 00000024 bf9f5358 c0056250
9f00: bf9f5364 00007fff 00000000 dcb1c400 df52f4d0 00000000 00000124 bf9f5494
9f20: bf9f5364 01b1f038 e1184000 00075b20 e11d8eac e11d8c1b e11df754 000602b0
9f40: 000642d0 00000000 00000000 00000037 00000038 0000002e 00000000 00000012
9f60: 00000000 00000000 00000000 00000000 00000000 00000000 00000000 c009b93c
9f80: 00000003 00075b20 be870e34 00000000 00000080 c0009228 dc5f8000 00000000
9fa0: 00000000 c0009080 00075b20 be870e34 b6e14008 00075b20 01b1f038 01b1f008
9fc0: 00075b20 be870e34 00000000 00000080 00000000 00000000 b6f2df74 00000000
9fe0: be870c30 be870c20 000245a0 b6e97200 a0000010 b6e14008 e1a0300c e1a0200c
[<bf9cbb58>] (dhdpci_bus_read_frames+0x1084/0x1810 [dhd]) from [<bf9ce828>] (dhd_bus_init+0x44/0xd4 [dhd])
[<bf9ce828>] (dhd_bus_init+0x44/0xd4 [dhd]) from [<bf9c0b84>] (dhd_bus_start+0x5c/0x220 [dhd])
[<bf9c0b84>] (dhd_bus_start+0x5c/0x220 [dhd]) from [<bf9dbc3c>] (dhdpcie_pci_probe+0x298/0x568 [dhd])
[<bf9dbc3c>] (dhdpcie_pci_probe+0x298/0x568 [dhd]) from [<c018f2ac>] (pci_device_probe+0x64/0x88)
[<c018f2ac>] (pci_device_probe+0x64/0x88) from [<c01a9640>] (driver_probe_device+0x70/0x1e0)
[<c01a9640>] (driver_probe_device+0x70/0x1e0) from [<c01a983c>] (__driver_attach+0x8c/0x90)
[<c01a983c>] (__driver_attach+0x8c/0x90) from [<c01a7f9c>] (bus_for_each_dev+0x50/0x7c)
[<c01a7f9c>] (bus_for_each_dev+0x50/0x7c) from [<c01a8eac>] (bus_add_driver+0x174/0x234)
[<c01a8eac>] (bus_add_driver+0x174/0x234) from [<c01a9acc>] (driver_register+0x78/0x12c)
[<c01a9acc>] (driver_register+0x78/0x12c) from [<c018f6f8>] (__pci_register_driver+0x44/0xa4)
[<c018f6f8>] (__pci_register_driver+0x44/0xa4) from [<bf9d1550>] (dhdpcie_bus_register+0x24/0xe0 [dhd])
[<bf9d1550>] (dhdpcie_bus_register+0x24/0xe0 [dhd]) from [<bfa0b1b4>] (init_module+0x1b4/0x2bc [dhd])
[<bfa0b1b4>] (init_module+0x1b4/0x2bc [dhd]) from [<c0008630>] (do_one_initcall+0x11c/0x184)
[<c0008630>] (do_one_initcall+0x11c/0x184) from [<c0056250>] (sys_init_module+0xc20/0x18e0)
[<c0056250>] (sys_init_module+0xc20/0x18e0) from [<c0009080>] (ret_fast_syscall+0x0/0x30)
Code: 0afffff6 e5943188 e1530005 0afffff3 (e5943168)
---[ end trace 9e6ff818ffd23534 ]---
Loading PCM shim driver
unionfs: new lower inode mtime (bindex=1, name=dev)
Broadcom 802.1Q VLAN Interface, v0.1
RDPA DS WAN UDP Filter Command Driver
Creating CPU ring for queue number 2 with 256 packets descriptor=0xbf7bce10
 Done initializing Ring 2 Base=0xffde4000 End=0xffde5000 calculated entries= 256 RDD Base=0x00c3e000 descriptor=0xbf7bce10
UBI: attaching mtd4 to ubi2
UBI: physical eraseblock size:   131072 bytes (128 KiB)
UBI: logical eraseblock size:    126976 bytes
UBI: smallest flash I/O unit:    2048
UBI: VID header offset:          2048 (aligned 2048)
UBI: data offset:                4096
UBI: max. sequence number:       1085420
UBI: attached mtd4 to ubi2
UBI: MTD device name:            "data"
UBI: MTD device size:            105 MiB
UBI: number of good PEBs:        834
UBI: number of bad PEBs:         8
UBI: number of corrupted PEBs:   0
UBI: max. allowed volumes:       128
UBI: wear-leveling threshold:    4096
UBI: number of internal volumes: 1
UBI: number of user volumes:     1
UBI: available PEBs:             34
UBI: total number of reserved PEBs: 800
UBI: number of PEBs reserved for bad PEB handling: 8
UBI: max/mean erase counter: 1390/1302
UBI: image sequence number:  2117556516
UBI: background thread "ubi_bgt2d" started, PID 808
Add UBI volume partitions: name=framework
UBIFS: recovery needed
UBIFS: recovery completed
UBIFS: mounted UBI device 2, volume 0, name "framework"
UBIFS: file system size:   98787328 bytes (96472 KiB, 94 MiB, 778 LEBs)
UBIFS: journal size:       4952064 bytes (4836 KiB, 4 MiB, 39 LEBs)
UBIFS: media format:       w4/r0 (latest is w4/r0)
UBIFS: default compressor: lzo
UBIFS: reserved for root:  4665969 bytes (4556 KiB)
Ethernet Auto Power Down and Sleep: Enabled
Energy Efficient Ethernet: Enabled
```

## All available urls on device (incl. hidden ones as default)
```http://192.168.1.1/0.1/gui/js/answering-machine.js
http://192.168.1.1/0.1/gui/js/config.js
http://192.168.1.1/0.1/gui/js/grid.locale-en.js
http://192.168.1.1/0.1/gui/js/gui-api.js
http://192.168.1.1/0.1/gui/js/gui-common.js
http://192.168.1.1/0.1/gui/js/gui-core.js
http://192.168.1.1/0.1/gui/js/gui-widgets.js
http://192.168.1.1/0.1/gui/js/jquery-1.3.2-sc.js
http://192.168.1.1/0.1/gui/js/jquery-1.7.2-sc.js
http://192.168.1.1/0.1/gui/js/jquery-ui-1.7.2.custom.js
http://192.168.1.1/0.1/gui/js/jquery-ui-1.7.3.custom-sc.js
http://192.168.1.1/0.1/gui/js/jquery-ui-1.8.20.custom.js
http://192.168.1.1/0.1/gui/js/jquery-ui.js
http://192.168.1.1/0.1/gui/js/jquery-utils.js
http://192.168.1.1/0.1/gui/js/jquery.cookie.js
http://192.168.1.1/0.1/gui/js/jquery.form.js
http://192.168.1.1/0.1/gui/js/jquery.jcarousel.js
http://192.168.1.1/0.1/gui/js/jquery.jqGrid.js
http://192.168.1.1/0.1/gui/js/jquery.js
http://192.168.1.1/0.1/gui/js/jquery.metadata.js
http://192.168.1.1/0.1/gui/js/jquery.mobile.js
http://192.168.1.1/0.1/gui/js/jquery.printf.js
http://192.168.1.1/0.1/gui/js/jquery.random.js
http://192.168.1.1/0.1/gui/js/jquery.tmpl.js
http://192.168.1.1/0.1/gui/js/json
http://192.168.1.1/0.1/gui/js/json2.js
http://192.168.1.1/0.1/gui/js/libs.js
http://192.168.1.1/0.1/gui/js/md5.js
http://192.168.1.1/0.1/gui/js/scripts.js
http://192.168.1.1/0.1/gui/js/sha512.js
http://192.168.1.1/0.1/gui/js/vendor.js
http://192.168.1.1/0.1/gui/js/xmo.js
http://192.168.1.1/0.1/gui/images/BoB-down-icon-24.png
http://192.168.1.1/0.1/gui/images/BoB-up-icon-24.png
http://192.168.1.1/0.1/gui/images/alert.png
http://192.168.1.1/0.1/gui/images/allow-both.png
http://192.168.1.1/0.1/gui/images/allow-local.png
http://192.168.1.1/0.1/gui/images/allow-remote.png
http://192.168.1.1/0.1/gui/images/app-install-01.png
http://192.168.1.1/0.1/gui/images/app-install-02.png
http://192.168.1.1/0.1/gui/images/arrow.jpg
http://192.168.1.1/0.1/gui/images/arrow_down.png
http://192.168.1.1/0.1/gui/images/barcode-2d.png
http://192.168.1.1/0.1/gui/images/btn-arrow-left-over.svg
http://192.168.1.1/0.1/gui/images/btn-arrow-left.svg
http://192.168.1.1/0.1/gui/images/btn-arrow-right-over.svg
http://192.168.1.1/0.1/gui/images/btn-arrow-right.svg
http://192.168.1.1/0.1/gui/images/btn_arrow.svg
http://192.168.1.1/0.1/gui/images/btn_arrow2.svg
http://192.168.1.1/0.1/gui/images/btn_arrow2_press.svg
http://192.168.1.1/0.1/gui/images/btn_arrow_press.svg
http://192.168.1.1/0.1/gui/images/check-status-hybrid.png
http://192.168.1.1/0.1/gui/images/check-status-no.png
http://192.168.1.1/0.1/gui/images/check-status-other.png
http://192.168.1.1/0.1/gui/images/coloricons-sprite.png
http://192.168.1.1/0.1/gui/images/coloricons-sprite2.png
http://192.168.1.1/0.1/gui/images/conect-05.svg
http://192.168.1.1/0.1/gui/images/conect-06.svg
http://192.168.1.1/0.1/gui/images/disallow-both.png
http://192.168.1.1/0.1/gui/images/disallow-local.png
http://192.168.1.1/0.1/gui/images/disallow-remote.png
http://192.168.1.1/0.1/gui/images/dlna-icon.png
http://192.168.1.1/0.1/gui/images/dot-bg.gif
http://192.168.1.1/0.1/gui/images/download166.png
http://192.168.1.1/0.1/gui/images/downstream.png
http://192.168.1.1/0.1/gui/images/external-link-pink.png
http://192.168.1.1/0.1/gui/images/external-link.png
http://192.168.1.1/0.1/gui/images/fair.gif
http://192.168.1.1/0.1/gui/images/favicon-gomalta.ico
http://192.168.1.1/0.1/gui/images/faviconNone.ico
http://192.168.1.1/0.1/gui/images/get_adobe_flash.png
http://192.168.1.1/0.1/gui/images/get_adobe_shockwave.png
http://192.168.1.1/0.1/gui/images/help-icon.png
http://192.168.1.1/0.1/gui/images/hide-password-icon.png
http://192.168.1.1/0.1/gui/images/ico-bottomNavigation.png
http://192.168.1.1/0.1/gui/images/ico-maintance.svg
http://192.168.1.1/0.1/gui/images/ico-qrcode.svg
http://192.168.1.1/0.1/gui/images/ico-sagencom.svg
http://192.168.1.1/0.1/gui/images/ico-wifi.svg
http://192.168.1.1/0.1/gui/images/icon-add-gcontacts-pink.png
http://192.168.1.1/0.1/gui/images/icon-add-gcontacts.png
http://192.168.1.1/0.1/gui/images/icon-alert-white.png
http://192.168.1.1/0.1/gui/images/icon-arrow.png
http://192.168.1.1/0.1/gui/images/icon-cell-phone.png
http://192.168.1.1/0.1/gui/images/icon-delete.png
http://192.168.1.1/0.1/gui/images/icon-dlna.png
http://192.168.1.1/0.1/gui/images/icon-dropbox.png
http://192.168.1.1/0.1/gui/images/icon-eject.png
http://192.168.1.1/0.1/gui/images/icon-ethernet.png
http://192.168.1.1/0.1/gui/images/icon-export-pink.png
http://192.168.1.1/0.1/gui/images/icon-export.png
http://192.168.1.1/0.1/gui/images/icon-femto.png
http://192.168.1.1/0.1/gui/images/icon-gcontacts-pink.png
http://192.168.1.1/0.1/gui/images/icon-gcontacts.png
http://192.168.1.1/0.1/gui/images/icon-gcontacts2.png
http://192.168.1.1/0.1/gui/images/icon-gdrive.png
http://192.168.1.1/0.1/gui/images/icon-harddrive-white.png
http://192.168.1.1/0.1/gui/images/icon-harddrive.png
http://192.168.1.1/0.1/gui/images/icon-hd.png
http://192.168.1.1/0.1/gui/images/icon-hidden.png
http://192.168.1.1/0.1/gui/images/icon-home-white.svg
http://192.168.1.1/0.1/gui/images/icon-home.png
http://192.168.1.1/0.1/gui/images/icon-home.svg
http://192.168.1.1/0.1/gui/images/icon-import-pink.png
http://192.168.1.1/0.1/gui/images/icon-import.png
http://192.168.1.1/0.1/gui/images/icon-networt-storage.png
http://192.168.1.1/0.1/gui/images/icon-next.svg
http://192.168.1.1/0.1/gui/images/icon-office.png
http://192.168.1.1/0.1/gui/images/icon-partner.png
http://192.168.1.1/0.1/gui/images/icon-pause.svg
http://192.168.1.1/0.1/gui/images/icon-phone.png
http://192.168.1.1/0.1/gui/images/icon-play.svg
http://192.168.1.1/0.1/gui/images/icon-prev.svg
http://192.168.1.1/0.1/gui/images/icon-settings.png
http://192.168.1.1/0.1/gui/images/icon-telephone.png
http://192.168.1.1/0.1/gui/images/icon-voicemail.svg
http://192.168.1.1/0.1/gui/images/icon-wifi0.png
http://192.168.1.1/0.1/gui/images/icon-wifi1.png
http://192.168.1.1/0.1/gui/images/icon-wifi2.png
http://192.168.1.1/0.1/gui/images/icon-wifi3.png
http://192.168.1.1/0.1/gui/images/icon-wifi4.png
http://192.168.1.1/0.1/gui/images/ipv6-logo.png
http://192.168.1.1/0.1/gui/images/loading.gif
http://192.168.1.1/0.1/gui/images/loading2.gif
http://192.168.1.1/0.1/gui/images/loading_dots.gif
http://192.168.1.1/0.1/gui/images/lock.png
http://192.168.1.1/0.1/gui/images/lock.svg
http://192.168.1.1/0.1/gui/images/logo-footer.svg
http://192.168.1.1/0.1/gui/images/logo-sgc-mobile.svg
http://192.168.1.1/0.1/gui/images/logoappstore.png
http://192.168.1.1/0.1/gui/images/logogplay.png
http://192.168.1.1/0.1/gui/images/mass-storage-help.png
http://192.168.1.1/0.1/gui/images/name.svg
http://192.168.1.1/0.1/gui/images/network-map.svg
http://192.168.1.1/0.1/gui/images/off-hook.svg
http://192.168.1.1/0.1/gui/images/on-hook.svg
http://192.168.1.1/0.1/gui/images/order-down.png
http://192.168.1.1/0.1/gui/images/order-up.png
http://192.168.1.1/0.1/gui/images/qrcode.png
http://192.168.1.1/0.1/gui/images/refresh.png
http://192.168.1.1/0.1/gui/images/refresh2-over.png
http://192.168.1.1/0.1/gui/images/refresh2.png
http://192.168.1.1/0.1/gui/images/rubbish7.png
http://192.168.1.1/0.1/gui/images/simple_wait_spinner.svg
http://192.168.1.1/0.1/gui/images/spectrum-greyed.svg
http://192.168.1.1/0.1/gui/images/spectrum-normal.svg
http://192.168.1.1/0.1/gui/images/splash_FU.gif
http://192.168.1.1/0.1/gui/images/sprite-devices.png
http://192.168.1.1/0.1/gui/images/sprite-home.svg
http://192.168.1.1/0.1/gui/images/sprite-machine.svg
http://192.168.1.1/0.1/gui/images/sprite-novo.svg
http://192.168.1.1/0.1/gui/images/sprite.png
http://192.168.1.1/0.1/gui/images/sprite_mobile.svg
http://192.168.1.1/0.1/gui/images/sprite_tree.png
http://192.168.1.1/0.1/gui/images/strong.png
http://192.168.1.1/0.1/gui/images/telia
http://192.168.1.1/0.1/gui/images/test-connection-ok.png
http://192.168.1.1/0.1/gui/images/test-connection.jpg
http://192.168.1.1/0.1/gui/images/upstream.png
http://192.168.1.1/0.1/gui/images/view-password-icon.png
http://192.168.1.1/0.1/gui/images/weak.png
http://192.168.1.1/0.1/gui/images/wps-icon-da.png
http://192.168.1.1/0.1/gui/images/wps-icon.png
http://192.168.1.1/0.1/gui/css/gui-common.css
http://192.168.1.1/0.1/gui/css/gui-core.css
http://192.168.1.1/0.1/gui/css/images
http://192.168.1.1/0.1/gui/css/jquery-ui-1.8.20.custom.css
http://192.168.1.1/0.1/gui/css/jquery-ui.css
http://192.168.1.1/0.1/gui/css/jquery.jqGrid.css
http://192.168.1.1/0.1/gui/css/jquery.mobile.css
http://192.168.1.1/0.1/gui/js/answering-machine.js
http://192.168.1.1/0.1/gui/js/config.js
http://192.168.1.1/0.1/gui/js/grid.locale-en.js
http://192.168.1.1/0.1/gui/js/gui-api.js
http://192.168.1.1/0.1/gui/js/gui-common.js
http://192.168.1.1/0.1/gui/js/gui-core.js
http://192.168.1.1/0.1/gui/js/gui-widgets.js
http://192.168.1.1/0.1/gui/js/jquery-1.3.2-sc.js
http://192.168.1.1/0.1/gui/js/jquery-1.7.2-sc.js
http://192.168.1.1/0.1/gui/js/jquery-ui-1.7.2.custom.js
http://192.168.1.1/0.1/gui/js/jquery-ui-1.7.3.custom-sc.js
http://192.168.1.1/0.1/gui/js/jquery-ui-1.8.20.custom.js
http://192.168.1.1/0.1/gui/js/jquery-ui.js
http://192.168.1.1/0.1/gui/js/jquery-utils.js
http://192.168.1.1/0.1/gui/js/jquery.cookie.js
http://192.168.1.1/0.1/gui/js/jquery.form.js
http://192.168.1.1/0.1/gui/js/jquery.jcarousel.js
http://192.168.1.1/0.1/gui/js/jquery.jqGrid.js
http://192.168.1.1/0.1/gui/js/jquery.js
http://192.168.1.1/0.1/gui/js/jquery.metadata.js
http://192.168.1.1/0.1/gui/js/jquery.mobile.js
http://192.168.1.1/0.1/gui/js/jquery.printf.js
http://192.168.1.1/0.1/gui/js/jquery.random.js
http://192.168.1.1/0.1/gui/js/jquery.tmpl.js
http://192.168.1.1/0.1/gui/js/json
http://192.168.1.1/0.1/gui/js/json2.js
http://192.168.1.1/0.1/gui/js/libs.js
http://192.168.1.1/0.1/gui/js/md5.js
http://192.168.1.1/0.1/gui/js/scripts.js
http://192.168.1.1/0.1/gui/js/sha512.js
http://192.168.1.1/0.1/gui/js/vendor.js
http://192.168.1.1/0.1/gui/js/xmo.js
http://192.168.1.1/0.1/gui/msg/da
http://192.168.1.1/0.1/gui/msg/en
http://192.168.1.1/0.1/gui/styles/app-download.css
http://192.168.1.1/0.1/gui/styles/dev.css
http://192.168.1.1/0.1/gui/styles/fonts
http://192.168.1.1/0.1/gui/styles/lib.css
http://192.168.1.1/0.1/gui/styles/login-malta.css
http://192.168.1.1/0.1/gui/styles/login-telia.css
http://192.168.1.1/0.1/gui/styles/main.css
http://192.168.1.1/0.1/gui/styles/mobile
http://192.168.1.1/0.1/gui/styles/mobile-main.css
http://192.168.1.1/0.1/gui/styles/themes
http://192.168.1.1/0.1/gui/styles/vendor.css
http://192.168.1.1/0.1/gui/views/access-control.dmz-ipv6.html
http://192.168.1.1/0.1/gui/views/access-control.dmz.html
http://192.168.1.1/0.1/gui/views/access-control.firewall.html
http://192.168.1.1/0.1/gui/views/access-control.ipv6-pinholling.html
http://192.168.1.1/0.1/gui/views/access-control.main.html
http://192.168.1.1/0.1/gui/views/access-control.main.wifi.html
http://192.168.1.1/0.1/gui/views/access-control.parental-control.filtering.html
http://192.168.1.1/0.1/gui/views/access-control.parental-control.main.html
http://192.168.1.1/0.1/gui/views/access-control.parental-control.planning.dual.html
http://192.168.1.1/0.1/gui/views/access-control.parental-control.planning.html
http://192.168.1.1/0.1/gui/views/access-control.parental-control.planning.simple.html
http://192.168.1.1/0.1/gui/views/access-control.parental-control.planning.timeslot.html
http://192.168.1.1/0.1/gui/views/access-control.port-forwarding.games-app.html
http://192.168.1.1/0.1/gui/views/access-control.port-forwarding.html
http://192.168.1.1/0.1/gui/views/access-control.port-forwarding.main.html
http://192.168.1.1/0.1/gui/views/access-control.port-forwarding.main.simple.html
http://192.168.1.1/0.1/gui/views/access-control.port-triggering.html
http://192.168.1.1/0.1/gui/views/access-control.portmirror.html
http://192.168.1.1/0.1/gui/views/access-control.remote-access.simple.html
http://192.168.1.1/0.1/gui/views/access-control.smartinterface-rrm.html
http://192.168.1.1/0.1/gui/views/access-control.upnp.html
http://192.168.1.1/0.1/gui/views/access-control.user.html
http://192.168.1.1/0.1/gui/views/access-control.user.simple.html
http://192.168.1.1/0.1/gui/views/android-help.html
http://192.168.1.1/0.1/gui/views/answering-machine.mail-server.html
http://192.168.1.1/0.1/gui/views/answering-machine.main.html
http://192.168.1.1/0.1/gui/views/answering-machine.messages.html
http://192.168.1.1/0.1/gui/views/answering-machine.settings.html
http://192.168.1.1/0.1/gui/views/base-simple-talktalk.html
http://192.168.1.1/0.1/gui/views/base.html
http://192.168.1.1/0.1/gui/views/baseSimple.html
http://192.168.1.1/0.1/gui/views/broad-band.simple.html
http://192.168.1.1/0.1/gui/views/content-sharing.simple.html
http://192.168.1.1/0.1/gui/views/dect.advanced.html
http://192.168.1.1/0.1/gui/views/dect.basic.html
http://192.168.1.1/0.1/gui/views/dect.handset.advanced.html
http://192.168.1.1/0.1/gui/views/dect.handset.handset.html
http://192.168.1.1/0.1/gui/views/dect.handset.main.html
http://192.168.1.1/0.1/gui/views/dect.handset.main.simple.html
http://192.168.1.1/0.1/gui/views/dect.main.html
http://192.168.1.1/0.1/gui/views/ethernet-device.device-info.html
http://192.168.1.1/0.1/gui/views/ethernet-device.dmz.html
http://192.168.1.1/0.1/gui/views/ethernet-device.main.html
http://192.168.1.1/0.1/gui/views/ethernet-device.main.simple.html
http://192.168.1.1/0.1/gui/views/ethernet-device.port-forwarding.main.html
http://192.168.1.1/0.1/gui/views/ethernet-device.port-forwarding.main.simple.html
http://192.168.1.1/0.1/gui/views/ethernet-lan.html
http://192.168.1.1/0.1/gui/views/ethernet.html
http://192.168.1.1/0.1/gui/views/extended-menu.html
http://192.168.1.1/0.1/gui/views/first-access.connection.html
http://192.168.1.1/0.1/gui/views/first-access.end.html
http://192.168.1.1/0.1/gui/views/first-access.html
http://192.168.1.1/0.1/gui/views/first-access.ppp.html
http://192.168.1.1/0.1/gui/views/first-access.user.html
http://192.168.1.1/0.1/gui/views/first-access.wifi.html
http://192.168.1.1/0.1/gui/views/internet-connection-talktalk.html
http://192.168.1.1/0.1/gui/views/internet-connectivity.3g.cellular.html
http://192.168.1.1/0.1/gui/views/internet-connectivity.3g.hsxpalte.html
http://192.168.1.1/0.1/gui/views/internet-connectivity.basic.html
http://192.168.1.1/0.1/gui/views/internet-connectivity.connectionServices.html
http://192.168.1.1/0.1/gui/views/internet-connectivity.docsis.main.html
http://192.168.1.1/0.1/gui/views/internet-connectivity.gpon.html
http://192.168.1.1/0.1/gui/views/internet-connectivity.greTunnel.html
http://192.168.1.1/0.1/gui/views/internet-connectivity.ipv4.html
http://192.168.1.1/0.1/gui/views/internet-connectivity.ipv6Simple.html
http://192.168.1.1/0.1/gui/views/internet-connectivity.main.html
http://192.168.1.1/0.1/gui/views/internet-connectivity.main.simple.html
http://192.168.1.1/0.1/gui/views/internet-connectivity.mapT.html
http://192.168.1.1/0.1/gui/views/internet-connectivity.mptcp.kpi-information.html
http://192.168.1.1/0.1/gui/views/internet-connectivity.mptcp.main.html
http://192.168.1.1/0.1/gui/views/internet-connectivity.mptcp.statistics.html
http://192.168.1.1/0.1/gui/views/internet-connectivity.mptcp.status.html
http://192.168.1.1/0.1/gui/views/internet-connectivity.ppp.html
http://192.168.1.1/0.1/gui/views/internet-connectivity.vlan.html
http://192.168.1.1/0.1/gui/views/lan.main.html
http://192.168.1.1/0.1/gui/views/login-dtag-xdsl.html
http://192.168.1.1/0.1/gui/views/login-dtag.html
http://192.168.1.1/0.1/gui/views/login-get.html
http://192.168.1.1/0.1/gui/views/login-optus.html
http://192.168.1.1/0.1/gui/views/login-simple-comhem.html
http://192.168.1.1/0.1/gui/views/login-tim-v2.html
http://192.168.1.1/0.1/gui/views/login-wizard-tim-v2.html
http://192.168.1.1/0.1/gui/views/login.html
http://192.168.1.1/0.1/gui/views/loginSimple.html
http://192.168.1.1/0.1/gui/views/main-charter-5280.html
http://192.168.1.1/0.1/gui/views/main-comhem.html
http://192.168.1.1/0.1/gui/views/main-malta.html
http://192.168.1.1/0.1/gui/views/main-new.html
http://192.168.1.1/0.1/gui/views/main-simple-talktalk.html
http://192.168.1.1/0.1/gui/views/main-talktalk-simple.html
http://192.168.1.1/0.1/gui/views/main-talktalk.html
http://192.168.1.1/0.1/gui/views/main-telia.html
http://192.168.1.1/0.1/gui/views/main-telus.html
http://192.168.1.1/0.1/gui/views/main.html
http://192.168.1.1/0.1/gui/views/my-devices-simple-talktalk.html
http://192.168.1.1/0.1/gui/views/mynetwork.main.html
http://192.168.1.1/0.1/gui/views/mynetwork.map.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.advanced.options.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.antenna-settings.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.autodimming.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.bridge-mode.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.ddns.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.ddns.simple.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.device-info.arp.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.device-info.configuration.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.device-info.connection.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.device-info.device-info.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.device-info.dhcp-leases.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.device-info.docsis.configuration.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.device-info.docsis.connection.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.device-info.docsis.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.device-info.licenses.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.device-info.main.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.dhcp.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.dns.main.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.dns.server.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.fon.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.lan-ipv6-router.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.led-slider.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.led.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.ledDimmed.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.main.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.maintenance.dsl-line.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.maintenance.first-install.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.maintenance.internet-utilities.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.maintenance.log.main.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.maintenance.main.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.maintenance.mainSimple.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.maintenance.ntp.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.maintenance.reset.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.mass-storage.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.network-configuration.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.simple-main.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.sip-alg.html
http://192.168.1.1/0.1/gui/views/mysagemcombox.walled-garden.html
http://192.168.1.1/0.1/gui/views/partials
http://192.168.1.1/0.1/gui/views/plc.device-info.html
http://192.168.1.1/0.1/gui/views/ploampassword.html
http://192.168.1.1/0.1/gui/views/scheduling.control.html
http://192.168.1.1/0.1/gui/views/scheduling.html
http://192.168.1.1/0.1/gui/views/scheduling.main.html
http://192.168.1.1/0.1/gui/views/services.simple.main.html
http://192.168.1.1/0.1/gui/views/splash-firmware-upgrade.html
http://192.168.1.1/0.1/gui/views/traffic-monitor.main.simple.html
http://192.168.1.1/0.1/gui/views/traffic-monitor.simple.html
http://192.168.1.1/0.1/gui/views/usb-device.device-info.html
http://192.168.1.1/0.1/gui/views/usb-device.main.html
http://192.168.1.1/0.1/gui/views/usb-device.main.simple.html
http://192.168.1.1/0.1/gui/views/webradio.html
http://192.168.1.1/0.1/gui/views/wifi-simple-talktalk.html
http://192.168.1.1/0.1/gui/views/wifi.advanced.html
http://192.168.1.1/0.1/gui/views/wifi.basic.dual.generic.html
http://192.168.1.1/0.1/gui/views/wifi.basic.html
http://192.168.1.1/0.1/gui/views/wifi.environment.main.html
http://192.168.1.1/0.1/gui/views/wifi.environment.scan.html
http://192.168.1.1/0.1/gui/views/wifi.mac-filter.html
http://192.168.1.1/0.1/gui/views/wifi.main.dual.html
http://192.168.1.1/0.1/gui/views/wifi.main.html
http://192.168.1.1/0.1/gui/views/wifi.new-ssid.main.html
http://192.168.1.1/0.1/gui/views/wifi.simple.html
http://192.168.1.1/0.1/gui/views/wifi.simple.main.html
http://192.168.1.1/0.1/gui/views/wifi.ssid.creation.html
http://192.168.1.1/0.1/gui/views/wifi.stats.html
http://192.168.1.1/0.1/gui/views/wifi.wps.html
http://192.168.1.1/0.1/gui/views-mobile/404.html
http://192.168.1.1/0.1/gui/views-mobile/answering-machine.html
http://192.168.1.1/0.1/gui/views-mobile/base.html
http://192.168.1.1/0.1/gui/views-mobile/ethernet-device.device-info.html
http://192.168.1.1/0.1/gui/views-mobile/ethernet-device.main.html
http://192.168.1.1/0.1/gui/views-mobile/guest-access.html
http://192.168.1.1/0.1/gui/views-mobile/login.html
http://192.168.1.1/0.1/gui/views-mobile/main.html
http://192.168.1.1/0.1/gui/views-mobile/maintenance.internet-utilities.html
http://192.168.1.1/0.1/gui/views-mobile/maintenance.main.html
http://192.168.1.1/0.1/gui/views-mobile/maintenance.reset.html
http://192.168.1.1/0.1/gui/views-mobile/my.media.html
http://192.168.1.1/0.1/gui/views-mobile/networkmap-app-phone.html
http://192.168.1.1/0.1/gui/views-mobile/networkmap-app-tablet.html
http://192.168.1.1/0.1/gui/views-mobile/networkmap-app.html
http://192.168.1.1/0.1/gui/views-mobile/parental-control.html
http://192.168.1.1/0.1/gui/views-mobile/qr-code.html
http://192.168.1.1/0.1/gui/views-mobile/status-settings.main.html
http://192.168.1.1/0.1/gui/views-mobile/status-settings.wifi.basic.html
http://192.168.1.1/0.1/gui/views-mobile/status-settings.wifi.main.html
http://192.168.1.1/0.1/gui/views-mobile/status-settings.wifi.sched.html
http://192.168.1.1/0.1/gui/views-mobile/status-settings.wifi.wps.html
http://192.168.1.1/0.1/gui/views-mobile/status-statistics.main.html
http://192.168.1.1/0.1/gui/views-mobile/status-statistics.statistics.html
http://192.168.1.1/0.1/gui/views-mobile/status-statistics.status.html
http://192.168.1.1/0.1/gui/views-mobile/usb-device.device-info.html
http://192.168.1.1/0.1/gui/views-mobile/voice.device-info.html
http://192.168.1.1/0.1/gui/views-mobile/wifi-strength.html
```

## Asking for your help 

* If anyone have found a way to use netcat from newRequest please let me know, 
i have tried everything almost i belive, an example wich works to execute but 
listening other things like admin info and some other things:

```javascript
  $.xmo.client.newRequest("nc", "");

b.Request {client: b.Client, _options: {…}, actions: Array(0), _uploadFiles: _.fn.init(0)}actions: []client: b.Client {_options: {…}, _reqIndex: 32, _pendingRequests: Array(0), 
_connectedPages: Array(0), _sessionId: 4699, …}user: "sagemcom"_connectedPages: []_eventCount: 0_eventId: 1_eventRequest: null_events: {}_ha1: 
"582f7594246a7b16e18102"_hashEncoderPass: "f1b635ef4fadd500448d65"_nonce: "21734245"_options: actionErrorFunc: ƒ (d,e)actionResponseFunc: ƒ (e,d)ajaxErrorFunc: 
ƒ (d)ajaxRetry: falseajaxRetryTimer: 5ajaxTimeout: 30000authenticationErrorFunc: ƒ (d,e)authenticationResponseFunc: ƒ (e,d)autoRequestForEvents: truebasicAuth: falsecookie: 
"session"dataModel: {name: "Internal", nss: Array(1)}getEventsRetryDelay: 15lang: "en"notifyCurrentValue: falsepriority: falserefreshTimer: 5requestErrorFunc: ƒ 
(a,b)requestResponseFunc: ƒ (d)synchronous: false__proto__: Object_pendingRequests: []_reqIndex: 32_sessionId: 420863_proto__: Object_options: {0: "/", 1: "u", 2: "s", 3: "r", 
4: "/", 5: "s", 6: "b", 7: "i", 8: "n", 9: "/", 10: "n", 11: "c", ajaxTimeout: 30000, lang: "en", refreshTimer: 5, basicAuth: false, cookie: "session", …}0: "/"1: "u"2: "s"3: "r"4: 
"/"5: "s"6: "b"7: "i"8: "n"9: "/"10: "n"11: "c"actionErrorFunc: ƒ (d,e)actionResponseFunc: ƒ (e,d)ajaxErrorFunc: ƒ (d)ajaxRetry: falseajaxRetryTimer: 5ajaxTimeout: 
30000authenticationErrorFunc: ƒ (d,e)authenticationResponseFunc: ƒ (e,d)autoRequestForEvents: truebasicAuth: falsecontains: ƒ (str)cookie: "session"dataModel: {name: "Internal", 
nss: Array(1)}getEventsRetryDelay: 15lang: "en"notifyCurrentValue: falsepriority: falserefreshTimer: 5requestErrorFunc: ƒ (a,b)requestResponseFunc: ƒ (d)synchronous: 
false__proto__: Object_uploadFiles: _.fn.init []__proto__: Object

$.xmo.setValuesTree("8213d162ea32a3fcfec2aae5538c48e5", "Device/UserAccounts/Users/User[@uid='1']/Password");
$.xmo.setValuesTree("8213d162ea32a3fcfec2aae5538c48e5", "Device/UserAccounts/Users/User[@uid='2']/Password");
$.xmo.setValuesTree("8213d162ea32a3fcfec2aae5538c48e5", "Device/UserAccounts/Users/User[@uid='3']/Password");
$.xmo.setValuesTree("8213d162ea32a3fcfec2aae5538c48e5", "Device/UserAccounts/Users/User[@uid='4']/Password");
$.xmo.setValuesTree("assist", "Device/UserAccounts/Users/User[@uid='1']/ClearTextPassword");
$.xmo.setValuesTree("assist", "Device/UserAccounts/Users/User[@uid='2']/ClearTextPassword");
$.xmo.setValuesTree("assist", "Device/UserAccounts/Users/User[@uid='3']/ClearTextPassword");
$.xmo.setValuesTree("assist", "Device/UserAccounts/Users/User[@uid='4']/ClearTextPassword");
$.xmo.setValuesTree("assist", "Device/UserAccounts/Users/User[@uid='4']/ClearTextPassword");
$.xmo.setValuesTree("true", "Device/UserAccounts/Users/User[@uid='1']/Functionalities[@uid='0']/Writable");
$.xmo.setValuesTree("wuseman", "Device/UserAccounts/Users/User[@uid='1']/SecretQuery");
$.xmo.setValuesTree("wuseman", "Device/UserAccounts/Users/User[@uid='1']/ClearTextPassword");
$.xmo.setValuesTree("true", "Device/UserAccounts/Users/User[@uid='1']/CurrentlyRemoteAccess);
$.xmo.setValuesTree('SuperUser', "Device/UserAccounts/Users/User[@uid='1']/Role");
$.xmo.setValuesTree("internal", "Device/UserAccounts/Users/User[@uid='1']/Profiles/Profile[@uid='1']/Name");
$.xmo.getValuesTree("Device\/WiFi\/AccessPoints\/AccessPoint[@uid='3']\/Security\/ModeEnabled");
$.xmo.getValuesTree("Device\/WiFi\/AccessPoints\/AccessPoint[@uid='3']\/Security\/WEPKey");
$.xmo.getValuesTree("Device\/USB\/USBHosts\/Hosts\/Host[@uid='1']\/Devices");
$.xmo.getValuesTree("Device\/USB\/USBHosts\/Hosts\/Host[@uid='2']\/Devices");
$.xmo.getValuesTree("Device\/WiFi\/SSIDs\/SSID[@uid='3']\/Status");
$.xmo.getValuesTree("Device\/WiFi\/Radios\/Radio[@uid='1']\/OperatingChannelBandwidth");
$.xmo.getValuesTree("Device/WiFi/AccessPoints/AccessPoint[@uid='1']/Security/KeyPassphrase");
$.xmo.getValuesTree("Device/DHCPv4/Server/Pools/Pool[@uid='1']/SubnetMask");
```
## Donation 

All donations I get I use to buy new devices that I spend all my waking hours 
trying to hack, if it's something unique and something that I'm first with 
I will always share this on my github and NO where else, not even a CVE but 
everything ends up here because I hack for fun and to share everything I 
know for YOU and as always for FREE and under GPLv3. 

```
BTC: bc1q9jzfuwww5me9602y0fsk69lkjhg8svk8h3ejz0
```

## Bonus tip, for the real hackers 

* `http://192.168.1.1/0.1/gui/?item=dhcpdstaticlease.cmd?action=add&mac=MAC:ADDR:HERE&static_ip=192.168.1.1&sessionKey=<session_key>#/`

brrrrrrrz, did you get it? ;-) (if not, no worries - this was added for the curios one)






## Here is some bonus, for fun!

Finally I found all the old pictures and it's been years now since this repo was created. this was worth a 100% CVE. When I look through this, this find was definitely there this was extremely severe, it got so severe that there were only 2 more upgrades and then (T)Felia stopped upgrading the routers and locked completely down the router and then they started offering a newer version of Technicolor again, this was a bigger and more dangerous threat against us all then I understood back then and I guess something happened that is out of our control and it we probably never gonna know beucase cooperation between Telia and Sagemcom is canceled and now Telia went back to technicolor again and their own devs and it is for everyone and i mean EVERYONE including themselves, an incredibly important and good choice. They was taken seriously, thanks telia! They proved to me with this that they take their customers' safety seriously and I have great respect for everyone who works at telia and its subcontractors, I have now instead found flaws with other operators where there is extreme ignorance so this history is now history and I am both happy, proud and extremely satisfied with the results.

Everything in this repo may still be relevant for other internet providers and the firmware they using on their devices worldwide since `Sagemcom` is still cooperates with `Tele2`(comhem) and many many many more internet providers out there  and even if Telia has removed most of the alternatives, mostly things is working the same as before but with less options(for telia customers) due to an upgraded version, so everything I have written here is highly relevant, but because I have already shown, revealed and done what if I can, I will archive this repo from `2022-11-15` and there will be no more upgrades.

Alot has happened since I did this repo in 2018 and did it public in `January, 2019`

Sagemcom has now become become a "mission-driven company" `Since January 2022`: https://www.sagemcom.com/en/group

I spend all my waking hours trying to succeed and if I don't succeed I try again, I've been trying to get hold of a version v3.4.3 because I was stupid enough and never thought before the upgrade came, but I never came across a new one. Here are some pictures for myself to remember these 4 years, I have spent over 600 hours of my free time on this router, here are some random pictures I never shared before but since it is now archived, so here are my 600 hours in pictures shown.

## Approx ~430 hours later and four years and all time I spent on this router I have learned:

``` bash
1) During these 4 years I bought 9 routers to find one with firmware 
   ´v3.4.3´ after the major upgrade, without luck..

2) During this period I was used 7 differnet serial tools for reading data

3) During this period I really know how dangerous it can be to try things 
   without be VERY careful and reading datasheets,  i even managed to set the router on fire (FOR REAL)

4) I tried so many things that would make anyone to think im crazy, 
  but during this time I found a way to bypass auth if serial console is protected 
  by password and it works on other devices as well, this is my secret but I don't 
  regret spending so many hours on this router, in my solitude ;)

5) During this period I asked support 12 times if there is a 'back door' 
  into my home for whatever reason? I got the answer NO out of 11 out of 12 in 
  my internet operator's support for answers. I now know that support cannot 
  be trusted and their knowledge of their own devices is zero.

6) I'll let all the pictures speak for themselves, what's not included 
   here probably isn't worth knowing..
   
   Save yourself from bricking/disassemble the device if you don't really want to, 
   you'll see most of what's on the router below.
```

## Secret connector

 Did you know there is a hidden and 'secret' connector under the aluminum case on the 'front side' of the board?

* When I mention 'front' side of the board it is this side of the board

![PXL_20211022_092146149](https://user-images.githubusercontent.com/26827453/202089140-8fbef78c-8381-44aa-af2e-1edf4d9b693a.jpg)

* When I mention 'back' side of the board it is this side of the board

![Screenshot_20221116_072307](https://user-images.githubusercontent.com/26827453/202100395-1aa6b76b-81bf-4cb2-914a-ba977049f32b.png)

* The secret/hidden (not in even in manual it's listed) connector is on the 'front side' of the router board

![IMG_20220116_002359](https://user-images.githubusercontent.com/26827453/202090160-4c1a51ef-7a86-4405-acf0-ed556dcba091.jpg)
![IMG_20220116_002413](https://user-images.githubusercontent.com/26827453/202090161-151e180c-8af3-4b6c-b254-6362ac8c9c5d.jpg)
![IMG_20220116_002416](https://user-images.githubusercontent.com/26827453/202090163-aadc435c-bed7-4701-a1e4-60e6ec9e998f.jpg)
![IMG_20220116_002419](https://user-images.githubusercontent.com/26827453/202090167-94488a94-ded6-4610-afda-28d48816b3cd.jpg)
![IMG_20220116_002427](https://user-images.githubusercontent.com/26827453/202090168-0606beee-8f77-436e-88b4-672014e486c9.jpg)

![Screenshot_20221116_072307](https://user-images.githubusercontent.com/26827453/202102035-7c588ddd-4f66-40f0-a7c5-ac162a1f61e6.png)
![Screenshot_20221116_072638](https://user-images.githubusercontent.com/26827453/202101976-f20bdd4d-a992-48c3-ad0d-0fe9cfdedf50.png)

Under the aluminum case on 'backside' of this board the broadcom chip is found

![Screenshot_20221116_073703](https://user-images.githubusercontent.com/26827453/202103423-cf4a390e-277c-4bb5-aac5-d5bb91404641.png)
![IMG_20220116_010234](https://user-images.githubusercontent.com/26827453/202090285-50756bab-d3a2-4864-b736-4a5c6e33482d.jpg)
![IMG_20220116_010238](https://user-images.githubusercontent.com/26827453/202090291-93fe6f86-65cc-4a3a-aeba-d0e17f21a493.jpg)

During this period I documented a lot I never told or have told, 
here you can see how I did, what I did, how I work, how extremely 
determined to succeed I am when it comes to hacking devices for fun

These photos I took to remember RX/TX/GND to NOT come when v3.3 on the first router.

![PXL_20211126_232927539 PORTRAIT](https://user-images.githubusercontent.com/26827453/202092114-5b3887ac-0b7e-461c-b97b-6553cbce831c.jpg)
![PXL_20211126_232910051](https://user-images.githubusercontent.com/26827453/202092151-d0a839c6-2dbc-496b-94b0-24dc738eea44.jpg)
![PXL_20211126_232527185](https://user-images.githubusercontent.com/26827453/202092337-65277804-9cd4-4064-8861-55c3907dc14b.jpg)
![PXL_20211126_232529791](https://user-images.githubusercontent.com/26827453/202092346-a077f469-565f-44b3-995d-580a86a25dfd.jpg)
![PXL_20211126_232534970 (1)](https://user-images.githubusercontent.com/26827453/202092348-1782992f-037a-4582-b1c6-d73c5cd5b3a1.jpg)
![PXL_20211126_232910051](https://user-images.githubusercontent.com/26827453/202092352-1a603472-4a8b-4e15-9c5a-1b0091242476.jpg)

Here is serial console when I was forcefully "yanking" two capacitors away on 1 of the 9 routers to see what happens at different 
  "damages" to a device to know what different things are due to if there are "failures" in the future on other devices
  so this is NOT because  because a wrong baudrate of course, it was a "let's fuck this router and see what happens" time

https://user-images.githubusercontent.com/26827453/202096875-354674e4-ae9c-4690-9650-7c8ced71338a.mp4

Just another device and other tools for trying AGAIN to hack the last firmware release 
  after few months with a break for get motivation back again for trying get root access on latest firmware `v4.**`

![PXL_20211027_190253660](https://user-images.githubusercontent.com/26827453/202093360-798581c0-2cce-4645-bb62-c6026f38d600.jpg)
![PXL_20211027_190259295](https://user-images.githubusercontent.com/26827453/202093363-220359fd-3b09-41fd-858a-da44961c4e0c.jpg)
![PXL_20211027_190301283](https://user-images.githubusercontent.com/26827453/202093365-452818b4-15f6-45a8-9a02-e75d5662e75e.jpg)

Same as above but just another device of the same model and firmware and A new ft232dl reader since I experimenting 
 with "crazy" things and the serial readers gets and these devices break extremely easily if you guess pins etc 
 and if you are NEW to hardware hacking want to try the same things if you get insperation. Always read the manual, 
 datasheets and measure the points and don't take chances it will end in disaster. It is impossible to GUESS 
 unless there is clearly what is what on the devices, *BE CAREFUL*!!
 
![PXL_20210922_130435544](https://user-images.githubusercontent.com/26827453/202093672-9cd73222-6bf7-4955-8150-e0c3ee9e6d22.jpg)

This was 4 Years _after_ this repo was created and I still was not able to get root access on latest firmware :(

![1](https://user-images.githubusercontent.com/26827453/202099558-e6939525-f49e-4472-a4f1-4ce0a3b4377a.jpg)
![3](https://user-images.githubusercontent.com/26827453/202099561-fb485649-748f-47c3-a003-7132e557d35d.jpg)

I have a large collection on all devices and hardware that I have managed to hack in my own way. Here is the current router in the list. All the others I throw away or give away to whoever needs them as I don't use these myself. J

Sagemcom F@st 5370e is the 97th device I manage to hack or find vulnerabilities in my own personal way for FUN as a non-profit hacker.

![Screenshot_20221116_070306](https://user-images.githubusercontent.com/26827453/202099355-92abde81-4acb-4520-833f-6aab3d32240a.png)
![Screenshot_20221116_071524](https://user-images.githubusercontent.com/26827453/202099359-857bc4ad-ba76-4fd5-a1f0-36876043713f.png)
![Screenshot_20221116_075818](https://user-images.githubusercontent.com/26827453/202108874-696e121d-f74a-4a4e-9555-40309a612b81.png)

4 of 9 different routers I found, I really worked hard for get root access on this device

![Screenshot_20221116_075552](https://user-images.githubusercontent.com/26827453/202108870-fb37a1be-b77b-4e94-8125-897a380630a1.png)
![Screenshot_20221116_075818](https://user-images.githubusercontent.com/26827453/202109025-8db87775-10c9-4717-bbab-5553cdf636b7.png)
![Screenshot_20221116_080505](https://user-images.githubusercontent.com/26827453/202109252-27382c55-8255-41e5-93ee-47db124b467f.png)
![Screenshot_20221116_075933](https://user-images.githubusercontent.com/26827453/202108882-b45e20a4-257e-492b-874f-b6d266f27a9d.png)

https://user-images.githubusercontent.com/26827453/202110329-ae0db266-8fb8-458e-b9bb-e5e7d95afef4.mp4
https://user-images.githubusercontent.com/26827453/202110573-13a36b14-809e-49b9-9f09-5bd5689a6b70.mp4
https://user-images.githubusercontent.com/26827453/202109900-83f70bdd-eb68-405a-87b3-2854142d7352.mp4

![Screenshot](https://user-images.githubusercontent.com/26827453/202100149-e55591fb-e75b-409f-8656-135da6e4f230.jpg)

## References/Resources

* https://github.com/ezruneko/masvoz-sagemcom-fast-5355-hacks
* https://github.com/iMicknl/python-sagemcom-api
* https://web.archive.org/web/20190128135420/https://noconroy.net/blog/
* https://forums.whirlpool.net.au/archive/2746904
* https://forum.archive.openwrt.org/viewtopic.php?id=73005
* https://www.dslreports.com/forum/r28188441-Line-Stats-Telnet-Unlock-Tool-for-Sagemcom-2864-V2-00
* https://mega.nz/file/ohMxkArD#JKqV9gd9wBZBRIe_EFPwt0HFqalrdv9fVx72qQqm38A
* https://krishnendu.com/telia-se-router-sagemcom-f-st-5370e-mod/
* https://www.dropbox.com/s/h74terxw9oga8ph/5355.json?dl=0
* https://drive.google.com/file/d/1OcZrsvSmttWvZUOitP0dgtyFBGfHQDQx/view
* https://github.com/electronicayciencia/tr-069-proxy
* 
## Get in Touch

* https://www.nr1.nu 
* https://github.com/wuseman/ 
* https://t.me/wuseman

<h3 align="center">The End!</h3>
