# Danny's Digital Packet - Release v0.6.1 on 27/08/2012 #

Link: http://code.google.com/p/ddp/

For license and copyright, please see the LICENSE file.

**Please note the README file in the download will contain more up-to-date information than this wiki page.**


# Notes #

## v0.6.1 - 27th August 2012 ##

  1. DDP now has the concept of broadcast packets, these kind of packets are sent out with no intention of being replied to - they are sent in UDP with the destination callsign "BROADCAST".  They are for informative purposes only - e.g. "Server is going down at 1200GMT", "Power failure at repeater", etc - I'm sure you can find other uses for this as well.  You can enable receiving broadcast packets in your client apps by passing "ignore\_broadcast\_packets = False" to the init() function - by default broadcast packets will be NOT passed to the client apps.
  1. Existing examples updated to ignore broadcast packets since they don't need to deal with those kind of packets.
  1. New example code showing how to send and receive broadcast packets.
  1. All examples now use the builtin library "sqlite3" in Python - don't know why I didn't use this earlier.
  1. DDP is now aimed for Python v2.7 - please update your packages.
  1. Slightly improved the speed of the receivePacket() sub when running in RS-232 mode.
  1. The protocol header and footer have changed - please review the PROTOCOL document.
  1. Packet searching in the receivePacket() is now done backwards to avoid picking multiple partial packets.
  1. DDP logging now shows the date and time including the microseconds.
  1. Improved the speed of receiveRawPacket() and also added extra timing checking when writing data in RS-232 mode.
  1. Improved the logging feature (using my new class "DanLog" - don't forget to copy that Python file as well), please ensure you update the specification files as well if you're upgrading.
  1. All the example code now uses my new logging module.
  1. New flag indicating whether the data should be returned to the client application - for advanced use only.  Please review the PROTOCOL document.  Fax example code has been updated.
  1. Few typos and invalid packet transfer example in the PROTOCOL file - corrected.  Please re-read it.
  1. Experimental FDMDV modem provided by Codec2 - set your datamode to "FDMDV".  Please note that only the TX side is currently implemented and this feature is highly experimental and is only available to Unix-like OSes since the "ossaudiodev" python library is used (not available under Cygwin).  Follow the Codec2 installation instructions in the DDV v0.2.0 README file.
  1. Improved the error logic in receiveDataFromAny() subroutine.
  1. Raw packets are now verified (by default) using the new subroutine validatePacket() before transmission to avoid transmitting bad packets - can be turned off by passing "verify\_packet\_before\_tx = False" to init() subroutine.  This subroutine is part of DDP not the specification modules.
  1. Fixed a bug when running in RS-232 mode where the same packet could be parsed (technically it would fail to be parsed for a reason) until the serial buffer overflows.

## v0.6.0 - 11th February 2012 ##
  1. The specifications have now been split up into separate modules, this allows easier updating as well as adding new specifications without changing the core code.  Remember to copy the specification files if you're upgrading from a previous version.
  1. Introduced a new specification based on the SMS specification which allows binary transfer (specification ID 3).  Please read the PROTOCOL document for more information.
  1. You can now define if you want the logging colour coded, by default it's turned on.
  1. Further improved the transmitter keying code, especially when running under FLDIGI.

## v0.5.4 - 25th January 2012 ##
  1. Introduced a new short message specification (SMS for short) designed to send basic text-only packets.  Please read the PROTOCOL document for more information.
  1. The 7-bit protocol now hex encodes the flags section, same as the new SMS spec.  Please read the PROTOCOL document for more information.
  1. The sequence section in the packet has now been removed from all specifications.  Please read the PROTOCOL document for more information.

## v0.5.3 - 10th January 2012 ##
  1. Improved constructPacket() to use bytearray() for 7-bit specification.
  1. DanRSA()/maximumDataLength() didn't correctly return the max data length if we exceeded 2048-bit, this has been corrected.

## v0.5.2 - 13th October 2011 ##

  1. Packets now have a application ID section, this will prevent your application from processing packets it isn't expecting.  Please review the PROTOCOL document for more information.  The example code have been updated to reflect this new feature.
  1. Corrected an issue where the GUID of the packet ID was checksummed twice.
  1. New example code showing how to send and receive email (mail exchange - MX) using DDP.

## v0.5.1 - 27th August 2011 ##

  1. New example code showing how DDP can be used to proxy XMLRPC traffic.  Should be compatible with all XMLRPC programs including (but not limited to) StormForce XR.  Please note, this isn't quick so increase the "update periods" to 15 minutes (900 seconds) in the SXR client - or better yet use the SXR mini client instead.  The server component sits with the actual XMLRPC host (e.g. SXR server) and the client goes with the XMLRPC client (e.g. SXR client).  Remember to change the client port number and URL to ensure it goes through the proxy.
  1. Introduced packet replay detection, this routine will prevent the exact same packet from re-sent if it has already been processed by DDP.
  1. Ensured when using FLDIGI we unlock the program first before attempting to change parameters.
  1. Callsign verification using RSA public/private key pair signatures.  Read the PROTOCOL document on how this is implemented.  You'll need M2Crypto installed for this to work.
  1. New example code showing how to transfer your RSA public key using DDP.
  1. The crypto (RSA signatures) can be disabled on initialisation.
  1. Allowing unsigned packets can be allowed on initialisation.
  1. Corrected the repeater example code which no longer ran after introducing the TCP ACK timeout in the last version.
  1. Example code XML setting files now reflect the new crypto options.

## v0.5.0 - 12th June 2011 ##

  1. Please note the "ddp.py" file in example directory has been removed.  So if you want to use the examples copy the "ddp.py" file from the parent directory.
  1. DDP logging is now colourised to aid debugging.
  1. PyLZMA has been dropped and has been replaced by GZIP which is built-in to Python.
  1. Improved packet header and footer handling.
  1. Corrected a small issue when running with fldigi, when requesting the bytes it's zero based and I forgot to subtract one off.  This would have caused the odd exception but nothing major.
  1. A seperate timeout for the TCP ACK packet has been added.
  1. EC can be disabled on initialisation.


## v0.4.2 - 29th April 2011 ##

  1. PyPNG is included for parsing PNG files.  Used **with** permission from http://code.google.com/p/pypng/ - Thanks David.
  1. New example code showing how DDP can be used for sending and receiving faxes.  Have a look in the examples directory.  **Please note that only PNG files are supported.**
  1. receiveDataFromAny() routine has been tweaked so it can ignore FIN packets, instead it will just return a single packet.
  1. Few improvements made to the fldigi packet handling code.
  1. When using fldigi the data payload section of the packet is now scrambled, this is to prevent spectral lines.  Previously, scrambling was only done on the 8-bit protocol - now it's also done on the 7-bit protocol but only on the data load section.  Please revise the PROTOCOL document for more information.

## v0.4.1 - 23rd April 2011 ##

  1. Tweaked code to support repeating packets transparently.
  1. Repeater code now released.  Take a look in examples directory.
  1. The default Reed-Solomon coder is now (64,48), which gives a max of 12.5% packet loss.
  1. TCP/IP (UDP) support has been dropped, let's keep this project pure RF.
  1. Base64 de/encoding has now been moved to Base128, should shave off a few bytes of the packet size.
  1. New example code showing how DDP can be used for emergency communications (EmComm).  Have a look in the examples directory.

## v0.4.0 - 2nd April 2011 ##

  1. Changed the way ptt() is handled to reduce dekeying when it isn't necessary.
  1. DDP now has an additional data mode called "EXTENSION", this allows easy extension to the DDP base class - DDV uses this method.
  1. Added more coding for DDV, so far DDV will only work on Unix-like OS'es due to the OSS audio module (ossaudiodev) in Python.  Also due to the Codec2 codec DDV now uses.  This now makes DDP fully aware of DDV, DDV is class extension.
  1. New data mode called "GMSK" for when using a RS-232 GMSK modem, uses same parameters for the RS-232 backend.
  1. If PyLZMA is not available (due to any reason), DDP will automatically switch to the built-in GZIP module instead for it's default compression.
  1. The operating system is now detected on startup and will display any warnings and/or errors when running on that specific OS.
  1. PySerial is no longer a required module.  It's only imported when using the RS-232 backend, so if you only use FLDIGI you no longer need to install PySerial.
  1. Example code has been tidied and includes some extra exception trapping.
  1. Seperated out some of the subroutines for easier overloading and testing.

## v0.3.3 - 5th February 2011 ##

  1. DDP will now show you its license when initialising, just a reminder.
  1. When using Reed-Solomon, interleaving will now be used to improve the correction factor.

## v0.3.2 - 28th December 2010 ##

  1. Tweaked the 8-bit protocol to correctly use the preample.
  1. Includes a few code changes for DDV, but changes aren't 100% complete for DDV.
  1. `*`codeReedSolomon() routines now parses the data in chunks rather than byte-per-byte.  If the chunk is too small it will be padded with "\x00".
  1. The default Reed-Solomon coder is now (64,32), when running in debug mode the N, K, S, and Lmax (not part of Reed-Solomon) values are shown.  Lmax is maximum byte loss shown as a percentage (just thought it was nice to know).  Overheads will now be around 150%.
  1. Reduced the TX hangtime when using fldigi and RS-232.
  1. isTX() routine now uses the RTS state when using RS-232.
  1. New ptt() routine handles keying up the modem over RS-232.


## v0.3.1 - 21st December 2010 ##

  1. 8-bit binary mode now works with fldigi.  HOWEVER, since I can't send the whole 8-bit character set to fldigi the binary data is first encoded in hex before transmitting.  This is a limitation with fldigi, not DDP or PSK.
  1. Default TX wait time is now 500ms.
  1. The packet is now scrambled (using Python's random module) to avoid long streams of zeros, ones, or patterns - notice the word SCRAMBLED not encrypted.  Simple but seems to do the job.  The scrambler only gets used for the 8-bit specification.
  1. Reed-Solomon parity checking now available on the 8-bit protocol and will automatically be used if the "pyreedsolomon" directory is present, if you don't want this just rename the directory.  Used **with** permission from https://github.com/brownan/Reed-Solomon - Thanks Andrew.  **WILL NOT BE USED WHEN USING FLDIGI**
  1. When running in debug mode the packet overhead is mentioned.  A overhead of over 200% is normal when using the 8-bit protocol due to Reed-Solomon.  A overhead of over 100% is normal when using the 8-bit protocol using fldigi.


## v0.3.0 - 15th December 2010 ##

  1. When using the RS-232 backend, the RTS is set to high (serial.setRTS(True)) when transmitting and low (serial.setRTS(False)) when receiving.
  1. A small 75ms delay is performed before sending the actual data, the same delay is done after the data has been sent.
  1. Introduced a new 8-bit binary mode, mainly for using DDP over a modem like my GMSK one.  Just set "specification = 1" to enable it, otherwise set it to 0 to use the original 7-bit text mode.  The example code XML files will expose this after they have updated.  `*`PLEASE NOTE THAT THE 8-BIT MODE CURRENTLY DOESN'T WORK WITH FLDIGI AS THE BACKEND, I'M CURRENTLY TRYING TO RESOLVE THIS`*`
  1. Packets are now sent with a preample using the characters "\xcc", again this is mainly to add the GMSK modem but otherwise won't harm anything
  1. receiveData`*`() routines now return the data already reconstructed, this reduces the user end code.  Please review the code examples for this new behavour.
  1. A HTTP proxy server and client code has been wrote as `*`proof of concept`*`.  You will need a real proxy server (like Squid - http://www.squid-cache.org) for my code to forward the packets onto (the upstream server in the XML config), don't expect this to run quick!

## v0.2.1 - 20th September 2010 ##

  1. TCP/IP is now supported as a backend, set "BackendDataMode" to "TCP/IP" and set "BackendHostname" to the interface address to listen on and set "BackendPort" to the port number to listen on.  Please pay particular attention to the "PacketFromIP", "PacketFromPort", "PacketToIP", and "PacketToPort" in the settings XML - these are contained in the packet to allow it to route back to you again.  Normally, the IPs will be the public address you're on this is useful if you are using NAT.  At this stage, TCP/IP support is still experimental as it currently shows proof of concept.  The way this backend works may change in the future.  All packets are sent and received using UDP.
  1. Since TCP/IP is supported, there's no reason why it wouldn't work with D-STAR (DD) now.

## v0.2.0 - 13th September 2010 ##

  1. This release contains a tweak to the DDP code to include a TX/RX delay to allow recover time of the rig.  It also happens to allow me to use only one copy of fldigi rather than two for testing purposes!
  1. Default protocol is now PSK500R when using fldigi, this is supported in fldigi 3.20.X and above (I compile my own version of fldigi under FreeBSD since the maintainer no longer maintains it), I would recommend to upgrade to at least this version.
  1. The checksum algorithm has now been changed from CRC32 to SHA1.
  1. The transmitData() routine is aware of a: Packets which require to be ACK'ed to confirm they were received (like with TCP) and b: Packets not to bother ACK'ing them (like with UDP).  This is handled automatically by the receiveData() routine, TCP mode is set by default for the transmitData() routine.
  1. The BBS server and client now have XML setting files and allows the default datamode to be changed.
  1. D-STAR (DV) is now supported as a backend, set "BackendDataMode" to "D-STAR" and the COM port that your rig is on for the "BackendHostname" e.g. "/dev/ttyu0", and set the "BackendPort" to the serial parameters e.g. "9600/8/N/1".
  1. Wrote a IM chat program for sending short messages to other users.
  1. Improved the timeout coding, now uses time.time().
  1. Wrote a file transfer program for sending files to other users.
  1. Since D-STAR (DV) is supported, I've included support to send data over the serial port, uses same parameters as D-STAR (DV) mentioned above except set "BackendDataMode" to "RS-232".  This allows any new rigs which give direct access to RS-232 for sending and receiving data to work with DDP.
  1. Base API improved, various improves made with new subroutines - code examples modified.
  1. The protocol will not maintain backwards compatibility until we reach v1.0.0, incompatible packets will be dropped.

## v0.1.0 - 6th June 2010 ##

  1. Initial release, bit rough on the edges.  Basics working.

## v0.0.0 - 21st February 2010 ##
  1. Development started

# Usage #

On the command line: -

`% python bbs_client.py`

`% python bbs_server.py`

`% python broadcast_client.py`

`% python broadcast_server.py`

`% python emcomm.py`

`% python fax_receive.py`

`% python fax_send.py`

`% python file_transfer.py`

`% python httpproxy_server.py`

`% python httpproxy_client.py`

`% python im_chat.py`

`% python kex.py`

`% python mx_client.py`

`% python mx_server.py`

`% python repeater.py`

`% python xr_client.py`

`% python xr_server.py`


# Current Features #

DDP has numerous features which aren't in any other form of packet radio, here is what you get: -

  1. `*``*``*` You must have fldigi installed on your PC as well as enabling the XMLRPC protocol, see the help documents for fldigi for more information!  That's if you want to use fldigi that is... `*``*``*`
  1. Contains example code for: -
  * A very basic BBS server and client using the DDP protocol
  * A basic IM chat program using the DDP protocol
  * A basic file transfer program using the DDP protocol
  * A **proof-of-concept** HTTP proxy server and client using the DDP protocol
  * A simple repeater for repeating DDP packets using the DDP protocol
  * A basic program for automating passing messages for EmComm using the DDP protocol
  * A basic application which can send and receive faxes using the DDP protocol
  * A basic XMLRPC server and client proxy which will allow applications which use XMLRPC to send traffic using the DDP protocol
  * A basic key exchange (KEX) program for transferring your public keys using the DDP protocol
  * A basic mail exchanger (MX) for sending and receiving emails using DDP protocol
  * A basic broadcast packet server and client using DDP protocol
  1. You can include the ddp.py to get support of the protocol in your project - look at the example code (BBS/IM/FT/HP/EMCOMM/FAX/KEX/MX) for guidance.
  1. Error correction on the packets using Reed-Solomon(64,48).
  1. Callsign signatures using RSA public/private key pairs to help prevent callsign abuse.
  1. Application IDs prevents your application from processing packets from other programs.
  1. Unique packet IDs prevents simple packet replay attacks.



# Installation #

## FreeBSD ##

Here are the packages I've currently got installed for DDP to work: -

  * py27-m2crypto (/usr/ports/security/py-m2crypto/)
  * py27-serial (/usr/ports/comms/py-serial/)
  * python26  (/usr/ports/lang/python/)

You can install them in any order, you might want to make sure the your ports collection is up-to-date.  Python 2.X is normally installed by default so don't worry about that one.


## Linux ##

Untested - But you should find the above packages for your distro.  I don't expect any problems running DDP on Linux.


## MacOS ##

Untested.


## Microsoft Windows ##

The preferred method for using DDP on Windows is by using Cygwin.  Download the guide from the DDP website for using this option.  Running DDP outside of the Cygwin environment under Windows will become unsupported soon.



# FAQ #

**What are the dependencies for this program?**

Python v2.6 or greater.  Modules used are collections, hashlib, math, m2crypto`*`, pypng, serial`*`, socket, threading, time and xmlrpclib.  `*` - External package which requires installing since it's not normally installed by default.


**What operating systems does it support?**

I develop and test DDP with FreeBSD 8.1, it should work in other POSIX compliant operating systems as well other distros of Linux.  I have also tested it under MS Windows and haven't seen any problems.


**Can I create (port) of DDP?**

By all means! Be sure to read the LICENSE as your port will inherit the license.


**I've found a bug! What do I do?**

Let me know by raising it as an issue so I can fix it in the next version.


**I would like a feature that's not in DDP...**

I'm currently not accepting feature requests as DDP is a protocol not a "final" product.


**Can/Will you make DDP compatible with the existing packet radio system?**

No, DDP is aiming to replace it entirely.  However, there is nothing stopping someone from writing a wrapper program which does this - I will not write this myself and/or provide support to perform this.  DDP has many more features than the old packet system and it's actually faster when running over HF, DDP uses PSK500R by default which gives around 500 baud vs 300 baud for the old system.  DDP can also go crossband and specifications with its repeater code.


**When using the FLDIGI backend, can I use another datamode?**

Yes you can, just specify which datamode you want to use (in-case of the examples just change it in the XML file).  I prefer using PSK myself but you should not have any problems using another mode which supports the full ASCII character like MFSK (my second preferred datamode).  So using a datamode like RTTY won't work.



# Legal #

I am in no way affiliated or in partnership with Google, Fldigi, Icom, Yaesu, Microsoft, or anyone else.