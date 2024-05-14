# BiosDisplay Library Documentation

## Introduction

The BiosDisplay library is a simple Arduino library designed to facilitate the display of startup information and system diagnostics on an OLED display. It provides an easy-to-use interface for displaying battery status, temperature, and memory usage information, making it ideal for embedded systems projects where monitoring system health is essential.

## Features

- **Startup Logo Display**: Display a custom logo on the OLED display during startup.
- **BIOS Message**: Display a message indicating how to enter the BIOS or configuration menu.
- **Battery Status**: Monitor battery voltage and state of charge using the MAX17043 fuel gauge.
- **Temperature Monitoring**: Check the temperature of the ESP32 microcontroller.
- **Memory Usage**: Display information about free heap memory and the largest available memory block.

## Installation

To install the BiosDisplay library, follow these steps:

1. Download the latest release from the [GitHub repository](https://github.com/your-username/BiosDisplay).
2. Extract the downloaded ZIP file.
3. Copy the `BiosDisplay` folder to your Arduino libraries directory.
   - On Windows, this is typically located in `Documents\Arduino\libraries`.
   - On macOS, this is typically located in `Documents/Arduino/libraries`.
   - On Linux, this is typically located in `~/Arduino/libraries`.

## Usage

### Initialization

To use the BiosDisplay library in your Arduino sketch, include the `BiosDisplay.h` header file and create an instance of the `BiosDisplay` class. You need to specify the pin connected to the button used to enter the BIOS menu.

```cpp
#include <BiosDisplay.h>

#define BUTTON_PIN F1  // Change this to your actual button pin

BiosDisplay biosDisplay(BUTTON_PIN);

void setup() {
  Serial.begin(115200);
  biosDisplay.begin();
}

void loop() {
  biosDisplay.displayInfo();
  delay(1000);
}
```

### Customization

You can customize the library to suit your needs by modifying the logo displayed during startup or the message displayed to prompt the user to enter the BIOS menu. You can do this by editing the `displayLogo()` and `begin()` functions in the `BiosDisplay.cpp` file.

## Examples

The BiosDisplay library comes with an example sketch to help you get started. You can find it in the Arduino IDE by navigating to `File -> Examples -> BiosDisplay -> BiosDisplayExample`.

## Troubleshooting

If you encounter any issues while using the BiosDisplay library, please check the following:

- Ensure that your OLED display is properly connected to your ESP32 board.
- Verify that the `BUTTON_PIN` constant is set to the correct pin connected to your button.
- Check the wiring of your components and ensure they match the configuration in your sketch.

If you're still having trouble, feel free to open an issue on the [GitHub repository](https://github.com/your-username/BiosDisplay) for assistance.

## License

This library is released under the [CC BY-NC-SA 4.0 License](https://creativecommons.org/licenses/by-nc-sa/4.0/). See the `LICENSE` file included in the library for more information.

## Contributions

Contributions to the BiosDisplay library are welcome! If you have ideas for new features or improvements, feel free to open a pull request on the [GitHub repository](https://github.com/your-username/BiosDisplay).
