Onyx The Black Cat
==================

Copyright © fG!, 2011, 2012, 2013, 2014 - reverser@put.as - http://reverse.put.as
All rights reserved.

Introduction
-------------------------------------------------------------------------------
A kernel module for Intel Mac OS X that will provide you with some
anti anti-debug protection and other features.

This module will allow you to debug programs which use these tricks without
need to patch them (no need to patch lots of anti-debug calls and maybe 
checksum code).
Compatible with all OS X versions since Snow Leopard (older probably supported!).
Mavericks introduces kernel extension code signing but this still works
if you load it manually.

Features can be enabled or disabled using the control program. By default
everything is disabled. This util requires root privileges to run. If you
want to run it as normal user you can remove CTL_FLAG_PRIVILEGED from
kernel_control.c source file.

This code uses diStorm as its disassembler. 
Due to licensing differences its files are not included. 
You can download diStorm from:
http://code.google.com/p/distorm/ and include the missing files.
The only required change is to define SUPPORT_64BIT_OFFSET. You can do it
either at diStorm's config.h file or at Xcode project settings.

Included are small test programs to test the anti-debug tricks, and other 
features.

The weird name is based on a big black cat named Onyx who is always hiding and 
running from me :).
"I'm gonna hug you and kiss you and love you forever (and never use you up)"
Elmyra Fudd.

I hope it's useful for you. It is for me.
If you find/know any other gdb anti-debug tricks, please drop me an email with 
some details so I can add them to the module.

Have fun.
fG!

Installation
-------------------------------------------------------------------------------
Copy onyx-the-black-cat.kext to /System/Library/Extensions
(sudo cp -rf onyx-the-black-cat.kext /System/Library/Extensions)

and then load the module with kextload
(sudo kextload /System/Library/Extensions/onyx-the-black-cat.kext)

Unload module with kextunload
(sudo kextunload /System/Library/Extensions/onyx-the-black-cat.kext)

Use the control program to enable/disable features. Everything is disabled by
default.

You can check dmesg or /var/log/system.log for debug messages and anti-debug
 hits.

Known Problems
-------------------------------------------------------------------------------
Still some ugly code :-)
