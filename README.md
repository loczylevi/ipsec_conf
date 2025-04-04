# ipsec_conf


# R1
```bash

en

license boot module c1900 technology-package securityk9 

sh ver
Cisco IOS Software, C1900 Software (C1900-UNIVERSALK9-M), Version 15.1(4)M4, RELEASE SOFTWARE (fc2)
Technical Support: http://www.cisco.com/techsupport
Copyright (c) 1986-2007 by Cisco Systems, Inc.
Compiled Wed 23-Feb-11 14:19 by pt_team

ROM: System Bootstrap, Version 15.1(4)M4, RELEASE SOFTWARE (fc1)
cisco1941 uptime is 37 seconds
System returned to ROM by power-on
System image file is "flash0:c1900-universalk9-mz.SPA.151-1.M4.bin"
Last reload type: Normal Reload

This product contains cryptographic features and is subject to United
States and local country laws governing import, export, transfer and
use. Delivery of Cisco cryptographic products does not imply
third-party authority to import, export, distribute or use encryption.
Importers, exporters, distributors and users are responsible for
compliance with U.S. and local country laws. By using this product you
agree to comply with applicable laws and regulations. If you are unable
to comply with U.S. and local laws, return this product immediately.

A summary of U.S. laws governing Cisco cryptographic products may be found at:
http://www.cisco.com/wwl/export/crypto/tool/stqrg.html

If you require further assistance please contact us by sending email to
export@cisco.com.
Cisco CISCO1941/K9 (revision 1.0) with 491520K/32768K bytes of memory.
Processor board ID FTX152400KS
2 Gigabit Ethernet interfaces
2 Low-speed serial(sync/async) network interface(s)
DRAM configuration is 64 bits wide with parity disabled.
255K bytes of non-volatile configuration memory.
249856K bytes of ATA System CompactFlash 0 (Read/Write)

License Info:

License UDI:

-------------------------------------------------
Device#   PID                   SN
-------------------------------------------------
*0        CISCO1941/K9          FTX1524RZ0K-


Technology Package License Information for Module:'c1900'

----------------------------------------------------------------
Technology    Technology-package          Technology-package
              Current       Type          Next reboot
-----------------------------------------------------------------
ipbase        ipbasek9      Permanent     ipbasek9
security      securityk9    Evaluation    securityk9
data          disable       None          None

Configuration register is 0x2102

reload
conf t

access-list ?
  <1-99>     IP standard access list
  <100-199>  IP extended access list
Router(config)#access-list 110 permit ip 192.168.1.0 0.0.0.255 192.168.3.0 0.0.0.255



crypto isakmp policy 10
encryption aes ?
  128  128 bit keys.
  192  192 bit keys.
  256  256 bit keys.
  <cr>
encryption aes 256 

group 5
ex
crypto isakmp key ?
  WORD  The UNENCRYPTED (cleartext) user password
crypto isakmp key alma1234 add
crypto isakmp key alma1234 address ?
  A.B.C.D  Peer IP address
  ipv6     define shared key with IPv6 address
crypto isakmp key alma1234 address 10.2.2.2     ! az ip cim az a destination address cél eszköz ip cime lesz
```
### ! az ip cim az a destination address cél eszköz ip cime lesz

```bash
crypto isakmp key alma1234 address 10.2.2.2
```


```bash
crypto ipsec transform-set VPN-SET esp-aes esp-sha-hmac
crypto map VPN-MAP 10 ipsec-isakmp 
% NOTE: This new crypto map will remain disabled until a peer
        and a valid access list have been configured.
set peer 10.2.2.1                                ! az ip cim az a destination address cél eszköz ip cime lesz
```
### ! az ip cim az a destination address cél eszköz ip cime lesz

```bash
set peer 10.2.2.1
```


```bash

set transform-set VPN-SET 
match address 110                 ! ACL cumber i guess

int s0/1/0
crypto map VPN-MAP
*Jan  3 07:16:26.785: %CRYPTO-6-ISAKMP_ON_OFF: ISAKMP is ON
end

copy running-config startup-config 


[OK]
Router#
Router#
Router#
Router#

```

