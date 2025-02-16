**Task 5:**


**Overview**
This project uses an ultrasonic sensor to measure distance and control an LED based on object proximity. The TRIG_PIN sends a pulse, while the ECHO_PIN measures the reflection time to calculate distance. If an object is within 10 cm, the LED turns ON instantly; otherwise, it remains OFF. The use of pulseIn() ensures fast and accurate measurements, while a 30ms timeout prevents delays, making the system highly responsive.

This system is useful for object detection, obstacle avoidance, and safety applications. It can be implemented in robotics, smart parking systems, automated doors, and security alarms to detect nearby objects and trigger actions accordingly. The fast response ensures real-time decision-making, making it ideal for critical applications. The project runs on the CH32V003F4U6 microcontroller, which features a 32-bit RISC-V core based on the RV32EC instruction set, ensuring efficient performance and low power consumption.

**COMPONENTS REQUIRED TO BUILD SMART ULTRASONIC PROXIMITY DETECTOR WITH LED ALERT:**

VSD SQUADRON MINI (CH32V003F4U6 chip with 32-bit RISC-V core based on RV32EC instruction set)
HC-SRO4 sensor
Bread Board
Jumper Wires

The SMART ULTRASONIC PROXIMITY DETECTOR WITH LED ALERT is built using essential electronic components to ensure accurate distance measurement and quick response. The VSD SQUADRON MINI, powered by the CH32V003F4U6 microcontroller with a 32-bit RISC-V core (RV32EC instruction set), serves as the brain of the system, handling sensor data and controlling outputs efficiently. The HC-SR04 ultrasonic sensor is used to detect object proximity by measuring the time delay between transmitted and received sound waves. A breadboard provides a flexible platform for assembling the circuit without soldering, while jumper wires ensure seamless electrical connections between the components. Together, these components create a fast, reliable, and responsive proximity detection system suitable for automation and safety applications.

![image](https://github.com/user-attachments/assets/3fe53937-70c1-43bb-baf0-d0c62ba70e68)

**Table for Pin connection:**

HC-SRO4 sensor to CH32V003x

HC-SRO4 sensor	CH32V003x Pin
VCC             	5 volts
GND	                ground
TRIGGER	            PD2
ECHO	            PD5
LED	                PD6


**WORKING OF THE CODE**

The code utilizes an ultrasonic sensor to measure the distance to an object and control an LED based on that distance. In the setup() function, the necessary pins are configured: TRIG_PIN (PD2) for sending the trigger pulse, ECHO_PIN (PD5) for receiving the reflected echo, and LED_PIN (PD6) to control the LED. In the loop() function, the TRIG_PIN sends a pulse to the ultrasonic sensor, causing it to emit an ultrasonic wave. The ECHO_PIN then listens for the echo and measures the time it takes for the wave to return. This duration is converted into a distance using the speed of sound. If the distance is less than 10 cm, the LED_PIN is set HIGH, turning on the LED; otherwise, it is set LOW to turn the LED off. This process repeats every 500 milliseconds, continuously monitoring the distance and adjusting the LED based on proximity. This setup can be used for proximity sensing, such as in obstacle detection or distance measurement applications.


**PROGRAMMING CODE**

![image](https://github.com/user-attachments/assets/77acd190-d5e4-4bc4-a214-2852c899e5f4)


