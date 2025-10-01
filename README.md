# deepLink
deepLink is a python script allowing to list and verify deeplinks from Android apps using an ADB access or an APK file.

## Prerequisites

- Python3
- Apktool
- argparse
- re
- tabulate
- colorama
- requests

## Install

```
$ git clone https://github.com/mathis2001/deepLink
$ cd deepLink
$ chmod +x deepLink.py
```
## Usage

```
$ ./deepLink.py [-h] (--adb | --apk APK | -l LAUNCH | -c CODE_SEARCH) [-p PACKAGE] [-s SERIAL] [-v]
```

### List Deeplinks using ADB

```
$ ./deepLink.py --adb -p com.example.xyz [--verify]
```

### List Deeplinks from an APK

```
$ ./deepLink.py --apk /path/to/app.apk [--verify]
```

#### Open a specific deeplink

```
$ ./deepLink.py -l app://deeplink.xyz
```

#### Search for potential deeplinks handling in Java / Kotlin code

```
$ ./deepLink.py -c /path/to/project
```

## Options

```
options:
  -h, --help            show this help message and exit
  --adb                 ADB Analyze
  --apk APK             APK analyze
  -l LAUNCH, --launch LAUNCH
                        Launch a deeplink
  -c CODE_SEARCH, --code-search CODE_SEARCH
                        Search for potential deeplink handling in JAVA / Kotlin code
  -p PACKAGE, --package PACKAGE
                        Package Name (ex: com.example.xyz)
  -s SERIAL, --serial SERIAL
                        Device/Emulator to use
  -v, --verify          Verify Assets Links
```
