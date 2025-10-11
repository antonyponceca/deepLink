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
- adb

## Install

```
$ git clone https://github.com/mathis2001/deepLink
$ cd deepLink
$ chmod +x deepLink.py
```
## Usage

```
$ ./deepLink.py [-h] (--adb | --apk APK | -l LAUNCH | -c CODE_SEARCH) [-p PACKAGE] [-s SERIAL] [-v] [-o]
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
  -o OUTPUT, --output OUTPUT
                        Save results in an output file
```

## Screenshots

### PoC Scenarios (BugBazaar)

<img width="1157" height="909" alt="BugBazaar Deeplink check" src="https://github.com/user-attachments/assets/5b61f25f-d001-40a8-bac6-65b44e2195d7" />
<img width="1649" height="53" alt="BugBazaar code search" src="https://github.com/user-attachments/assets/c807ab02-03bf-4c6d-a3e9-62be1b7ad706" />
<img width="1368" height="485" alt="BugBazaar Code Review" src="https://github.com/user-attachments/assets/ba149d07-e593-43c7-8f49-2683ea404eec" />

#### Insecure Deeplink handling leads to CSRF

<img width="1792" height="719" alt="BugBazaar CSRF" src="https://github.com/user-attachments/assets/1dda50bc-77de-4101-abfa-480d85e0920c" />

#### Insecure Deeplink handling leads to WebView Hijacking

<img width="1829" height="720" alt="BugBazaar WebView Hijacking" src="https://github.com/user-attachments/assets/aeebd276-b4e4-43ed-ad4c-8289a11a8aeb" />







