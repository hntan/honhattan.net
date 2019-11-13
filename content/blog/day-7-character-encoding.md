---
title: "Character Encoding"
date: 2019-05-31T10:09:09+07:00
---

## What's character encoding?

Words and sentenses are created from characters. Those characters are stored in computers in bytes.

Basically, you can visuallize by assuming all characters are stored in computer using a special code. A character encoding provides a key to unlock the code. It is set of a mappings between bytes in computers and the characters in character set.
Without key, the data looks like garbage.

## Unicode

Unicode assigns unique numbers to characters used all over the world. Those numbers are known as code points.

There are over one millions code points in Unicode character set. From U+0000 to U+10FFFF  
* U+0022: _"_  
* U+0030: _0_  
* U+0063: _C_  
* U+01A1: _ơ_  

Lot of unassigned code points. If Minion language becomes widespead enough at some points, it can easily be added.

## Encoding

There are many way to represented a code point.

Usually a code point is represented in bytes per the rules of an encoding. 

Ex: U+20AC EURO SIGN  
* 0x80: in windows-1252  
* 0xAC 0x20: in utf-16le  
* 0x20 0xAC: in utf-16be  
* 0xE2 0x82 0xAC: in utf-8  

Only utf-8, utf-16(both variants) can present all the code points.