# network-ethernet-library
Ethernet library designed to simplify handling of the underlying hardware by/from mikroelectrika
Overview:

-This library is designed to simplify handling of the underlying hardware (ENC24J600/ENC28J60 and internal ethernet module on PIC18 and PIC32).
-Network Ethernet ENC24J600/ENC28J60 Library supports :IPv4 protocol, ARP requests, ICMP echo requests, UDP, TCP Stack. (Server/Client),  ARP client with cache, DNS client, UDP client, DHCP client. 
TCP Stack features:
-Improved Stack can handle almost all posible TCP States like: closed, Established, Listen, SYN Sent, SYN Received... In other word, We can open socket, send/received data in packets (as many as We want), and finaly close socket.
-User can define size of Tx bufer which is used session handling. This can be useful because user can choose the amount of RAM he wants to occupy. Of course, smaller Tx bufer means more available RAM and less communication speed (because packets are smaller). Buffer size must be the power of 2 (1, 2, 4, ... 512, ...).
-Multiple sockets are supported, and user can define number of sockets required.
Examples:
-This package contains also simple HTTP_Demo example for each ethernet controller. It's shows how to use the Network Ethernet Library. After programming, board will reply to ARP&ICMP echo requests, to UDP requests on any port (returns the request in upper char with a header made of remote host IP & port number), and to HTTP requests on port 80. 
-Note that web page, which is sent on HTTP request, contains (four) images, and each image use different socket. In this simple demo 5 sockets are defined. 
-Examples are tested in Google-Chrome browser.

New version (1.0.6.1):
-Note: currently, this release is related to ARM compilers. On every next update of our compilers we also will update corresponding package.
-Added support for new TIVA internal ethernet module.
-Added new functions: Net_Ethernet_xxxx_closeSocketTCP, Net_Ethernet_xxxx_bufferFreeSizeTCP, Net_Ethernet_28j60_swReset.
-Fixed bugs.

New version (1.0.5.0):
-New packages for ARM  (mikroC, mikroBasic, mikroPascal) are added. New packages include libraries for external ethernet modules (ENC24J600 and ENC28J60) and for internal ethernet modules for Stellaris and STM.
-24.07.2012. Solved DHCP client bug in library for STM internal module.
-03.11.2012. Package for "mikroC PRO for ARM" has been replaced (because old package had bad .emcl files). Fixed DHCP bug in libraries for internal PIC32 module.-09.01.2013. Library for internal STM Ethernet module is updated. New release of compilers for ARM (ver 3.0.0) requires this update, so please download and reinstall corresponding package.

New version (1.0.4.0):
-New packages for ARM  (mikroC, mikroBasic, mikroPascal), and for PIC32 (mikroPascal, mikroBasic) added.
-Fixed problem on receiveing UDP broadcast messages.
- 28.02.2012. Replaced packages for ARM with packets which was build with new version of ARM compilers (2.00). To use these packets, you need to install 2.00 version of compilers.
- 09.07.2012. Added packages for STM (for ENC24j600 and ENC28j60 ethernet modules).

New version (1.0.3.0):
-New packages for PIC, dsPIC and AVR added (mikroC, mikroBasic, mikroPascal). To use these packages user must install 5.20 (or later) version of our compilers.
-Compared to the previous package version, 1.0.3.0 version do not have timer TCP function, and it is user responsibility to increment Net_Ethernet_xxjxx_userTimerSec variable each second in it's code.

New version (1.0.2.0):
-Network Ethernet Library for AVR added.
-Minor changes have been performed in Network Ethernet Library for dsPIC.

New version (1.0.1.0):
-Network Ethernet Library for Internal PIC32 Ethernet Controller module added. You can download project WebcamSurveillance, which use this library.
-Minor changes were made in Help files.
