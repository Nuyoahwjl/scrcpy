### [简体中文](README_ZH.md)

`scrcpy` is an open-source application that allows you to control and display your Android device's screen through your computer. Here are the steps to install `scrcpy` on Windows:

## 1. **Download and Install Scoop** (if you don't have Scoop yet):

   Open Command Prompt (CMD) and run the following commands to install Scoop (make sure to enable PowerShell's execution policy first):

```bash
Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
iwr -useb get.scoop.sh | iex
```

## 2. **Install scrcpy via Scoop**:

   Run the following command in the Command Prompt:

```bash
scoop install scrcpy
```

## 3. **Install ADB** (if not installed yet):

```bash
scoop install adb
```

## 4. **Enable "USB Debugging"**

   Before connecting the device, ensure USB Debugging is enabled on your Android device. Usually, this can be done by going to “Settings” -> “System” -> “About Phone” and tapping the “Build Number” seven times, then going back to “System” where you will find “Developer Options” to enable “USB Debugging.”

## 5. Basic Usage

#### <u>*Enable Mirroring*</u>

First, ensure that USB Debugging is enabled on your device and connect it to your computer via a USB cable. Open Command Prompt/PowerShell on your computer, and start `scrcpy` by entering the following command:

```bash
scrcpy
```

#### <u>*Wireless Connection*</u>

To use `scrcpy` over Wi-Fi, first connect via USB and run the following command to set the device to listen for TCP/IP connections:

```bash
adb tcpip 5555
```

Find the IP address of your Android device, then disconnect the USB cable and use the following command to connect wirelessly:

```bash
adb connect DEVICE_IP:5555
scrcpy
```

Replace `DEVICE_IP` with your device's actual IP address.

#### <u>*Common Options*</u>

- **Adjust Resolution**:
  
  ```bash
  scrcpy --max-size 1024
  ```
  
  This limits the maximum width or height of the mirrored device screen to 1024 pixels.

- **Set Bitrate**:
  
  ```bash
  scrcpy --bit-rate 2M
  ```
  
  This sets the bitrate for data transfer to 2 Mbps.

- **Fullscreen Mode**:
  
  ```bash
  scrcpy --fullscreen
  ```
  
  Or use the shortcut `Ctrl` + `f` to toggle between fullscreen and windowed mode.

- **Read-only Mode**:
  
  ```bash
  scrcpy --no-control
  ```
  
  This disables controlling the device from the computer.

- **Crop the Device Screen**:
  
  ```bash
  scrcpy --crop 1920:1080:0:0
  ```
  
  This will display only a portion of the device screen, in the format `width:height:left:top`.

- **Keep Screen Awake**:
  
  ```bash
  scrcpy --stay-awake
  ```
  
  This keeps the device screen on while connected.

- **Show Touches**:
  
  ```bash
  scrcpy --show-touches
  ```
  
  This displays the physical touch points on the screen.

- **Turn off the Device Screen**:
  
  ```bash
  scrcpy --turn-screen-off
  ```
  
  This turns off the device screen while connected.

#### <u>*Keyboard Shortcuts*</u>

- `Ctrl` + `o`: Turn the device screen off/on.
- `Ctrl` + `p`: Pause/resume device screen mirroring.
- `Ctrl` + `r`: Rotate the device screen display.
- `Ctrl` + `h`/`Home`: Simulate pressing the Home button.
- `Ctrl` + `b`/`Back`: Simulate pressing the Back button.
- `Ctrl` + `m`/`Menu`: Simulate pressing the Menu button.
- `Ctrl` + `s`: Take a screenshot and save it to the default directory.
- `Ctrl` + `Shift` + `s`: Take a screenshot and copy it to the clipboard.

`scrcpy` offers a wide range of features, and the above are just a few examples. You can run `scrcpy --help` to see more available options.

## 6. **Effect Demonstration**
![](scrcpy.png)

