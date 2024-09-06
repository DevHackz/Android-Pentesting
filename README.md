# Android-Application-Pentesting

>
![android-g30bff2539_640](https://user-images.githubusercontent.com/59237881/222998869-6d1866de-3796-4744-bcd4-806fa016ab6f.png)

# Android Development

# For Beginners

* [Android-Architecture](https://www.tutorialspoint.com/android/android_architecture.html)
* [Intro-To-Mobile-Pentesting](https://www.hackthebox.com/blog/intro-to-mobile-pentesting)

 Youtube Videos In English :
 * [BitsPlease](https://www.youtube.com/watch?v=si1LhLHhmzk&list=PLgnrksnL_Rn09gGTTLgi-FL7HxPOoDk3R&index=12)
 * [Insider Learners](https://www.youtube.com/playlist?list=PLbytsNUpQrWG8bKy4wC4A8806mnGPfRhf)
 * [Hacking Simplified](https://www.youtube.com/watch?v=6-M_7O3A8AI&list=PLGJe0xGh7cH2lszCZ7qwsqouEK23XCMGp)

 Youtube Videos In Hindi :
 * [Fortify Solutions](https://www.youtube.com/watch?v=6DIeR8CtVww)
 * [Ubaid Ahmed](https://www.youtube.com/watch?v=0I6ciwP8190&list=PLseJXX1OcscKnhj-mUdqFu4VRZzZFH2Ex)

# PDF Books 
* [Android Security Internals An In-Depth Guide to Android's Security Architecture](https://www.pdfdrive.com/android-security-internals-an-in-depth-guide-to-androids-security-architecture-e178419522.html)
* [Learning Pentesting for Android Devices A practical guide](https://github.com/Dev-Hacks/Android-Pentesting/files/10893592/Learning.Pentesting.for.Android.Devices.A.practical.guide.to.learning.penetration.testing.for.Android.devices.and.applications.pdf)
* [Android Security Attacks and Defenses](https://github.com/Dev-Hacks/Android-Pentesting/files/10893633/Android.Security.Attacks.and.Defenses.pdf)


# Android SSL Pinning Bypass
* [Android SSL Pinning Bypass](https://github.com/DevHackz/android-ssl-pinning-bypass)

# How to find bug on android application


 1) [Testing-Frida](https://www.hackingarticles.in/android-penetration-testing-frida/) 
 2) [Testing-Drozer](https://www.hackingarticles.in/android-penetration-testing-drozer/)
 3) [ADB-Command-Cheatsheet](https://www.hackingarticles.in/android-pentest-lab-setup-adb-command-cheatsheet/)
 4) [Automated-Analysis-Using-MobSF](https://www.hackingarticles.in/android-pentest-automated-analysis-using-mobsf/)
 5) [Testing-Webview-Attacks](https://www.hackingarticles.in/android-penetration-testing-webview-attacks/)
 6) [Deep-Link-Exploitation](https://www.hackingarticles.in/android-pentest-deep-link-exploitation/)


# APK Download 
1) https://apk-dl.com/
2) https://en.uptodown.com/
3) https://en.aptoide.com/
4) https://www.apkmirror.com/
5) https://f-droid.org/en/
6) https://en.softonic.com/
7) https://androidapksfree.com/

# Tool For Windows 


1) [Appie](https://manifestsecurity.com/appie/)
    * Appie Framework is a popular open-source framework used for Android application penetration testing. It provides a comprehensive, self-contained environment specifically designed to facilitate testing of Android applications
 
---

# Objection Tool Usage Guide

This repository provides a comprehensive guide on how to use the Objection tool for mobile security testing. Objection is a runtime mobile exploration toolkit, powered by Frida, designed to help penetration testers assess the security of mobile applications without requiring a jailbreak or root access.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
  - [Prerequisites](#prerequisites)
  - [Installing Objection](#installing-objection)
- [Basic Usage](#basic-usage)
  - [Starting Objection](#starting-objection)
  - [Common Commands](#common-commands)
- [Advanced Usage](#advanced-usage)
  - [Bypassing SSL Pinning](#bypassing-ssl-pinning)
  - [Interacting with the File System](#interacting-with-the-file-system)
  - [Manipulating Application Data](#manipulating-application-data)
- [Troubleshooting](#troubleshooting)
- [Contributing](#contributing)
- [License](#license)

## Introduction

Objection is a powerful tool that allows security researchers to explore and test the security of mobile applications at runtime. It provides an easy-to-use interface for tasks like bypassing SSL pinning, manipulating application data, exploring the file system, and much more. Objection is particularly useful because it works on both Android and iOS devices without the need for root or jailbreak.

## Features

- **Bypass SSL Pinning**: Easily disable SSL pinning in mobile apps to intercept network traffic.
- **File System Exploration**: Access and manipulate the file system of the mobile app at runtime.
- **Runtime Manipulation**: Modify application behavior and data while the app is running.
- **Cross-Platform**: Supports both Android and iOS devices.

## Installation

### Prerequisites

Before installing Objection, ensure that you have the following installed on your system:

- **Python 3.x**: Objection is a Python-based tool and requires Python 3.x to run.
- **Frida**: Objection uses Frida under the hood. You can install Frida using pip:
  ```bash
  pip install frida-tools
  ```
- **ADB (Android Debug Bridge)**: Required for interacting with Android devices.

### Installing Objection

You can install Objection using pip:

```bash
pip install objection
```

After installation, verify that Objection is installed correctly by running:

```bash
objection --help
```

## Basic Usage

### Starting Objection

To start using Objection with a mobile application, first ensure that the app is running on the device. Then, launch Objection using the following command:

```bash
objection -g <app_package_name> explore
```

Replace `<app_package_name>` with the actual package name of the mobile app (e.g., `com.example.app`).

### Common Commands

- **Bypass SSL Pinning**:
  ```bash
  android sslpinning disable
  ```
  This command disables SSL pinning, allowing you to intercept HTTPS traffic.

- **Explore the File System**:
  ```bash
  android fs ls /
  ```
  Lists the files and directories in the root directory of the app's file system.

- **Dumping SQLite Databases**:
  ```bash
  android sqlite list
  android sqlite dump <database_name>
  ```
  Lists and dumps the contents of SQLite databases used by the app.

- **Inspecting Keychain/Shared Preferences**:
  ```bash
  android prefs list
  ios keychain dump
  ```
  Lists and dumps shared preferences on Android or keychain data on iOS.

## Advanced Usage

### Bypassing SSL Pinning

Objection makes it easy to bypass SSL pinning in mobile applications, which is useful for intercepting and analyzing HTTPS traffic during security assessments. Simply use the following command:

```bash
android sslpinning disable
```

### Interacting with the File System

You can explore and manipulate the file system of the app directly from the Objection command line:

- **List Files**:
  ```bash
  android fs ls /data/data/com.example.app/files/
  ```
- **Download a File**:
  ```bash
  android fs download /data/data/com.example.app/files/secret.txt
  ```

### Manipulating Application Data

Objection allows you to modify the data used by the app at runtime:

- **Change the Value of a Variable**:
  ```bash
  android hooking set class_variable com.example.app.ClassName variableName newValue
  ```

- **Trigger a Function**:
  ```bash
  android hooking call com.example.app.ClassName methodName arg1,arg2
  ```

## Troubleshooting

- **Objection Not Connecting**: Ensure that your device is properly connected via USB and that ADB is running for Android devices. For iOS, ensure that Frida is correctly installed on the device.
- **SSL Pinning Not Disabled**: Some apps may implement SSL pinning in ways that are resistant to Objection's default bypass method. In such cases, you may need to use custom Frida scripts.


---

# Bug Find Checklist For Android
* [workbook.securityboat.in](https://workbook.securityboat.in/bug-bounty/bug-bounty-checklist/bug-bounty-checklist-for-android)
* [book.hacktricks.xyz](https://book.hacktricks.xyz/mobile-pentesting/android-checklist)
* [blog.softwaroid.com](https://blog.softwaroid.com/2020/05/02/android-application-penetration-testing-bug-bounty-checklist/)
* [xmind.app](https://xmind.app/m/GkgaYH/)
* [hackinarticles](https://twitter.com/hackinarticles/status/1627571685187788800?t=fddGmsHKUxGbWL3C_vqyrQ&s=35)
 
# CTF & Chalenges 
1) InsecureShopApp : https://www.insecureshopapp.com
   GitHub : https://github.com/hax0rgb/InsecureShop
2) [Allsafe](https://github.com/t0thkr1s/allsafe) 
3) [InjuredAndroid](https://github.com/B3nac/InjuredAndroid)
4) [HpAndro1337](https://github.com/RavikumarRamesh/hpAndro1337)
5) [KGB_Messenger](https://github.com/tlamb96/kgb_messenger)

* More about android mobile CTF chalenges : [Awesome-Mobile-CTF](https://github.com/xtiankisutsa/awesome-mobile-CTF) 

# Telegram Channels 
* [Android-Security & Malware](https://t.me/androidMalware)

# Android Security Crash Course
 [Youtube](https://youtube.com/playlist?list=PLH5GW4W70qp_B2eptq1Qo7KM2S66M77hi)

# Root Detection Bypass Using Frida 
  https://codeshare.frida.re/@dzonerzy/fridantiroot/
  
  frida --codeshare dzonerzy/fridantiroot -U -f YOUR_BINARY
  
   Demo video :
   
   [Screencast.webm](https://github.com/Rupeesh-Patil/Android-Pentesting/assets/59237881/4a083ddc-aa44-45b3-995c-a8c9d094fe74)

