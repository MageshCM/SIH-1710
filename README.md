# Smart India Hackathon Workshop
# Date: 19-09-2026
## Register Number: 212223220053
## Name: Magesh C M

## Problem Title
SIH 1710: Enhancing Navigation for Railway Station Facilities and Locations

## 🚆 Problem Statement
Railway stations are complex environments with numerous facilities — ticket counters, platforms, restrooms, food courts, waiting areas. Passengers, especially in large or unfamiliar stations, struggle to navigate efficiently, leading to congestion and missed connections. A user-friendly, real-time, multi-platform navigation system is needed — one that also accounts for accessibility and can scale affordably across thousands of stations.

## 💡 Our Solution
Most indoor navigation tools fail in Indian railways because passengers resist downloading dedicated 50MB+ apps when rushing to catch a train, and cellular data often drops inside dense concrete platforms.

**RailDrishti** solves this through a zero-install, offline-first ecosystem utilizing existing station infrastructure:

* **Wi-Fi Fine-Time Measurement (FTM) & RSSI Fingerprinting:** Utilizes existing RailWire / station Wi-Fi access points for passive multi-lateration positioning—requiring zero external sensor or beacon hardware.
* **App-Free Progressive Web Experience + WhatsApp Bot:** Passengers either access a lightweight browser-based 2.5D interactive map via a local captive portal (operates with zero active mobile internet) or interact via an official WhatsApp chatbot to fetch instant text/voice turn-by-turn guidance and route snippets.
* **Train Schedule & Coach Position Sync:** Integrates live NTES (National Train Enquiry System) data to guide passengers directly to their specific coach position (e.g., S3, B1) based on incoming train rake configuration.
* **Battery-Free Tactile & Visual Guidance for Accessibility:** High-contrast visual wayfinding modes, step-free ramp navigation filters for luggage and wheelchair users, and text-to-speech audio beacons triggered as passengers pass registered Wi-Fi zones.

---

## ⚙️ How It Works
1. **Seamless Entry:** The passenger connects to station Wi-Fi or scans a platform QR code. A lightweight WebGL captive portal opens instantly in Chrome/Safari without requiring an app installation.
2. **Train / Facility Search:** The passenger enters their PNR, train number, or desired facility (e.g., "Food stall near Coach B2, 12622 Tamil Nadu Express").
3. **Smart Graph Routing:** The routing engine evaluates a topological graph of the station, calculating optimal paths through foot-over-bridges (FOBs), escalators, and wheelchair-accessible ramps/lifts.
4. **Passive Positioning:** The client device detects nearby Wi-Fi BSSID signals and matches them against an edge-stored radio map using k-NN fingerprinting to establish accurate real-time location.
5. **Turn-by-Turn Wayfinding:** The interface delivers 2.5D floor-by-floor route rendering alongside multilingual voice guidance until the passenger reaches their berth or facility.

---

## 🛠️ Tech Stack

| Layer | Technology |
| :--- | :--- |
| **Frontend (Zero-Install)** | Three.js / WebGL, Tailwind CSS, Vite PWA, Workbox |
| **Chatbot Interface** | WhatsApp Cloud API / Meta Graph API, Python (Twilio fallback) |
| **Backend & Edge Server** | Node.js (Express) or Django running on station micro-servers |
| **Positioning Engine** | K-Nearest Neighbors (k-NN) RSSI Fingerprinting + Dead Reckoning |
| **Graph & Routing** | Custom Station Graph (Dijkstra / Contraction Hierarchies) + NTES API |
| **Database & Cache** | PostgreSQL with PostGIS extension + Redis caching |
| **Admin & Analytics** | React Admin Dashboard for station facility monitoring and crowd analytics |

---

## 📦 Dependencies

### Frontend
```text
react
react-dom
react-router-dom
tailwindcss
vite-plugin-pwa
workbox-window
three
@react-three/fiber
html5-qrcode
react-speech-recognition
axios
lucide-react
```
### Backend — Node/Express
```

express
cors
dotenv
pg
pg-hstore
redis
ngraph.graph
graphlib
axios
```
### Key Features

✅ Zero-Install Access: Works directly via web browser captive portal or official WhatsApp chatbot.

✅ Hardware-Free Deployment: Reuses existing RailWire Wi-Fi APs—no costly BLE beacons needed.

✅ Coach-Level Precision: Navigates directly to specific train coaches based on live rake composition.

✅ Offline-First Resilience: Fully functional through local station edge servers during mobile network dropouts.

✅ Universal Accessibility: Step-free wheelchair routing, high-contrast layouts, and multi-lingual voice beacons.

✅ Dynamic Facility Management: Station managers can disable malfunctioning escalators/lifts in real-time, instantly updating passenger paths.

## Proposed Solution / Architecture Diagram
<img width="1024" height="559" alt="8a9a9dd9-b731-4dfd-9914-768a3d780246" src="https://github.com/user-attachments/assets/d562487b-94fe-4b08-a007-79d207ffa082" />
