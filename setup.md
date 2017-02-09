React Native 101
===

By the end of this workshop, you should be comfortable setting up a React Native development environment, putting together a basic application and deploying it to an emulator or a real Android device.

We'll be focusing on Android on Windows for the purpose of this tutorial. If you have a Mac, the steps will be mostly the same aside from configuring environment variables (grab me for assistance if you need to).

Dependencies
---

1. [NPM 6.x or later](https://nodejs.org/en/)
2. [JDK 8](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)
2. [Android Studio](https://developer.android.com/studio/index.html) - it's possible to get away with just the command line tools and SDK, but recommend the full option as it walks you through SDK setup and is helpful if you need to drop down into native Java plugins at a later stage
3. Android SDK 6.0 - Android Studio > Tools > Android > SDK Manager > SDK Platforms
4. Android Build Tools 23.0.1 and 23.0.3, Google APIs - Android Studio > Tools > Android > SDK Manager > SDK Tools -> Show Package Details
5. If you don't have a physical Android device, also tick Intel x86 Atom System Image, Intel x86 Atom_64 System Image, Google APIs Intel x86 Atom_64 System Image, Performance (Intel ® HAXM) and Android Virtual Device

Configuration
---

### Environment Variables

1. **ANDROID_HOME** *%LOCALAPPDATA%*\Android\SDK
2. **JAVA_HOME** *%PROGRAMFILES%*\Java\jdkVERSION
3. **PATH** *%PATH%*;*%ANDROID_HOME%*\platform-tools

Installation
---

1. npm install -g react-native-cli