# R2


```bash

Router(config)#
Router(config)#
Router(config)#
Router(config)#
Router(config)#acc
Router(config)#access-list 110 per
Router(config)#access-list 110 permit ip 192.168.3.0 0.0.0.255 192.168.1.0 0.0.0.255
Router(config)#
Router(config)#
Router(config)#cr
Router(config)#crypto i
Router(config)#crypto i
Router(config)#crypto is
Router(config)#crypto isakmp 
Router(config)#crypto isakmp 
Router(config)#crypto isakmp p
Router(config)#crypto isakmp policy 10
Router(config-isakmp)#en
Router(config-isakmp)#encryption 256
                                 ^
% Invalid input detected at '^' marker.
	
Router(config-isakmp)#encryption a
Router(config-isakmp)#encryption aes 2
Router(config-isakmp)#encryption aes 256 
Router(config-isakmp)#au
Router(config-isakmp)#authentication pre-sh
Router(config-isakmp)#authentication pre-share 
Router(config-isakmp)#gro
Router(config-isakmp)#group 5
Router(config-isakmp)#
Router(config-isakmp)#ex
Router(config)#
Router(config)#
Router(config)#
Router(config)#
Router(config)#
Router(config)#crq
Router(config)#crq
Router(config)#cr
Router(config)#crypto is
Router(config)#crypto isakmp k
Router(config)#crypto isakmp key alma1234 add
Router(config)#crypto isakmp key alma1234 address 10.1.1.2
Router(config)#cr
Router(config)#crypto ip
Router(config)#crypto ipsec tr
Router(config)#crypto ipsec transform-set VPN-SET es
Router(config)#crypto ipsec transform-set VPN-SET esp
Router(config)#crypto ipsec transform-set VPN-SET esp-aes es
Router(config)#crypto ipsec transform-set VPN-SET esp-aes esp-sha-hmac
Router(config)#
Router(config)#
Router(config)#cr
Router(config)#crypto m
Router(config)#crypto map VPN-MAP 10 ip
Router(config)#crypto map VPN-MAP 10 ipsec-isakmp 
% NOTE: This new crypto map will remain disabled until a peer
        and a valid access list have been configured.
Router(config-crypto-map)#set pee
Router(config-crypto-map)#set peer 10.1.1.2
Router(config-crypto-map)#set
Router(config-crypto-map)#set tr
Router(config-crypto-map)#set transform-set VPN-SET
Router(config-crypto-map)#ma
Router(config-crypto-map)#match ad
Router(config-crypto-map)#match address 110
Router(config-crypto-map)#
Router(config-crypto-map)#ex
Router(config)#
Router(config)#
Router(config)#
Router(config)#
Router(config)#in
Router(config)#interface s0/1/0
Router(config-if)#?
  bandwidth          Set bandwidth informational parameter
  cdp                CDP interface subcommands
  clock              Configure serial interface clock
  crypto             Encryption/Decryption commands
  custom-queue-list  Assign a custom queue list to an interface
  delay              Specify interface throughput delay
  description        Interface specific description
  encapsulation      Set encapsulation type for an interface
  exit               Exit from interface configuration mode
  fair-queue         Enable Fair Queuing on an Interface
  frame-relay        Set frame relay parameters
  hold-queue         Set hold queue depth
  ip                 Interface Internet Protocol config commands
  ipv6               IPv6 interface subcommands
  keepalive          Enable keepalive
  mtu                Set the interface Maximum Transmission Unit (MTU)
  no                 Negate a command or set its defaults
  ppp                Point-to-Point Protocol
  priority-group     Assign a priority group to an interface
  service-policy     Configure QoS Service Policy
  shutdown           Shutdown the selected interface
  tx-ring-limit      Configure PA level transmit ring limit
  zone-member        Apply zone name
Router(config-if)#
Router(config-if)#
Router(config-if)#
Router(config-if)#
Router(config-if)#
Router(config-if)#
Router(config-if)#cr
Router(config-if)#crypto ?
  map  Assign a Crypto Map
Router(config-if)#crypto m
Router(config-if)#crypto map ?
  WORD  Crypto Map tag
Router(config-if)#crypto map VPN-MAP
*Jan  3 07:16:26.785: %CRYPTO-6-ISAKMP_ON_OFF: ISAKMP is ON
Router(config-if)#co
Router(config-if)#co
Router(config-if)#co
Router(config-if)#ex
Router(config)#
Router(config)#
Router(config)#co
Router(config)#ex
Router#
%SYS-5-CONFIG_I: Configured from console by console

Router#
Router#
Router#
Router#co
Router#co
Router#co
Router#co
Router#copy ru
Router#copy running-config st
Router#copy running-config startup-config 
Destination filename [startup-config]? 
Building configuration...
[OK]
Router#
Router#
Router#
Router#
Router#
Router#
Router#
Router#
Router#
Router#sh
Router#show c
Router#show c
Router#show c
Router#show cr
Router#show crypto 
Router#show crypto ?
  ipsec   Show IPSEC policy
  isakmp  Show ISAKMP
  key     Show long term public keys
  map     Crypto maps
Router#show crypto ip
Router#show crypto ipsec ?
  sa             IPSEC SA table
  transform-set  Crypto transform sets
Router#show crypto ipsec sa

interface: Serial0/1/0
    Crypto map tag: VPN-MAP, local addr 0.0.0.0

   protected vrf: (none)
   local  ident (addr/mask/prot/port): (192.168.3.0/255.255.255.0/0/0)
   remote  ident (addr/mask/prot/port): (192.168.1.0/255.255.255.0/0/0)
   current_peer 10.1.1.2 port 500
    PERMIT, flags={origin_is_acl,}
   #pkts encaps: 0, #pkts encrypt: 0, #pkts digest: 0
   #pkts decaps: 0, #pkts decrypt: 0, #pkts verify: 0
   #pkts compressed: 0, #pkts decompressed: 0
   #pkts not compressed: 0, #pkts compr. failed: 0
   #pkts not decompressed: 0, #pkts decompress failed: 0
   #send errors 0, #recv errors 0

     local crypto endpt.: 0.0.0.0, remote crypto endpt.:10.1.1.2
     path mtu 1500, ip mtu 1500, ip mtu idb Serial0/1/0
     current outbound spi: 0x0(0)

     inbound esp sas:

     inbound ah sas:

     inbound pcp sas:

     outbound esp sas:

     outbound ah sas:

     outbound pcp sas:

Router#
Router#
Router#
Router#
```

