# esphome-smart-display
esphome-smart-display
# ESP32-S3 4.0" Smart Display (`esphome-smart-display`)

A modular, high-performance ESPHome configuration for the 4.0-inch 480x480 ESP32-S3 capacitive touch display. Built using LVGL and ESP-IDF, this template features an embedded local web interface, auto-dimming power management, thermal safety throttling, and modular application packages.

---

## Hardware Overview

- **MCU**: ESP32-S3 (Dual-core 32-bit LX7, 240 MHz, Wi-Fi 4 + Bluetooth 5 LE)
- **Display Size**: 4.0-inch IPS LCD
- **Resolution**: 480 × 480 pixels (Square form factor)
- **Interface**: 16-bit Parallel / RGB Interface (ST7701S Driver IC)
- **Touch Panel**: Capacitive Multi-Touch (GT911 Controller)
- **Features**: Onboard USB-C for flashing/power, exposed GPIO expansion headers, ambient light/thermal monitoring capabilities.

### Where to Buy
You can purchase this board on AliExpress:
* [ESP32-S3 4.0" 480x480 Smart Display Board (Capacitive Touch)](https://www.aliexpress.us/item/3256808028364930.html)

---

## Features

- **Embedded Web Server (v2)**: Monitor and adjust device settings (such as backlight brightness) directly from any web browser on your network.
- **Power & Thermal Management**:
  - **Auto-Dimming**: Display dims to 10% brightness after 60 seconds of inactivity.
  - **Tap-to-Wake**: Touching the screen instantly restores full backlight brightness and resets the timer.
  - **Thermal Safeguard**: Automatically forces backlight brightness down to 20% if internal CPU temperatures exceed 75°C.
- **System Status App**: Shows IP address, Wi-Fi RSSI, CPU temperature, firmware version, and renders a dynamic QR code for direct web UI access.

---

## Accessing & Logging into the Web Server UI

Once flashed and connected to your Wi-Fi network, the device runs an embedded web server on port 80.

### Step 1: Find the Device IP Address
You can get the local IP address in two ways:
1. **On-Screen Display**: Look at the **System Status** page on the 4.0" display. The IP address and a scannable QR code are rendered directly on the screen.
2. **QR Code Scanning**: Scan the on-screen QR code with your phone camera to automatically open the web interface in your browser.

### Step 2: Open the Web UI
In your web browser (Chrome, Safari, Edge, etc.), type:
```text

### Step 3: Log In
When prompted for HTTP Basic Authentication credentials:

Username: admin (or the value configured in secrets.yaml for web_username)

Password: The password defined in your secrets.yaml under web_password.

Note: Once logged in, you can adjust the active Display Brightness slider in real-time, view sensor telemetry, and trigger OTA firmware updates.
http://<DEVICE_IP_ADDRESS>
