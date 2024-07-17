# Smart Distance Monitoring System with CAN Bus

## Project Overview

The Smart Distance Monitoring System is an embedded project using the STM32F407VG Discovery Kit. It measures distance using an HC-SR04 ultrasonic sensor and displays the readings on a 16x2 I2C LCD. The system features CAN bus communication to send distance data to a central node, with alert mechanisms like LEDs and a buzzer for distance threshold breaches. This project was completed in collaboration with my colleague, Wafe Tlili, and with the support of Centre Supérieur de Formation.

## Features

- **Distance Measurement**: Uses the HC-SR04 ultrasonic sensor to measure distances.
- **Real-time Display**: Displays the measured distance on a 16x2 I2C LCD.
- **CAN Bus Communication**: Transmits distance data to a central STM32F407 node.
- **Alert Mechanisms**:
  - Blue and Green LEDs to indicate different distance ranges.
  - Buzzer activation when distance exceeds 10 cm.
  - Push button to deactivate the buzzer.
- **Modular Design**: Two nodes - one for distance measurement and one central node for data aggregation.

## Components

1. **STM32F407VG Discovery Kit**
2. **HC-SR04 Ultrasonic Sensor**: For distance measurement.
3. **16x2 I2C LCD**: For displaying the measured distance.
4. **CAN Bus**: For communication between nodes.
5. **Buzzer**: For auditory alerts.
6. **LEDs**: Blue and green LEDs for visual distance indication.
7. **Push Button**: For deactivating the buzzer.

## System Architecture

### Nodes

1. **Distance Measurement Node**:
   - Interfaced with HC-SR04 sensor and 16x2 I2C LCD.
   - Measures distance and displays it.
   - Sends distance data via CAN bus.

   Below is a figure that describes the interfacing of the Distance Measurement Node:

   ![Distance Measurement Node](path/to/distance_measurement_node_figure.png)

2. **Central Node**:
   - Receives distance data from the measurement node.
   - Manages alert mechanisms (LEDs, Buzzer).
   - Processes data to determine when to activate/deactivate alerts.

   Below is a figure that describes the interfacing of the Central Node:

   ![Central Node](path/to/central_node_figure.png)

## Setup and Configuration

### Hardware Connections

1. **HC-SR04 Ultrasonic Sensor**:
   - TRIG_PIN connected to GPIO_PIN_10 (PORT E).
   - ECHO_PIN connected to TIM_CHANNEL_1.

2. **16x2 I2C LCD**:
   - Connected to I2C1 interface of STM32.

3. **CAN Bus**:
   - CAN_TX connected to appropriate GPIO pin.
   - CAN_RX connected to appropriate GPIO pin.

4. **LEDs and Buzzer**:
   - Blue LED connected to GPIO_PIN (PORT C).
   - Green LED connected to GPIO_PIN (PORT C).
   - Buzzer connected to GPIO_PIN (PORT A).

5. **Push Button**:
   - Connected to GPIO_PIN_0 (PORT A).

### Software Setup

1. **Install STM32CubeIDE**: Download and install [STM32CubeIDE](https://www.st.com/en/development-tools/stm32cubeide.html).
2. **Clone the Repository**: Clone this repository to your local machine.
   ```bash
   git clone https://github.com/Louay-Chernii/Smart-Distance-Monitoring-System-with-CAN-Bus/tree/master
   ```
3. **Open the Project**: Open the project in STM32CubeIDE.
4. **Build and Flash**: Build the project and flash the firmware to the STM32F407VG Discovery Kit.

## Acknowledgments

- **Wafe Tlili**: My colleague who collaborated with me on this project.
