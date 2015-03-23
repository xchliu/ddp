# Danny's Digital Packet #

A protocol designed to be used as alternative to packet radio which interfaces with fldigi, RS-232, or D-STAR DV to provide the backend.  Packets are sent and received in plain text so they can be seen by eye (on the waterfall, console, etc) and also for ease of use and implementation.

Designed to work with ANY transceiver that can be interfaced to your computer using fldigi, RS-232, or using any compatible D-STAR DV rig.


Developed by Danny Knaggs [2E0DPK](http://qrz.com/db/2E0DPK)/[M6DPK](http://qrz.com/db/M6DPK).


---


---


Status: **Beta**

Supported OS: **[FreeBSD](http://www.freebsd.org/), Linux, and Microsoft Windows**

Supported Hardware: **Any transceiver which can be interfaced to your PC via soundcard/interface (like the [Signalink USB](http://www.tigertronics.com/slusbmain.htm)) and/or RS-232**

Technology Backends: **[Fldigi](http://www.w1hkj.com/Fldigi.html) (PSK500R, PSK250R, MFSK64, MFSK32, etc), D-STAR (DV) over RS-232, and plain RS-232**

Needs testing on: **MacOS and others**


---


---


## Features ##

DDP has numerous features which aren't present in any other form of packet radio for amateur/ham use: -

  * Interfaces with [FLDIGI](http://www.w1hkj.com/Fldigi.html) or RS-232.
  * Ability to use either 7-bit, 8-bit, or short message modes (text-only and binary) for packet transfer.
  * Error correction using Reed-Solomon(64,48).
  * Data scrambling.
  * TCP or UDP modes.
  * Callsign signatures using RSA public/private key pairs to help prevent callsign abuse by signing the packets.
  * Application IDs prevents your application from processing packets from other programs.
  * Packet IDs prevents simple packet replay attacks.
  * You can include the ddp.py file to get support of the protocol in your project, use the examples as a guide.
  * Code examples showing how to use DDP for: -
> | BBS server and client |
|:----------------------|
> | Instant messaging |
> | File transfer |
> | HTTP proxy server and client |
> | Repeater |
> | EmComm |
> | Sending and receiving faxes |
> | XMLRPC proxy server and client |
> | RSA key exchange (KEX) |
> | Mail exchange (MX) |
> | Broadcast messages |

DDP is a faster (especially on HF), more secure and reliable alternative to the aging packet radio system for the 21st century.


---


---


### Don't forget to download ###

  * **(All)** [7zip](http://www.7-zip.org/) - To extract the files from the archive.
  * **(All)** [Fldigi](http://www.w1hkj.com/Fldigi.html) - DDP's default backend.

---

  * **(Windows)** [DDP and Cygwin Guide](http://code.google.com/p/ddp/downloads/detail?name=DDP%20and%20Cygwin.pdf) - Step by step guide on installing Cygwin for DDP.
  * **(Windows)** [Cygwin](http://www.cygwin.com/) - Linux-like environment for Windows.
  * **(Windows)** [Notepad++](http://notepad-plus-plus.org/) - Use for editing/viewing the text files.

---

### My other projects ###

  * **(Unix)** [DanZFS](http://code.google.com/p/danzfs/) - My own take on providing a Python backend to ZFS for monitoring (additional features like snapshots, etc will come later)
  * **(Unix)** [DDV](http://code.google.com/p/ddv/) - My own version of digital voice which uses DDP as it's transport layer, currently only supports unix-like operating systems.
  * **(All)** [StormForce XR](http://code.google.com/p/stormforce/) - Real-time lightning detection for your desktop using [Boltek](http://www.boltek.com/ld250.html) products.

---


---


## News ##

---

27th August 2012 - DDP v0.6.1 released!
  * It's been a while but here is a big update!  Features several bugfixes and the concept of broadcast packets.  Take a look at the README file for more information.  Hope you all like it!
  * [DDV](http://code.google.com/p/ddv/) has also been updated.

---

4th August 2012 - Upcoming updates
  * Updates for DDP and [DDV](http://code.google.com/p/ddv/) coming soon!  Maybe even a [SXR](http://code.google.com/p/stormforce/) one.  Watch this space!

---

23rd April 2012 - News
  * Yep, spending some time on [StormForce XR](http://code.google.com/p/stormforce/) since I haven't got anything more to add to DDP at the moment.

---

12th April 2012 - News
  * Not a lot going on with DDP at the moment, got nothing to add to it for now.  May do some more work on [StormForce XR](http://code.google.com/p/stormforce/) as we near the summer months.

---

11th February 2012 - DDP v0.6.0 released!
  * Here is the latest version of DDP.  Features a new binary specification based on the SMS protocol in the previous version and now the specifications have been separated from the core so adding new specifications or altering them can be done without altering the core code.  So if you want to create your own specification you can!  Please read both the README and the PROTOCOL document for more information.
  * UPDATE: [DDV](http://code.google.com/p/ddv/) has also been updated.

---

25th January 2012 - DDP v0.5.4 released!
  * Here another update to DDP this month, a few tweaks have been made to the 7-bit and 8-bit specifications.  I've also introduced a new specification designed for short messages.  Take a look at the the README and the PROTOCOL document for more information.  Hope you all like it!

---

10th January 2012 - DDP v0.5.3 released!
  * Here is a little update to DDP, just a couple of improvements.  See the README file for information.

---

24th December 2011 - Google Plus
  * Join me [here](https://plus.google.com/114133917349096726827) on Google Plus for ham/electronics-related topics!

---

2nd December 2011 - News
  * With [Codec2](http://www.rowetel.com/blog/?p=2255) now running at 1400bit/s, it should be possible to run it over my AFSK modem running at 1800 baud (MX614 IC) - wonder if the 1200 bit/s port on the rig is able to run a little faster?  Hmmm, thinking DV over SSB on my trusty Yaesu FT-817.

---

14th November 2011 - News
  * Sorry for the lack of updates, been extremely busy with work.

---

13th October 2011 - DDP v0.5.2 released!
  * The next version of DDP is now available.  This update includes a new feature called "application ID" and also contains example code showing how to use DDP for mail exchange.  Hope you all like it.
  * [DDV](http://code.google.com/p/ddv/) has also been updated.

---

9th October 2011 - News
    * Been a while since I've done any updates.  However, this will soon be remedied with a new feature and another code example.  Watch this space!

---

27th August 2011 - DDP v0.5.1 released!
    * Here is the next version of DDP.  This update includes the [XMLRPC](http://www.xmlrpc.com/) server/client proxy code as well as a new feature called "callsign signature" - this new feature allows you to authenticate callsigns by signing the packets using RSA.  It is NOT used for encryption, just the signing.  Please read the [README](http://code.google.com/p/ddp/wiki/README) and the PROTOCOL document for more information.  Hope you all like it.
    * [DDV](http://code.google.com/p/ddv/) has also been updated.
    * **UPDATE**: The [Cygwin](http://www.cygwin.com/) guide has been updated, grab it from the [downloads](http://code.google.com/p/ddp/downloads/list) section.

---

18th August 2011 - News
    * Bear with me for the next release, I just want to get this new feature that I want in DDP perfect - details will be given when released.

---

12th August 2011 - News
    * Next release due soon, contains the [XMLRPC](http://www.xmlrpc.com/) server/client proxy code as mentioned on the [StormForce XR](http://code.google.com/p/stormforce/) page.  Watch this space.

---

4th August 2011 - News
    * No ideas have coming in, so I'm going to devote some time to [StormForce XR](http://code.google.com/p/stormforce/) instead.

---

17th July 2011 - News
    * Well, not a lot going on with DDP - not sure where to go with it next.  Any ideas which will improve the protocol?

---

12th June 2011 - DDP v0.5.0 released!
    * Apologies for the lack of updates, been playing round with [IPv6](http://en.wikipedia.org/wiki/IPv6) - very good.  Anyway, here is the next release of DDP which contains a few more tweaks and improvements.  Hope you all like it.

---

28th May 2011 - News
    * No new updates as of yet as I've been working on [StormForce XR](http://code.google.com/p/stormforce/).  I will be writing a example application which can receive strike data over DDP, watch this space!

---

21st May 2011 - StormForce XR v0.1.1 released!
    * The next version of StormForce XR is now available for download.  Head over to the [StormForce](http://code.google.com/p/stormforce/) project page for more information.

---

16th May 2011 - StormForce XR v0.1.0 released!
    * The next generation of StormForce is now available for download.  Head over to the [StormForce](http://code.google.com/p/stormforce/) project page for more information.

---

14th May 2011 - News
    * I'm looking at updating [StormForce](http://code.google.com/p/stormforce/) which allows better headless operation, this would also make it more usable for external clients.  This would lead to sending strikes information via DDP.  Watch this space!

---

2nd May 2011 - News
    * New group created for support of DDP.  This group is open to everyone you just need to join as member.  Take a [look](http://groups.google.com/group/ddp-support).

---

1st May 2011 - News
    * Just made a few changes to this front page to allow easier downloading of the components you may require to use DDP.

---

30th April 2011 - News
    * DDP has now been mentioned on the [ARRL](http://www.arrl.org/news/view/surfin-moving-packets-with-ddp) website.  It's also been mentioned over at [Southgate ARC](http://www.southgatearc.org/news/april2011/ddp.htm) website.  Thank you very much!
    * UPDATE: I've updated the [Cygwin](http://www.cygwin.com/) guide for DDP as [PyLZMA](http://pypi.python.org/pypi/pylzma) now compiles under [Cygwin](http://www.cygwin.com/) fine.  Grab it from the [downloads](http://code.google.com/p/ddp/downloads/list) section.
    * UPDATE: I've made a few changes to the [README](http://code.google.com/p/ddp/wiki/README) file which corrects a few changes which will present in the next release.  No point re-releasing for a few typos in the file!

---

29th April 2011 - DDP v0.4.2 released!
    * Here is the next version of DDP.  Includes a few changes made to the fldigi backend and also includes the fax example code.  Check out the [README](http://code.google.com/p/ddp/wiki/README) for more information.

---

26th April 2011 - News
    * [Fldigi](http://www.w1hkj.com/Fldigi.html) now appears to have WEFAX (HF-FAX), excellent!
    * That's given me an idea, sending and receiving faxes using DDP.  Watch this space!

---

23rd April 2011 - DDP v0.4.1 released!
    * Here is the next version of DDP.  Includes a few tweaks here and there so check out the [README](http://code.google.com/p/ddp/wiki/README) as per normal.  Also includes the EmComm and repeater example code.  I've dropped support for TCP/IP (UDP) as I want to keep this project pure RF.  Hope you all like it!
    * I've contacted both the [RSGB](http://www.rsgb.org/) and the [ARRL](http://www.arrl.org/) informing them of DDP.  Just trying to spread the word...

---

22nd April 2011 - News
    * Everything looks good, will be releasing the next version tomorrow.

---

21st April 2011 - News
    * The repeater code appears to be working, just needs more testing.  The repeater is able to work across different backends and protocol specifications, so you can mix and match as you please.
    * Also looking at doing a EmComm application which aids in sending [ICS-213](http://www.ics213.com/downloads/ics213.pdf) (or more specifically the modified [ICS-213](http://ronhashiro.htohananet.com/am-radio/emcomm/ics-213.pdf) document) messages via DDP.  As a example, when combined with the repeater code you can send messages crossband.  So you can be sending messages via HF across the country but being repeated locally via VHF/UHF so they can be dealt with.  Does anyone know what messaging standard the UK uses?  I can't find any information on this, but using the ICS document as the template for the application would be a good start...

---

20th April 2011 - News
    * Not having much luck with the [DVDongle](http://www.dvdongle.com/DV_Dongle/Home.html), so instead I've been working on the repeater code.

---

7th April 2011 - News
    * I'm going to look at using the AMBE codec via the [DVDongle](http://www.dvdongle.com/DV_Dongle/Home.html) to provide an additional codec available to [DDV](http://code.google.com/p/ddv/).  No-one has done any tools for the [DVDongle](http://www.dvdongle.com/DV_Dongle/Home.html) wrote in Python so I'll have to do it myself - nothing new then, hi.

---

2nd April 2011 - DDP v0.4.0 released!
    * It's been a few months but the next release of DDP is now available.  Offers various speed improvements to the internal code.  As per normal, please read the [README](http://code.google.com/p/ddp/wiki/README) for more information.
    * I've also done a guide on how to install and configure Cygwin so DDP can use it.  Grab it from the [downloads](http://code.google.com/p/ddp/downloads/list) section.
    * [DDV](http://code.google.com/p/ddv/) has now been released.

---

31st March 2011 - News
    * Managed to sort out the timing issue with [DDV](http://code.google.com/p/ddv/) completely.  Just needs additional testing and tidying up.

---

17th March 2011 - News
    * Still making the changes to DDP for [DDV](http://code.google.com/p/ddv/), managed to reduce the timing issue by half but still needs reducing further...
    * The next release will also have improved module loading, this means you don't have to install the extra packages (like [PySerial](http://pyserial.sourceforge.net/index.html) and [PyLZMA](http://pypi.python.org/pypi/pylzma)) if you don't want to.  It just means you can't use them, no [PySerial](http://pyserial.sourceforge.net/index.html) means you can't use the RS-232 backend and no [PyLZMA](http://pypi.python.org/pypi/pylzma) means compression will be switched to GZIP instead.
    * Windows support maybe dropped in favour of using [Cygwin](http://www.cygwin.com/) instead.  It will certainly make things easier to install...  I'm currently testing this.

---

28th February 2011 - News
    * Getting the first release of [DDV](http://code.google.com/p/ddv/) is taking longer than I expected, locating a timing issue which is causing the required baudrate to increase at 2x fold (maybe more, 4x)...  Bare with me!
    * On a side note, I've made a RS-232 modem which uses a laser as it's transmission medium.  Got it working upto 115200 baud without any problems.

---

12th February 2011 - News
    * Making some progress with [DDV](http://code.google.com/p/ddv/), maybe able to get something released in about a week.  Watch this space!

---

6th February 2011 - News
    * Been working on [DDV](http://code.google.com/p/ddv/) today, made some progress.  [DDV](http://code.google.com/p/ddv/) will use DDP as it's transport so it will have all the features and reliability of DDP.
    * [Codec2](http://www.rowetel.com/blog/?page_id=452) looks promising as well, [DDV](http://code.google.com/p/ddv/) will also support this codec.

---

5th February 2011 - DDP v0.3.3 released!
    * The next version of DDP is now available!  Now uses interleaving when using Reed-Solomon to improve it's correction factor.  Have a read of the [README](http://code.google.com/p/ddp/wiki/README) for more information.

---

28th December 2010 - DDP v0.3.2 released!
    * The next version of DDP is available for download!  Contains a few bug fixes and speed improvements.  Check out the [README](http://code.google.com/p/ddp/wiki/README) for more information.

---

24th December 2010 - News
    * I'm now doing some more work on [DDV](http://code.google.com/p/ddv/).  DDV will use DDP as it's transport layer, this is one of reasons I created the 8-bit protocol.  I've also started playing with [Codec2](http://www.rowetel.com/blog/?page_id=452) which I've managed to get compiled on FreeBSD, I've sent Dave VK5DGR what I did to do this.

---

21st December 2010 - DDP v0.3.1 released!
    * The next version of DDP is now available!  Includes 8-bit protocol in fldigi, data scrambling, and Reed-Solomon.  As always, check the [README](http://code.google.com/p/ddp/wiki/README).

---

19th December 2010 - News
    * The upcoming release will see the arrival of the 8-bit protocol to fldigi (had to workaround a few problems), data scrambling (found a potential problem with PSK500R and the other "robust" modes which scrambling cures it) - I've fired an e-mail off to Dave W1HKJ with the details, awaiting feedback on this), and Reed-Solomon on the packets as well (no external packages to install, all "built-in").  Watch this space!

---

16th December 2010 - News
    * A new discussion group has been created on [Google Groups](http://groups.google.com/group/ddp-protocol/) for discussing anything related to DDP.

---

15th December 2010 - DDP v0.3.0 released!
    * I'm proud to announce the next version DDP!  This version includes improved API, better packet handling, the HTTP proxy server/client, and the 8-bit version of the protocol (currently only works over RS-232, fldigi to follow soon).  As always, read the README file for more information.
    * A copy of the README is now available on the [wiki](http://code.google.com/p/ddp/wiki/README).

---

14th December 2010 - News
    * The 8-bit protocol is now done, expect a release soon.  Just getting the example code tested...
    * UPDATE: All looking good, will be releasing tomorrow.

---

9th December 2010 - News
    * I'm currently designing the 8-bit version of the DDP protocol designed to transmit binary data more efficiently.  Will be more useful for [DDV](http://code.google.com/p/ddv/) in particular but of course it will work with any other kind of data.  However, the 8-bit protocol won't be particularly useful when using fldigi.

---

7th December 2010 - News
    * The GMSK modem is now decoding packets.  Just fine tuning the RX section...

---

5th December 2010 - News
    * Left the modem for a while doing over projects, had another whirl today but still can't it to decode the GMSK signal.  Adjusting the DC bias on the RX input changes the data output so I know it's doing something.  Maybe the TX needs biasing as well?  Hmmm...

---

18th November 2010 - News
    * It appears the CMX589 needs a bias on the audio input, but can't get it decode yet...

---

9th November 2010 - News
    * New project created for another use of my modem - [DDV](http://code.google.com/p/ddv/)

---

6th November 2010 - News
    * The GMSK modem capable of 9600 bit/s is now under testing.
    * A code change is required to tell the modem to key up the transmitter, so I'll release an update when I can.  Few things to sort first...

---

6th October 2010 - News
    * Just a quick update, I'm working on designing my own modem suitable for use with DDP.  My first modem I'm designing uses the MX614 as it's main IC along with a few other ICs to handle RS-232 and logic.  After this has been successful, I'll be designing a GMSK modem based on the MX589 IC - the interesting thing about this one is that it should be possible to decode D-STAR with it (not the voice part as that requires the AMBE chip).  But that's a project for another day!  With the GMSK modem it should be possible to obtain 9600 baud.  Watch this space!
    * I may have to make a small change to the RS-232 code to raise the RTS pin to inform the modem to key up the transmitter, if this change is needed - I'll release an update.

---

20th September 2010 - DDP v0.2.1 released!
    * I'm proud to announce the release of v0.2.1 of DDP.  This includes support for TCP/IP as well as D-STAR (DD), as always read the README file for more information.
    * I've also included a PROTOCOL file to help those who wish to understand the DDP protocol for implementing in there own code.
    * I don't see any reason why DDP wouldn't work on Linux, so it's now supported.
    * Previous versions have been marked as deprecated.

---

19th September 2010 - News
    * DDP over TCP/IP is going OK, just tweaking a few things then I can get it released.
    * Future releases will be compressed with 7z (http://www.7-zip.org/) to allow easy file extraction for all OS users (rather than a tarball).  Windows users should download Notepad++ (http://notepad-plus-plus.org/) for reading the README file.
    * Testing on Microsoft Windows has not shown any problems (as expected), so it's now supported
    * Testing on Linux is currently under testing (just need to elaborate in the README file)

---

17th September 2010 - News
    * DDP over TCP/IP is currently in development.
    * DDP is currently being tested on Linux and Microsoft Windows for compatibility, so far it's looking fine with no changes made to the code.

---

13th September 2010 - DDP v0.2.0 released!
    * I'm proud to announce the release of v0.2.0 of DDP.  This includes support for D-STAR (DV), as always read the README file for more information.

---

12th September 2010 - News
    * OTA tests so far are looking good.  I'm just re-writing some of the base code to incorporate some of the future features and also to improve the API code.  This will minimise altering the protocol too much allowing better compatibility.

---

9th September 2010 - News
    * Looks like the code for handling higher speeds is running fine.  I'll need to run some on the air (OTA) tests now.  After these, I'll get DDP released with support for D-STAR and other serial devices.
    * Going a little bit ahead here, but after I release the code for D-STAR/serial I'll be adding support for sending/receiving DDP over a ethernet interface.  This will allow packets to be transferred over your LAN/WAN (internet) or even over D-STAR (DD) using TCP/IP.

---

8th September 2010 - News
    * Testing going fairly well, I'm just getting the code perfect when running over a crossover (null modem) cable.  This will ensure the code is able to handle higher speeds.

---

4th September 2010 - News
    * Testing DDP over D-STAR is going well, just ironing out the kinks.  Should be able to release it soon but without the repeater code.

---

26th August 2010 -News
    * DDP over D-STAR is now under testing.  Watch this space!

---

20th August 2010 - News
    * OK, the code has been modified to handle a D-STAR rig over RS-232.  I'll need to do some more testing before releasing.
    * I'm also looking at adding a repeater option so DDP packets can be sent over greater ranges, even using different backends/protocols.  I'm hoping this can be included with the next release.

---

19th August 2010 - News
    * I'm now looking at adding code which can communicate with a D-STAR rig, this means I can transport DDP over D-STAR DV using the RS-232 port.  So you'll have the option to use fldigi or D-STAR as the backend.  This will enable the potential for cross-backend communication, so you could have a user sending DDP using HF and then you could re-transmit the packets locally using D-STAR or (via fldigi again) if required.  The internet doesn't even have to be involved to move the packets about - all done using RF.  Watch this space!

---

8th August 2010 - News
    * An update will be available soon which improves timing issues between fldigi and the radio.

---

6th June 2010 - DDP v0.1.0 released!
    * The initial version of DDP has been released!  The download contains the DDP module so you include support in your application for it and example BBS server/client code.

---

21st February 2010 - News
    * Project created on Google Code, no code available yet.

---


---
