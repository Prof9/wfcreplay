﻿WfcReplay
=========
WfcReplay is a command-line Windows utility written in C# that automatically generates an Action Replay DS code for a Nintendo DS game that will make it use HTTP instead of HTTPS for connections to Nintendo Wi-Fi Connection. This is done by pre-finding all URLs in the ROM and patching them in-memory. This can be used to connect to any custom Nintendo Wi-Fi Connection server.

To run this program, the .NET Framework 4.0 or higher must be installed on your computer.

Usage
-----
```
WfcReplay.exe rompath
```

To use WfcReplay, pass it the file path of an NDS ROM. You can also drag-and-drop the ROM file onto the WfcReplay executable. WfcReplay will then analyze the ROM and produce a text file containing the Action Replay DS code, which will be written to the current working directory.

Compatibility
-------------
WfcReplay should work with most NDS games, though not every single one of them has been tested. See below for known incompatible games. If you find another incompatible game, please create an issue on the GitHub page at https://github.com/Prof9/wfcreplay.

Known incompatible games
------------------------
The following games are known to be incompatible with WfcReplay. These will most likely never be supported and will require a game-specific code to be written for them.

* **Animal Crossing: Wild World**: ARM9 binary gets copied to ITCM before AR has a chance to patch it.
* **Contact**: Code works, but the game never idles so the URLs never get patched.

Notes
-----
* Older versions of DeSmuME are incompatible with codes generated by WfcReplay. Use a newer version of DeSmuME based on r5047 or later, or try an alternative patching method.
* Action Replay DS codes generated by WfcReplay may interfere with certain Action Replay DS codes from other sources, such as cheat databases.
* Furthermore, the code may disrupt anti-anti-piracy features of older flash cards. Flash cards are not supported; only the official Action Replay DS(i) by Datel is.
* Additionally, for certain games, the code may clash with special flashcard features like soft-reset. If this happens, you will need to disable these features.
* If you use NitroHax, performing a soft reset (L+R+Start+Select) may cause the HTTPS bypass cheat to stop working.

Credits
=======
**WfcReplay (c) 2014 - 2016**

* Prof. 9

**BLZ (c) 2011**

* CUE

**Thanks**

* bjoern-r, for Mono compatibility.

License
=======
This project is licensed under the terms of the MIT license. See *license.txt* in the main folder for more information.

WfcReplay includes a modified version of BLZ v1.4 by CUE, which is covered by the GPLv3 license. As such, the source code for this program is included and can be found in *blz.c*. The full terms of the license can be found in *license.txt* in the *BLZ* folder, or in *blz_license.txt*. The relevant changes can be found at https://github.com/Prof9/wfcreplay/commits/master/BLZ/blz.c, and were made starting 25 April 2015.