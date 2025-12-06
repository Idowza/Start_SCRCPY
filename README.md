# Start_SCRCPY

A convenient Bash wrapper script for [scrcpy](https://github.com/Genymobile/scrcpy) that automatically detects the latest installed version and launches it with optimized settings for wireless mirroring.

## Features

- **Auto-detection**: Automatically finds the latest version of `scrcpy` located in your `${HOME}/bin` directory (configurable).
- **Wireless Mirroring**: Connects to your device via TCP/IP.
- **Optimized Defaults**: Launches with:
  - H.265 video codec (`--video-codec=h265`) for better quality/bandwidth ratio.
  - Screen off on device (`--turn-screen-off`) to save battery.
  - Stay awake (`--stay-awake`) to prevent the device from sleeping.
  - No audio (`--no-audio`) for lower latency (can be overridden).
- **Flexible**: Accepts a custom IP address and passes any additional arguments directly to `scrcpy`.

## Prerequisites

- A Linux environment (Bash).
- `scrcpy` downloaded and extracted.
- An Android device with USB debugging enabled and connected to the same network.

## Installation

1. Clone this repository:
   ```bash
   git clone https://github.com/Idowza/Start_SCRCPY.git
   cd Start_SCRCPY
   ```

2. Make the script executable:
   ```bash
   chmod +x start_scrcpy
   ```

3. (Optional) Move the script to a directory in your `$PATH` for easy access.

## Configuration

Open the `start_scrcpy` script in a text editor to adjust the default configuration variables at the top of the file:

- `SCRCPY_PARENT_DIR`: The directory where you keep your `scrcpy` folders. Default is `${HOME}/bin`.
- `DEFAULT_DEVICE_IP`: The default IP address of your Android device. Default is `192.168.1.35`.

## Usage

### Basic Usage
Run the script to connect to the default configured IP:
```bash
./start_scrcpy
```

### Specify IP Address
Pass the IP address as the first argument to connect to a specific device:
```bash
./start_scrcpy 192.168.1.50
```

### Pass Additional Arguments
Any arguments after the IP address (or if the IP is provided) are passed directly to `scrcpy`.

Example: Connect to a specific IP and limit the max size:
```bash
./start_scrcpy 192.168.1.50 --max-size=1024
```

## License

This project is licensed under the terms of the [LICENSE](LICENSE) file.
