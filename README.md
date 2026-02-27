# Keylogger POC Keyboard

An Android Proof-of-Concept custom keyboard designed strictly for demonstrating the risks of third-party keyboards during mobile application penetration testing. All keystrokes are logged locally to Logcat; no data is saved to disk or transmitted over the network.

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
<img src="https://github.com/user-attachments/assets/4bdbe408-8b2a-40e7-a415-194139322ae7" alt="Home Screen" width="50%">

### Keyboard Settings
<img src="https://github.com/user-attachments/assets/5142d04e-ddfa-4cee-9bc3-f832019bb797" alt="Keyboard Settings" width="50%">

### The Custom Keyboard
<img src="https://github.com/user-attachments/assets/079ad80f-a49b-462d-91a3-408348fe2b69" alt="Keyboard" width="50%">

### Logcat Output
![Logcat Output](https://github.com/user-attachments/assets/4abb11f8-c245-4bc3-9e4c-19f6f31c5a8c)
