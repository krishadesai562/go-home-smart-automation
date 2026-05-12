# Go HOME — Smart Home Automation System

> A Wi-Fi-based home automation system with voice control and multi-device integration, built and deployed during my **Application Development Internship at TechSevin Solutions LLP** in Surat, India (2021–2022).

![Status](https://img.shields.io/badge/status-deployed-success)
![Platform](https://img.shields.io/badge/platform-ESP8266-blue)
![IoT](https://img.shields.io/badge/IoT-Blynk-brightgreen)
![Voice](https://img.shields.io/badge/voice-Google%20Assistant-orange)

---

## 📖 Overview

Go HOME is an end-to-end IoT solution that lets users control household appliances — lights, fans, outlets — from anywhere in the world using either a **mobile app, manual switch, or voice command** through Google Assistant. The system was prototyped, tested, and deployed as a real product during my internship.

The goal was simple but real: bring affordable home automation to households that don't want to rip out their existing electrical wiring or buy expensive smart switches. Our system retrofits onto standard switches — you keep your existing setup and gain remote/voice control on top.

---

## ✨ Key Features

- 🌐 **Remote control from anywhere** via Wi-Fi and the Blynk IoT cloud
- 🗣️ **Voice control** through Google Assistant integration ("Hey Google, turn on the bedroom light")
- 🔘 **Manual switch override** so the system always works even when Wi-Fi is down
- 📱 **Mobile app interface** with real-time device state sync
- 💡 **2-channel relay control** — expandable to more channels
- 🔄 **State synchronization** between physical switches, app, and voice commands

---

## 🧠 How It Works

```
   ┌──────────────────┐         ┌──────────────────┐
   │  Google          │         │  Blynk Mobile    │
   │  Assistant       │         │  App             │
   └────────┬─────────┘         └─────────┬────────┘
            │                             │
            └──────────────┬──────────────┘
                           │
                           ▼
                  ┌─────────────────┐
                  │   Blynk Cloud    │
                  │   (IoT Server)   │
                  └────────┬────────┘
                           │  Wi-Fi
                           ▼
                  ┌─────────────────┐
                  │  ESP8266 NodeMCU │
                  │  Microcontroller │
                  └────────┬────────┘
                           │
              ┌────────────┴────────────┐
              ▼                         ▼
     ┌────────────────┐        ┌────────────────┐
     │  Relay Module  │        │  Manual Switch │
     │  (Appliance 1) │        │  (Override)    │
     └────────────────┘        └────────────────┘
```

When a user issues a command — whether via voice, app, or manual switch — the ESP8266 microcontroller updates the relay state, which in turn switches the appliance on or off. The system uses **virtual pins** on Blynk to keep all interfaces in perfect sync: flip the physical switch, the app updates; tap the app, the physical switch state reflects it.

---

## 🛠️ Tech Stack

| Component | What I used |
|---|---|
| **Microcontroller** | ESP8266 (NodeMCU board) |
| **IoT Platform** | Blynk 2.0 |
| **Voice Integration** | Google Assistant via Blynk |
| **Firmware Language** | C++ (Arduino framework) |
| **Hardware** | 2-channel relay module, manual toggle switches, jumper wires |
| **Documentation** | Microsoft Word, draw.io for circuit diagrams |

---

## 📁 Repository Structure

```
go-home-smart-automation/
├── Code_ESP8266_Blynk2_2Relay_Button_NEW/   # ESP8266 firmware source
├── Diagrams/                                # Circuit diagrams and use cases
├── Presentations/                           # Project presentations
├── Report/                                  # Full project report
├── screenshots of circuit and software/     # Photos of the working circuit
├── Go Home(final).pdf                       # Complete project documentation
├── Weekly Progress Report.docx              # Internship progress logs
└── README.md                                # You are here
```

---

## 🚀 Setup & Replication

Want to build your own? Here's what you'll need:

### Hardware
- ESP8266 NodeMCU board
- 2-channel relay module (5V)
- Manual toggle switches (optional, for override)
- Jumper wires + breadboard
- Appliance(s) to control

### Software
1. Install the [Arduino IDE](https://www.arduino.cc/en/software)
2. Add the ESP8266 board manager URL in Preferences:
   `http://arduino.esp8266.com/stable/package_esp8266com_index.json`
3. Install the **Blynk** library via the Library Manager
4. Sign up for a free [Blynk account](https://blynk.io/) and create a template
5. Open the `.ino` file in this repo and replace the placeholder:
   ```cpp
   #define BLYNK_TEMPLATE_ID "YOUR_BLYNK_TEMPLATE_ID"
   ```
6. Upload to your ESP8266 — Wi-Fi credentials are configured through Blynk's provisioning flow on first boot.

### Wiring
Refer to the diagrams in the `Diagrams/` folder for the circuit layout.

---

## 🎓 What I Learned

This was my first taste of building software for the physical world, and it taught me a lot that wasn't in the textbooks:

- **Embedded constraints are real** — you can't just allocate memory carelessly when your chip has 80KB of RAM total
- **Edge cases matter more in hardware** — what happens if Wi-Fi drops mid-command? My code had to handle that gracefully
- **User onboarding is a feature** — we spent serious time making the Wi-Fi provisioning flow simple enough for non-technical users
- **Documentation isn't optional** when handing a product to someone else to install

This was also my introduction to working professionally — daily stand-ups, weekly progress reports, code reviews, and shipping something real to a customer.

---

## 👤 About

Built by **Krisha Desai** during my Application Development Internship at TechSevin Solutions LLP (Surat, India, 2021–2022).

I'm currently a Computer Science student at Brock University focused on application development, design, and project management.

🔗 [LinkedIn](https://www.linkedin.com/in/krisha-desai-850015194) · 📧 krishudesai562@gmail.com