# jó javitott connfig

```bash



en 
conf t

license boot module c1900 technology-package securityk9 

end
copy run start
reload


conf t

access-list 170 permit ip 211.193.88.0 0.0.0.255 15.12.25.0 0.0.0.255


crypto isakmp policy 12
 encr aes 256
 authentication pre-share
 group 5
ex


crypto isakmp key sigmakosteszta address 192.168.100.26
crypto ipsec transform-set SIG-MAKOS-TESZTA esp-aes esp-sha-hmac

crypto map SIG-MAKOS-TESZTA 12 ipsec-isakmp 
 set peer 192.168.100.26
 set transform-set SIG-MAKOS-TESZTA
 match address 170
ex


int serial gig0/1
crypto map SIG-MAKOS-TESZTA



```



## kettó darab ipsec tunnel de csak egy interfészen csak egy darab crpyto map lehet igy kell megcsinálni
### ez már plusz opcionális
```bash
crypto map VPN-MAP 10 ipsec-isakmp 
 set peer 192.168.100.17
 set transform-set VPN-SET
 match address 110

crypto map VPN-MAP 20 ipsec-isakmp 
 set peer 192.168.100.26
 set transform-set SIG-MAKOS-TESZTA
 match address 170


interface gig0/1
 crypto map VPN-MAP





```
