# Workshop on: Real-Time-Embedded-IoT-System

This repository provides all required materials to conduct a hands-on **Embedded Systems Workshop** using the **FireBeetle 2 ESP32-E**, MQTT, Node-RED, and cloud-based monitoring.

---

## 👨‍🏫 Authors

**Shama Satter**  
Biomedical and AIoT Researcher  
🔗 [Google Scholar](https://scholar.google.com/citations?user=AMwr_8sAAAAJ&hl)  
🔗 [LinkedIn](https://www.linkedin.com/in/shamasatter/)

**Raihan Bin Mofidul**  
Embedded Systems & IoT Researcher  
🔗 [Google Scholar](https://scholar.google.com.au/citations?user=RHXWFqIAAAAJ&hl)

For collaboration or technical queries, please feel free to reach out.

---

## 📚 Instructions 
| 🔧 AIoT Development    | 📖 Description                            | 🔗 Details |
|-------------------|----------------------------------------|---------|
| 💻 Embedded System    | Software sketches and circuit diagrams for FireBeetle 2 ESP32-E with 4 progressive examples | [View](https://github.com/xundullah/Real-Time-Embedded-IoT-System/blob/main/Embedded%20System/Instruction%20on%20Embedded%20System.md) |
| 🌐 Broker Setup       | Mosquitto broker installation, configuration, and user-password authentication | [View](https://github.com/xundullah/Real-Time-Embedded-IoT-System/blob/main/Broker%20Setup/Instruction%20on%20Broker%20Setup.md) |
| ☁️ Cloud Operations    | Node-RED dashboard setup, deployment, and real-time visualization widgets | [View](https://github.com/xundullah/Real-Time-Embedded-IoT-System/blob/main/Cloud%20Operations/Instruction%20on%20Cloud%20Operations.md) |



---

## 📚 Workshop Outline

| Phase | Title                                       | Description                                                                 |
|-------|---------------------------------------------|-----------------------------------------------------------------------------|
| 1️⃣    | LED Control with ESP32                     | Local digital I/O example: read a button, control onboard LED               |
| 2️⃣    | DHT22 Sensor Integration                   | Acquire room temperature and humidity using DHT22 sensor                    |
| 3️⃣    | Timestamped Sensor Data with NTP           | Attach date-time using WiFi and NTP client                                  |
| 4️⃣    | Real-Time MQTT Monitoring & LED Control    | Publish sensor data and control LED via MQTT broker and Node-RED dashboard |
| 🔁    | Broker + Cloud Ops Setup                    | Setup secure Mosquitto broker & run Node-RED dashboard on localhost/cloud  |

---

## 📁 Repository Structure


```

.
├── Broker Setup
│   ├── configured_files/
│   ├── Instruction on Broker Setup.md
│   └── mosquitto-2.0.22-install-windows.exe
│
├── Cloud Operations
│   ├── Screenshots/
│   ├── Instruction on Cloud Operations.md
│   └── node-v22.17.0-x64.msi
│
├── Embedded System
│   ├── 1__LED_On_or_Off
│   ├── 2__DHT22_Room_Temp_n_Hum
│   ├── 3__WiFi_n_NTP_Timestamp
│   ├── 4__Realtime_Monitoring_n_Control
│   ├── Screenshots/
│   └── Instruction on Embedded System.md
│
├── LICENSE
└── README.md

```

---

## Embedded System Examples

These four progressive examples are located in `/Embedded System`. Each sketch introduces a new concept in embedded programming, sensor interfacing, or IoT communication.

| Sketch No. | Description                                       | Key Components                      |
|------------|---------------------------------------------------|-------------------------------------|
| 1️⃣         | LED Toggle using onboard button                   | GPIO control, Serial output         |
| 2️⃣         | Temperature & Humidity Monitoring via DHT22       | DHT22, Sensor interfacing           |
| 3️⃣         | WiFi + NTP Timestamp Addition                     | WiFi config, NTPClient library      |
| 4️⃣         | MQTT-based Real-Time Monitoring & LED Control     | PubSubClient, JSON, MQTT subscribe  |

👉 See `Instruction on Embedded System.md` for detailed setup and wiring.

---

## 🌐 MQTT & Cloud Visualization

Set up local MQTT broker and use Node-RED dashboard to:

- Visualize real-time temperature & humidity
- Control LED using dashboard switch
- Monitor JSON payloads sent over MQTT

### Broker Setup:

📂 `Broker Setup/Instruction on Broker Setup.md`  
Includes Mosquitto install, user-password setup, and testing guidance.

### Node-RED Dashboard:

📂 `Cloud Operations/Instruction on Cloud Operations.md`  
Describes Node.js setup, Node-RED dashboard deployment, and UI creation using these widgets:
- LED Switch (`Dashboard_LED_ON.jpg`)
- Temperature Gauge & Level (`T_gauge.png`, `T_level.png`)
- Humidity Chart & Gauge (`H_chart.png`, `H_gauge.png`)
- Payload Text Grouping (`DT_txt.png`, `DT_T_H_LED_Grouping.png`)

---

## 🔌 Required Arduino Libraries

Install the following via Arduino Library Manager:

📚 **[✓] PubSubClient** by Nick O'Leary  
📚 **[✓] DHT sensor library** by Adafruit  
📚 **[✓] NTPClient** by Fabrice Weinberg  

📦 **[✓] Board Manager: esp32** by Espressif Systems  
➡️ Choose **FireBeetle 2 ESP32-E** from board list  
➡️ Select appropriate **COM port** before uploading

📷 *See screenshots in `Embedded System/Screenshots/` for guidance*

---

## 🖥 Prerequisites

- [Arduino IDE](https://www.arduino.cc/en/software)
- [Node.js (v22+)](https://nodejs.org/)
- [Mosquitto MQTT Broker](https://mosquitto.org/)
- [Node-RED](https://nodered.org/)

---

## 📌 Notes

- Test WiFi credentials before uploading
- Broker IP is typically: `192.168.137.1`
- Default MQTT topics:
  - Publish: `Tutor.DHT`
  - Subscribe: `Tutor.LED`
- Run `mosquitto -v -c MQTT-secure.conf` to start broker with user-password authentication

---

## Future Direction

### Smart-Ring-Health-Analytics-Platform

We will develop a system to estimate HbA1c and Blood Glucose using a Smart Ring and ESP32 monitor.

#### Workflow:

**1. The Smart Ring will record 1-minute PPG data and send it to the ESP32 via Bluetooth.**

**2. The user will manually enter age, gender, BMI, hypertension, and other details in the ESP32 monitor.**

**3. The ESP32 will extract important PPG features, such as:**
   - Heart rate, heart rate variability (SDNN, RMSSD)
   - Pulse amplitude, rise/decay time, systolic–diastolic ratio
   - Notch timing, pulse width, and LF/HF ratio

**4. The ESP32 will combine these PPG features with manual inputs and send them to the Server PC through IoT.**

**5. The Server will use these datasets to train a deep learning model that estimates HbA1c and Blood Glucose.**

**6. Once trained, the ESP32 will communicate with the Server in real time — the PPG and input data will be sent instantly, and the Server will return the HbA1c and Glucose predictions to display on the ESP32 monitor.**

---

## 🤝 License

This project is licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.

---

Happy prototyping! 🌐💡📡
