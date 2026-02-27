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
   # Windows
   adb logcat | findstr "PocKeylogger"
   
   # Mac/Linux
   adb logcat | grep "PocKeylogger"
   ```
6. Type anything on the keyboard (including the dedicated 3x3 banking MPIN pad). All keystrokes will appear in your terminal.

## Screenshots

*(Add your screenshots here)*

- **[Insert Screenshot 1]**: Show the `Keylogger POC` App home screen with the "Open Keyboard Settings" button.
- **[Insert Screenshot 2]**: Show the Android System Settings page with the "Keylogger POC Keyboard" enabled.
- **[Insert Screenshot 3]**: Show the custom QWERTY or 3x3 MPIN layout open in a target application.
- **[Insert Screenshot 4]**: Show your terminal/command prompt displaying the captured `adb logcat` keystrokes.
