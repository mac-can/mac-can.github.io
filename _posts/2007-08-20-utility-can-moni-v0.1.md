---
layout: single
title:  "CAN Utility `can_moni` - Version 0.1 published"
tag: CAN-Utilities
categories: Change-log Utilities Linux SocketCAN
artifacts: https://github.com/uv-software/can_moni/releases/tag/v0.1
release: Version 0.1 (Build 17 of August 20, 2007)
---
[**{{ page.release }}**]({{ page.artifacts }}):

The CAN utility `can_moni` is a command line tool to view incoming CAN messages.
I hate this messing around with binary masks for identifier filtering.
So I wrote this little program to have an exclude list for single identifiers or identifier ranges
(see program option `--exclude` or just `-x`).
Precede the list with a `~` and you get an include list.

Origin: [https://www.uv-software.de/dokuwiki/doku.php?id=uvs:programs:can_moni_linux](https://www.uv-software.de/dokuwiki/doku.php?id=uvs:programs:can_moni_linux)
