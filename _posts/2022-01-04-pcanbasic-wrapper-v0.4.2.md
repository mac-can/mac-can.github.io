---
layout: single
title:  "PCANBasic-Wrapper - Version 0.4.2 released"
tag: PCANBasic-Wrapper
categories: Change-log Wrapper Windows Peak PCANBasic
artifacts: https://github.com/uv-software/PCANBasic-Wrapper/releases/tag/v0.4.2
release: Version 0.4.2 (Commit cede7f7 of January 4, 2022)
---
[**{{ page.release }}**]({{ page.artifacts }}):

- Updated PCANBasic DLL (version 4.6.0)
- Updated CAN API sources to rev. 1020 and applied the changes
- Resolved firmware version vs. software version confusion
- Fixed an issue with missing copy constructor (avoid dynamic allocation of class members)
- Fixed some bugs with getting properties from device and from library:
  - accept NULL pointer for `SET_FIRST_CHANNEL` and `SET_NEXT_CHANNEL`
  - getting device properties requires a valid handle
  - string values must be at least one byte in size
- Fixed some issues with vendor-specific property values
- Fixed findings from static code analysis (incl. C statement style)
- Updated Python examples (although they do not work under Windows)
- Updated my beloved utilities (and added GPL license text)
