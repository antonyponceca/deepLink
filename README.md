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

## Screenshots

### Static Search from APK
<img width="922" height="718" alt="DeepLink-APK-Check" src="https://github.com/user-attachments/assets/3b373620-2d1a-4e1e-afab-bb42a04711c1" />

### Dynamic Search from ADB
<img width="709" height="643" alt="DeepLink-ADB-Check" src="https://github.com/user-attachments/assets/9b2f06b3-94f1-4fda-9af8-757c169c2bdf" />

### Code search by patterns
<img width="1765" height="670" alt="DeepLink-Code-Search" src="https://github.com/user-attachments/assets/3ac870c7-a131-48fc-9813-a546ed95d0b6" />

### Launching a deeplink (insecure deeplink handling to webview hijacking example)
<img width="1600" height="479" alt="DeepLink-Launch" src="https://github.com/user-attachments/assets/6e313a1d-7123-4305-8f77-52e693c9d5cf" />
