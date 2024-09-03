
# ESP32 Wi-Fi Connection Example

Welcome to the **ESP32 Wi-Fi Connection Example** repository! This project showcases how to connect an ESP32 microcontroller to a Wi-Fi network and retrieve basic network information using the Arduino IDE. It is designed for users who want to get started with Wi-Fi connectivity on the ESP32.

## 📦 Features

- **Wi-Fi Connection**: Easily connect your ESP32 to any Wi-Fi network using your SSID and password.
- **Connection Status**: Monitor the status of the connection attempt through the Serial Monitor.
- **Network Information**: Retrieve and display the ESP32’s IP address and the router's gateway IP address.

## 🚀 Getting Started

To use this example, follow these steps:

### 1. Clone the Repository

Clone this repository to your local machine using:
```bash
git clone https://github.com/yourusername/ESP32-WiFi-Connection-Example.git
```

### 2. Install the Arduino IDE

Ensure you have the [Arduino IDE](https://www.arduino.cc/en/software) installed. You will also need to install the ESP32 board support package.

### 3. Upload the Code

1. Open the `main.ino` file in the Arduino IDE.
2. Replace `Your_SSID` and `Your_PASSWORD` with your Wi-Fi network credentials.
3. Connect your ESP32 board to your computer using a USB cable.
4. Select the correct board and port in the Arduino IDE.
5. Click on the upload button to compile and upload the code to your ESP32.

### 4. View Results

Open the Serial Monitor (set the baud rate to 115200) to view the connection progress and network information.

## 📋 Code Explanation

Here’s a detailed breakdown of the code:

```cpp
#include <WiFi.h>
```

- **`#include <WiFi.h>`**: This line includes the Wi-Fi library required to handle Wi-Fi functions for the ESP32.

```cpp
const char* ssid = "Your_SSID";
const char* password = "Your_PASSWORD";
```

- **`const char* ssid`**: Replace `"Your_SSID"` with the name of your Wi-Fi network.
- **`const char* password`**: Replace `"Your_PASSWORD"` with your Wi-Fi network password.

```cpp
void setup() {
  Serial.begin(115200);
  WiFi.begin(ssid, password);
```

- **`void setup()`**: This function runs once when the ESP32 is powered on or reset.
- **`Serial.begin(115200)`**: Initializes serial communication at a baud rate of 115200 to print messages to the Serial Monitor.
- **`WiFi.begin(ssid, password)`**: Starts the process of connecting to the Wi-Fi network using the provided SSID and password.

```cpp
  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }
```

- **`while (WiFi.status() != WL_CONNECTED)`**: Continuously checks if the ESP32 is connected to the Wi-Fi network. If not, it waits for 500 milliseconds and prints a dot to indicate progress.

```cpp
  Serial.println("Connected to Wi-Fi");
  Serial.print("IP Address: ");
  Serial.println(WiFi.localIP());
  Serial.print("Gateway (Router IP): ");
  Serial.println(WiFi.gatewayIP());
}
```

- **`Serial.println("Connected to Wi-Fi")`**: Prints a message indicating that the ESP32 has successfully connected to the Wi-Fi network.
- **`Serial.print("IP Address: ")`**: Prints the IP address assigned to the ESP32 by the router.
- **`Serial.println(WiFi.localIP())`**: Prints the actual IP address of the ESP32.
- **`Serial.print("Gateway (Router IP): ")`**: Prints the IP address of the router (gateway) to which the ESP32 is connected.
- **`Serial.println(WiFi.gatewayIP())`**: Prints the actual IP address of the gateway (router).

```cpp
void loop() {
  // Empty loop
}
```

- **`void loop()`**: This function runs repeatedly after the `setup()` function. In this example, it is left empty because no further actions are needed.

## 🌟 Support

For any questions or issues, please open an issue on GitHub or reach out through relevant forums or community groups.

---

