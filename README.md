# Keylogger POC Keyboard

An Android `InputMethodService` Proof-of-Concept designed specifically for demonstrating the risks of third-party custom keyboards during mobile penetration testing. 

This application functions as a standard, usable Android keyboard but operates entirely as an offline, non-malicious keylogger. Every keystroke is captured and printed directly to `Logcat` without ever being saved to disk or transmitted over the network.

## Features Built for Pentesting

1. **Native Typing Feel:** Includes tactile audio feedback exactly like a standard AOSP Android keyboard to feel authentic to clients during demonstrations.
2. **Visual Key Previews:** Pressing a key triggers a character popup above the finger (`keyPreviewLayout`), ensuring the keyboard doesn't look like a suspicious "dummy" app.
3. **Dedicated Banking MPIN Numpad:** Mobile banking apps frequently require users to input an MPIN on a 3x3 dialer pad. This keyboard includes a dedicated 3x3 layout designed specifically for testing this flow efficiently. 
   - Tap `123?` \> `NUM` to access the MPIN pad.
4. **Unified Logging:** All inputs across the QWERTY, symbols, and MPIN layouts are logged identically to Logcat using the standard `Key Typed: X` format.

## Setup & Building

You can build this project using Android Studio or the Gradle CLI.

### Using Android Studio
1. Open Android Studio and select **Open**.
2. Navigate to and select this repository's root folder.
3. Allow Gradle to sync.
4. Click **Build > Build Bundle(s) / APK(s) > Build APK(s)**, or click the **Run** button to install it directly to connected device/emulator.

### Using Gradle CLI
```bash
# Windows
gradlew.bat assembleDebug

# Mac/Linux
./gradlew assembleDebug
```

## How to Test on a Device

1. Install the built APK onto your test device or emulator.
2. Open the **Keylogger POC** app from your launcher.
3. Click **"Open Keyboard Settings"**.
4. Enable the **"Keylogger POC Keyboard"** in the Android system settings. 
   *(Note: You will see standard Android warnings that the keyboard may collect all text. This is what you are demonstrating).*
5. Open any application with text input (like Google Chrome, a Notes app, or your client's Banking App).
6. Switch your active keyboard to the **"Keylogger POC Keyboard"**.
7. Begin typing.

## Viewing Captured Data

Connect your device via ADB and filter the logs for the keylogger's tag:

```bash
# Windows
adb logcat | findstr "PocKeylogger"

# Mac/Linux
adb logcat | grep "PocKeylogger"
```

You will see output resembling:
```
D/PocKeylogger: Key Typed: [SHIFT]
D/PocKeylogger: Key Typed: S
D/PocKeylogger: Key Typed: e
D/PocKeylogger: Key Typed: c
D/PocKeylogger: Key Typed: r
D/PocKeylogger: Key Typed: e
D/PocKeylogger: Key Typed: t
D/PocKeylogger: Key Typed: [SPACE]
D/PocKeylogger: Key Typed: P
```

## Disclaimer

This project is intended strictly for authorized security testing, educational purposes, and proof-of-concept demonstrations. It does not perform any data exfiltration. Ensure you have explicit permission before using this software to test any device or application.
