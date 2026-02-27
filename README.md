# Keylogger POC Keyboard

An Android Proof-of-Concept custom keyboard designed strictly for demonstrating the risks of third-party keyboards during mobile penetration testing. All keystrokes are logged locally to Logcat; no data is saved to disk or transmitted over the network.

## Installation

1. Go to the **[Releases](../../releases)** section of this repository.
2. Download the latest `.apk` file.
3. Install the APK on your Android test device or emulator.

## Usage

1. Open the **Keylogger POC** app from your Android launcher.
2. Click **"Open Keyboard Settings"**.
3. Enable the **"Keylogger POC Keyboard"** in the Android system settings. 
4. Open any application with text input (browser, notes, client app, etc.) and switch your active keyboard to the **"Keylogger POC Keyboard"**.
5. Connect your device via ADB and run the following command to monitor the keylogger output in real-time:
   ```bash
   # Windows (PowerShell)
   adb logcat | Select-String "PocKeylogger"
   
   # Mac/Linux
   adb logcat | grep "PocKeylogger"
   ```
6. Type anything on the keyboard, all keystrokes will appear in the logs.

## Screenshots

### Home Screen
![Keylogger POC App home screen](screenshots/Keylogger%20POC%20App%20home%20screen.jpg)

### Keyboard Settings
![Keyboard Settings](screenshots/Keyboard%20Settings.jpg)

### The Custom Keyboard
![Keyboard](screenshots/Keyboard.jpg)

### Logcat Output
![Logcat](screenshots/logcat.jpg)
