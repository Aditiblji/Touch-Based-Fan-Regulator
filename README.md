# Touch-Controlled Multi-Speed Fan System (ESP32)

This project implements a **touch-based fan control system** using an ESP32 microcontroller.
Three capacitive touch sensors are used to toggle the fan ON/OFF at different speed levels without relying on mechanical switches. The system provides a smooth, durable and contact-less control mechanism suitable for smart-home applications.

## 🔧 **Features**

* Three independent touch sensors

  * **Sensor 1:** Low speed
  * **Sensor 2:** Medium speed
  * **Sensor 3:** High speed
* Toggle mechanism

  * Touch once → fan ON at associated speed
  * Touch again → fan OFF
* PWM-based motor control using `analogWrite`
* No mechanical components, ensuring longer lifespan and less maintenance
* Modular, extendable design

## 📌 **Hardware Used**

* **ESP32 Dev Module**
* **3 × Capacitive Touch Sensors (TTP223 or similar)**
* **NPN Transistor (BC548 or equivalent)**
* **Flyback Diode (1N4007)**
* **DC Fan (5V / 12V)**
* **Power Supply**
* **Current-limiting resistor for transistor base**
* **Breadboard and jumper wires**

## 🧩 **Circuit Overview**

* Each touch sensor output is connected to a dedicated GPIO pin.
* An NPN transistor acts as a driver to control the fan’s power.
* The ESP32 outputs a PWM signal to the transistor to regulate speed.
* A flyback diode protects components from motor back-EMF.

![Circuit Diagram](https://github.com/user-attachments/assets/00decd92-1e72-44c5-a648-477a2c5ae0e2)


## 📜 **Code Logic Summary**

* Each touch sensor has its own **toggle state** (ON/OFF).
* If a sensor is touched, its state flips.
* Only one speed is active at a time.
* PWM output controls fan speed depending on which sensor was activated.

## 🧠 **Program Flow**

1. Initialize GPIO pins and PWM channel.
2. Read all touch sensor states.
3. For each sensor:

   * If touched → toggle its ON/OFF state.
4. Determine which speed is active.
5. Apply PWM value to fan.
6. Loop continuously.

## 🎯 **Use Cases**

* Smart-home fan automation
* Touch-based appliances
* Education and embedded systems learning
* Low-cost interface prototypes
* Hygienic, no-contact control panels (kitchens, labs, hospitals)
