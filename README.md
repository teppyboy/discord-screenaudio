# discord-screenaudio

A very WIP custom discord client that supports streaming with audio on Linux,
made possible by the
[great work](https://github.com/edisionnano/Screenshare-with-audio-on-Discord-with-Linux)
of [@edisionnano](https://github.com/edisionnano) and the
[Rohrkabel library](https://github.com/Soundux/rohrkabel) by
[@Curve](https://github.com/Curve).

![Screenshot_20220718_194357](https://user-images.githubusercontent.com/48161361/179571245-11ea05f3-fb5e-4aef-9132-2736e122ef04.png)

## Known Issues

- Only works with **PipeWire**
- Only works on **X11**
- Can only share primary screen (no other screens or specific applications)

## Installation

If you are using Arch, you can build and install
[from the AUR](https://aur.archlinux.org/packages/discord-screenaudio). If you
aren't, you will have to [build it yourself](#building-from-source).

## Building from Source

### Requirements

- Basic building tools
- CMake
- Qt5 and QtWebEngine
- **PipeWire** (it currently doesn't work with PulseAudio)
- Git

On Debian:
`apt install -y build-essential cmake qtbase5-dev qtwebengine5-dev pkg-config libpipewire-0.3-dev git`

### Building

To build the program, run this in the source directory:

```bash
cmake -B build
cmake --build build --config Release
```

And then to optionally install it, run:

```bash
sudo cmake --install build
```

## How it works

This whole project is based on
[this](https://github.com/edisionnano/Screenshare-with-audio-on-Discord-with-Linux)
repository, which very nicely explains how to stream audio in the web version of
Discord. Basically: a virtual microphone is created which captures the
application audio, and this microphone is then fed to the Discord stream by
intercepting a API call of Discord.

## License

Copyright (C) 2022 Malte Jürgens

This program is free software: you can redistribute it and/or modify it under
the terms of the GNU General Public License as published by the Free Software
Foundation, either version 3 of the License, or (at your option) any later
version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with
this program. If not, see <https://www.gnu.org/licenses/>.
