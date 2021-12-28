# Linux Android Backup

Linux Android Backup is a tiny shell script & Flutter app that makes securely backing up Android devices on Linux and macOS easy, without vendor lock-ins or using closed-source software that could put your data at risk. It's based on ADB but doesn't use the deprecated `adb backup` command.

**Status:** Works, albeit testers are needed (my testbench broke).

## Data backed up

- Apps (.apk files of installed apps)
- Internal storage (pictures, downloads, videos, Signal backups if enabled, etc)
- Contacts (exported in vCard format)

These 3 things are the majority of what anyone would want to keep safe, but we all have different expectations and requirements, so suggestions are welcome.

## Features

- Automatically restores backed up data.
- Works on macOS & Linux (including WSL), and supports *any* Android device.
- Backs up data not normally accessible through ADB using a native companion app.
- Tiny - the script is 5KB in size, and the companion app is around 15 megabytes.
- Doesn't use proprietary formats: your data is safe even if this script ever gets lost. Simply open archives created by this script using 7-Zip.
- Encryption is *forced* - you can't disable it.
- All data is compressed using 7-Zip with maximum compression settings.

## Installation

1. Install p7zip and adb (`sudo apt update; sudo apt install p7zip-full adb` on Debian).
2. Clone or download this repository.
3. Enable developer options on your device and run `backup.sh`.

## Running under Windows

1. Install the [Windows Subsystem for Linux](https://docs.microsoft.com/en-us/windows/wsl/install) and a distro (Debian or Ubuntu is recommended).
2. Continue with the steps above.

## TODO

Sorted by importance. PRs are appreciated.

- Write usage instructions
- Create a desktop GUI for newcomers (using Flutter maybe?)
- Improve mobile app by fixing bugs and making it more appealing
- Clean up the code

## License

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program.  If not, see <https://www.gnu.org/licenses/>.
