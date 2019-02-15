# pytgvoip
 
[![](https://img.shields.io/pypi/v/pytgvoip.svg?style=flat)](https://pypi.org/project/pytgvoip/) [![](https://img.shields.io/appveyor/ci/bakatrouble/pylibtgvoip.svg?label=windows%20wheels%20build&style=flat)](https://ci.appveyor.com/project/bakatrouble/pylibtgvoip) [![](https://img.shields.io/appveyor/ci/bakatrouble/libtgvoip.svg?label=libtgvoip%20windows%20build&style=flat)](https://ci.appveyor.com/project/bakatrouble/libtgvoip) ![](https://img.shields.io/pypi/l/pytgvoip.svg?style=flat)
 
**Telegram VoIP Library for Python**

[Community](https://t.me/pytgvoip)

**PytgVoIP** is a [Telegram](https://telegram.org/) VoIP library written in Python and C++.

It uses [libtgvoip](https://github.com/grishka/libtgvoip) (a library used in official clients) 
for voice encoding and transmission, and [pybind11](https://github.com/pybind/pybind11) for simple 
generation of Python extension written in C++.

## Features
* Making and receiving Telegram calls
* Python callbacks for sending and receiving audio stream frames allow flexible control
* Pre-built Windows wheels in PyPI

## Requirements
* Python 3.4 or higher
* An MTProto client (i.e. Pyrogram, Telethon)

Linux, MacOS: (use binary wheels from PyPI for Windows)
* [libtgvoip](docs/libtgvoip.md)
* CMake, C++11-compatible compiler, Python headers

## Installing
```pip3 install pytgvoip```


## Encoding audio streams
Streams consumed by `libtgvoip` should be encoded in 16-bit signed PCM audio.
```bash
$ ffmpeg -i input.mp3 -f s16le -ac 1 -ar 48000 -acodec pcm_s16le input.raw  # encode
$ ffmpeg -f s16le -ac 1 -ar 48000 -acodec pcm_s16le -i output.raw output.mp3  # decode
```

## Copyright & License
* Copyright (C) 2019 [bakatrouble](https://github.com/bakatrouble)
* Licensed under the terms of the [GNU Lesser General Public License v3 or later (LGPLv3+)](COPYING.lesser)
