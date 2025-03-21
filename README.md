# ipsec_conf

```bash



Router(config)#license boot module c1900 technology-package securityk9 
Router#
Router#
Router#
Router#
Router#
Router#
Router#
Router#sh ver
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


Router#
Router#
Router#
Router#
Router#
Router#
Router#
Router#
Router#
Router#
Router#
Router#
Router#
Router#
Router#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#
Router(config)#
Router(config)#
Router(config)#acc
Router(config)#access-list ?
  <1-99>     IP standard access list
  <100-199>  IP extended access list
Router(config)#access-list 110 per
Router(config)#access-list 110 permit i
Router(config)#access-list 110 permit i
Router(config)#access-list 110 permit i
Router(config)#access-list 110 permit i
Router(config)#access-list 110 permit i
Router(config)#access-list 110 permit i
Router(config)#access-list 110 permit ip 
Router(config)#access-list 110 permit ip 
Router(config)#access-list 110 permit ip 
Router(config)#access-list 110 permit ip 192.168.1.0 0.0.0.255 192.168.3.0 0.0.0.255
Router(config)#cr
Router(config)#crypto is
Router(config)#crypto isakmp po
Router(config)#crypto isakmp policy 10
Router(config-isakmp)#en
Router(config-isakmp)#encryption a
Router(config-isakmp)#encryption aes ?
  128  128 bit keys.
  192  192 bit keys.
  256  256 bit keys.
  <cr>
Router(config-isakmp)#encryption aes 2
Router(config-isakmp)#encryption aes 256 
Router(config-isakmp)#gro
Router(config-isakmp)#group 5
Router(config-isakmp)#ex
Router(config)#
Router(config)#
Router(config)#
Router(config)#
Router(config)#
Router(config)#
Router(config)#c
Router(config)#c
Router(config)#cry
Router(config)#crypto is
Router(config)#crypto isakmp k
Router(config)#crypto isakmp key ?
  WORD  The UNENCRYPTED (cleartext) user password
Router(config)#crypto isakmp key alma1234 add
Router(config)#crypto isakmp key alma1234 address ?
  A.B.C.D  Peer IP address
  ipv6     define shared key with IPv6 address
Router(config)#crypto isakmp key alma1234 address 10.2.2.2
Router(config)#cr
Router(config)#crypto ip
Router(config)#crypto ipsec tr
Router(config)#crypto ipsec transform-set VPN-SET es
Router(config)#crypto ipsec transform-set VPN-SET es
Router(config)#crypto ipsec transform-set VPN-SET esp
Router(config)#crypto ipsec transform-set VPN-SET esp
Router(config)#crypto ipsec transform-set VPN-SET esp
Router(config)#crypto ipsec transform-set VPN-SET esp-
Router(config)#crypto ipsec transform-set VPN-SET esp-
Router(config)#crypto ipsec transform-set VPN-SET esp-
Router(config)#crypto ipsec transform-set VPN-SET esp-
Router(config)#crypto ipsec transform-set VPN-SET esp-aes esp-sha-hmac
Router(config)#cr
Router(config)#crypto ma
Router(config)#crypto map VPN-MAP 10 ipse
Router(config)#crypto map VPN-MAP 10 ipsec-isakmp 
% NOTE: This new crypto map will remain disabled until a peer
        and a valid access list have been configured.
Router(config-crypto-map)#set pe
Router(config-crypto-map)#set peer 10.2.2.1
Router(config-crypto-map)#set tra
Router(config-crypto-map)#set transform-set VPN-SET 
Router(config-crypto-map)#m
Router(config-crypto-map)#match add
Router(config-crypto-map)#match address 110
Router(config-crypto-map)#i n
Router(config-crypto-map)#in
Router(config-crypto-map)#in
Router(config-crypto-map)#in
Router(config-crypto-map)#int
Router(config-crypto-map)#int
Router(config-crypto-map)#int
Router(config-crypto-map)#int
Router(config-crypto-map)#int
Router(config-crypto-map)#int
Router(config-crypto-map)#int
Router(config-crypto-map)#int
Router(config-crypto-map)#int
Router(config-crypto-map)#int
Router(config-crypto-map)#int
Router(config-crypto-map)#int
Router(config-crypto-map)#int
Router(config-crypto-map)#int
Router(config-crypto-map)#int
Router(config-crypto-map)#int s0/1/0
Router(config-if)#cr
Router(config-if)#crypto m
Router(config-if)#crypto map VPN-MAP
*Jan  3 07:16:26.785: %CRYPTO-6-ISAKMP_ON_OFF: ISAKMP is ON
Router(config-if)#end
Router#
%SYS-5-CONFIG_I: Configured from console by console

Router#
Router#
Router#
Router#cop
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


```
