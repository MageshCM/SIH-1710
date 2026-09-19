# Smart India Hackathon Workshop
# Date: 18-9-2026
## Register Number: 212223220053
## Name: Magesh C M
## Problem Title
SIH 1710: Enhancing Navigation for Railway Station Facilities and Locations
## 🚆 Problem Statement
Railway stations are complex environments with numerous facilities — ticket counters, platforms, restrooms, food courts, waiting areas. Passengers, especially in large or unfamiliar stations, struggle to navigate efficiently, leading to congestion and missed connections. A user-friendly, real-time, multi-platform navigation system is needed — one that also accounts for accessibility and can scale affordably across thousands of stations.

## 💡 Our Solution
Most navigation prototypes for this problem lean on BLE beacons + AR, which are expensive to install and maintain across 7,000+ Indian Railway stations and perform poorly indoors. RailSetu takes a different, more deployable approach:

QR-anchor + phone-sensor fusion positioning — cheap printed QR codes at key junctions, combined with phone accelerometer/gyroscope dead-reckoning for smooth in-between tracking. Near-zero hardware cost.
Crowd-density-aware dynamic rerouting — uses existing CCTV/turnstile footfall data to route passengers around congestion in real time.
Multilingual conversational assistant — passengers type or speak queries in Hindi/Tamil/Bengali/English; an LLM parses intent and destination, no menu-diving required.
Digital Twin CMS for station staff — drag-and-drop dashboard to update facility/layout changes instantly, pushed live to app and kiosks with no app-store delay.
Accessibility-first design — audio + haptic (vibration pattern) turn-by-turn guidance for visually impaired users; wheelchair-friendly routing that avoids stairs.
Kiosk-to-mobile handoff — scan a QR on a station kiosk to continue the same route on your own phone.
## ⚙️ How It Works
Passenger scans a QR anchor or opens the app inside the station.
Selects/speaks a destination (e.g., "Platform 6", "wheelchair route to restroom").
Route engine computes the shortest path over a pre-mapped station graph (nodes = junctions/facilities, edges = corridors/stairs/ramps) using A* search.
Live crowd-density data reroutes the path around congested zones if needed.
Step-by-step directions are shown on a 2D live map, spoken aloud, and (for visually impaired users) reinforced with vibration patterns.
Station staff update layouts anytime via the CMS dashboard — changes reflect instantly across app and kiosks.
## 🛠️ Tech Stack
Layer	Technology
Frontend (Mobile + Kiosk)	React.js, Tailwind CSS, PWA (installable, offline-capable)
Voice/Chat	Web Speech API (STT/TTS) + LLM API for multilingual intent parsing
Backend	Node.js (Express) or Django REST Framework
Route Computation	Python/JS graph + A* pathfinding (networkx / ngraph.graph)
Database	Firebase Firestore or Supabase (Postgres) — real-time sync for layout & crowd data
Auth	Firebase Auth / Supabase Auth (role-gated for staff CMS)
Deployment	Vercel (frontend), Render/Railway.app (backend)
## 📦 Dependencies
Frontend

react, react-dom, react-router-dom tailwindcss vite-plugin-pwa workbox-window html5-qrcode react-speech-recognition axios

Backend — Node/Express

express, cors, dotenv firebase-admin ngraph.graph / graphlib

Backend — Django (alternative)

django, djangorestframework networkx django-cors-headers psycopg2-binary

LLM / Voice

@anthropic-ai/sdk or openai Web Speech API (browser-native, no install)

Infra clients

firebase / @supabase/supabase-js

## 🎯 Key Features
✅ No expensive beacon hardware — QR + sensor fusion
✅ Real-time crowd-aware routing
✅ Multilingual voice/text assistant
✅ Live station digital twin, editable by staff
✅ Full accessibility support (audio + haptic + wheelchair routing)
✅ Seamless kiosk-to-mobile continuity
## 📊 Diagrams
System Architecture Diagram — /docs/architecture.png
Use Case Diagram — /docs/use-case.png
(See /docs folder for full diagrams and the detailed proposal.)

## 🚀 Getting Started
bash

## Clone the repository
git clone cd railsetu

## Install frontend dependencies
cd frontend npm install npm run dev

## Install backend dependencies
cd ../backend npm install # or pip install -r requirements.txt for Django npm run dev # or python manage.py runserver


## Proposed Solution / Architecture Diagram



<img width="1045" height="557" alt="Screenshot 2026-09-19 081932" src="https://github.com/user-attachments/assets/ec82fe7b-9acd-4985-bd7a-fbb39a472940" />

<img width="1017" height="567" alt="Screenshot 2026-09-19 081944" src="https://github.com/user-attachments/assets/efd5ea0e-ca0a-43d2-b4c6-08d1c36ca1a1" />





