<div align="center">

# 🌱 VidhAI
### AI-Powered Agriculture Ecosystem for Indian Farmers & Consumers

**“The farmer doesn’t need to understand VidhAI — VidhAI understands the farmer.”**

![Android](https://img.shields.io/badge/Android-Available-3DDC84?logo=android&logoColor=white)
![Version](https://img.shields.io/badge/Version-1.0.0-42572A)
![Languages](https://img.shields.io/badge/Languages-13%2B-C2DBB9)
![Flutter](https://img.shields.io/badge/Flutter-3.x-02569B?logo=flutter&logoColor=white)
![Firebase](https://img.shields.io/badge/Firebase-Integrated-FFCA28?logo=firebase&logoColor=black)

### 📱 Download the Android App

[![Download APK](https://img.shields.io/badge/Download-VidhAI%20v1.0.0%20APK-42572A?style=for-the-badge&logo=android&logoColor=white)](https://raw.githubusercontent.com/VISHNUVS-1315/VidhAI-Public/main/releases/VidhAI-v1.0.0.apk)

**APK:** VidhAI v1.0.0 · **Size:** ~58.6 MB  
**Portfolio:** https://vishnuvs-1315.github.io/VidhAI-Public/

</div>

---

## 🌾 What is VidhAI?

**VidhAI** is an AI-powered agriculture platform designed to bring the farmer’s complete digital journey into one simple ecosystem — from **crop planning and farm decisions to disease support, market awareness, records, community and selling**.

The platform is designed around three access paths:

- **Farmer Console** — personalized farm guidance, crop planning, farm management and agricultural tools.
- **Consumer Console** — community, demand/supply discovery, market information and farmer connection.
- **AI Assistance Layer** — multilingual AI guidance with text, voice-enabled interaction and contextual actions across the app.

VidhAI focuses on Indian agriculture, multilingual usability, practical farm context and low-connectivity-friendly design.

---

## ✨ Latest VidhAI Capabilities

### 🧠 1. Live AI Crop Recommendation
VidhAI sends real farm and preference context to live AI instead of showing generic placeholder crops. Recommendations can consider **location, soil, water source, irrigation, previous crop, farm size, season, budget, crop type and duration preference**.

### 💬 2. Context-Aware AI Chat
The main assistant uses **Groq with `openai/gpt-oss-20b`** for responsive agricultural conversations. The assistant is designed to use farm context and provide concise, farmer-friendly answers.

### 👁️ 3. AI Crop Disease & Pest Support
Image-based crop analysis uses NVIDIA vision models to assist with disease/pest identification and provide structured guidance. The app includes multi-image and multi-pest analysis flows.

### 🌦️ 4. Weather & Daily Farm Guidance
Weather information is powered by **Open-Meteo**. Home and task flows combine weather context with farm activity planning.

### 📈 5. Market Price Intelligence
Market price features integrate **data.gov.in / AGMARKNET** data to help users view agricultural commodity prices and recent market information.

### 📒 6. Farm Management & Records
Farmers can maintain farm profiles, crop history, expenses, crop diary records, notes, fertilizer/pesticide records and crop lifecycle information.

### 🗓️ 7. Crop Planning & Calendar
Crop planning tools help organize crop stages, activities, reminders and farming tasks across the crop lifecycle.

### 🏛️ 8. Government Schemes & Agricultural Tools
VidhAI brings scheme discovery and practical tools such as fertilizer guidance, crop search/checking, market prices and farm utilities into one app.

### 🤝 9. Community + Demand/Supply
Farmers and consumers can participate in agriculture-focused community flows, share information and use demand/supply features to improve visibility between produce availability and consumer needs.

### 🔔 10. Smart Tasks & Notifications
Local notification and scheduling support helps users track farm tasks, reminders and important activities.

### 🗣️ 11. Multilingual & Voice-Friendly UX
VidhAI supports **13+ Indian languages** and includes on-device speech input/output capabilities for easier interaction.

---

## 👨‍🌾 Farmer Console

The Farmer Console is built around real farm context rather than one-size-fits-all advice.

**Main areas include:**

- Personalized onboarding and farm setup
- AI crop recommendation
- AI agriculture chat
- Crop disease/pest image analysis
- Weather and farm task guidance
- Market prices
- Government schemes
- Farm diary and expense tracking
- Crop lifecycle/history
- Crop calendar and planning
- Fertilizer/pesticide records and guidance
- Community and demand/supply
- Notifications and reminders

---

## 🛒 Consumer Console

The Consumer Console connects agricultural information and farmer interaction from the consumer side.

**Main areas include:**

- Consumer-focused home experience
- Agriculture community feed
- Demand posting and supply discovery
- AI chat adapted for consumer questions
- Market price information
- Crop/calendar information
- Rental machinery and scheme information where applicable
- Farmer/crop discovery and interaction
- Profile and language controls

---

## 🌐 Languages

VidhAI is designed for complete localized use across supported Indian languages:

**English, Tamil, Hindi, Telugu, Kannada, Malayalam, Marathi, Bengali, Gujarati, Punjabi, Odia, Assamese and Urdu.**

---

## 🤖 AI Model Routing

| VidhAI workload | Provider / model |
|---|---|
| Main App Chat | **Groq — `openai/gpt-oss-20b`** |
| Main / Deep Reasoning | **NVIDIA — Nemotron 3 Ultra 550B** |
| Crop Reasoning / Fast AI | **NVIDIA — Nemotron 3.5 Lightning 30B** |
| Vision / Disease Analysis | **NVIDIA — Nemotron 3 Nano Omni 30B Reasoning** |
| Safety | **NVIDIA — Nemotron 3.5 Content Safety** |

Model routing is handled on the backend so secrets are not exposed in the Android application.

---

## 🔌 APIs & Services Used

| Service | Purpose | API key in app? |
|---|---|---|
| **Groq API** | Main AI chat | No — server-side only |
| **NVIDIA NIM API** | Crop reasoning, vision and safety | No — server-side only |
| **data.gov.in / AGMARKNET** | Agricultural market prices | No — server-side only |
| **Open-Meteo** | Weather data | No key required |
| **Firebase** | Authentication, Firestore, Storage and messaging | Firebase client configuration only; privileged credentials remain server-side |
| **Render** | Secure Node.js/TypeScript backend hosting | Server environment |
| **Device Speech / TTS** | Voice input and output | On-device |

### 🔐 Secret Management

VidhAI never publishes real secret values in this repository or README. Production secrets are stored in backend environment variables such as:

```env
GROQ_API_KEY=
NVIDIA_API_KEY=
DATA_GOV_API_KEY=
FIREBASE_SERVICE_ACCOUNT_JSON=
```

Only the **variable names** are documented. Actual credentials stay in the secure backend environment.

---

## 🏗️ Technical Architecture

```text
                         ┌──────────────────────┐
                         │      VidhAI App      │
                         │  Flutter / Android   │
                         └──────────┬───────────┘
                                    │
                 ┌──────────────────┼──────────────────┐
                 │                  │                  │
                 ▼                  ▼                  ▼
        ┌────────────────┐  ┌────────────────┐  ┌────────────────┐
        │ Secure Backend │  │    Firebase    │  │   Open-Meteo   │
        │ Node.js / TS   │  │ Auth/DB/Store  │  │    Weather     │
        │    (Render)    │  └────────────────┘  └────────────────┘
        └───────┬────────┘
                │
       ┌────────┼───────────────┐
       │        │               │
       ▼        ▼               ▼
   ┌───────┐ ┌────────┐  ┌───────────────┐
   │ Groq  │ │ NVIDIA │  │ data.gov.in   │
   │ Chat  │ │  NIM   │  │ / AGMARKNET   │
   └───────┘ └────────┘  └───────────────┘
```

---

## 📶 Connectivity Design

VidhAI is **offline-aware**, not “AI fully offline.” Local preferences and selected records can remain available on-device, while live AI, current weather, market prices and cloud synchronization require internet access. This separation helps the app remain useful in unstable-network conditions without pretending live services are available offline.

---

## 🧰 Technology Stack

- **Frontend:** Flutter / Dart
- **Backend:** Node.js + TypeScript
- **Cloud & Identity:** Firebase
- **Backend Hosting:** Render
- **AI Chat:** Groq
- **AI Reasoning / Vision / Safety:** NVIDIA NIM
- **Weather:** Open-Meteo
- **Market Data:** data.gov.in / AGMARKNET
- **Local persistence:** Shared Preferences and app-managed local state
- **Notifications:** Flutter Local Notifications + WorkManager
- **Voice:** On-device Speech-to-Text and Text-to-Speech

---

## ✅ Current Build Status

- Android app build: **working**
- Web build: **working**
- Startup flow: **verified**
- Current app version: **1.0.0+1**
- Public APK: **VidhAI v1.0.0**

> The public APK is provided for project demonstration and evaluation. New source changes may be newer than the packaged public APK until the next APK is published.

---

## 📥 Download

**Direct APK:**  
https://raw.githubusercontent.com/VISHNUVS-1315/VidhAI-Public/main/releases/VidhAI-v1.0.0.apk

**Project Portfolio:**  
https://vishnuvs-1315.github.io/VidhAI-Public/

---

## 🎯 Vision

VidhAI aims to make agricultural technology practical for everyday use by bringing **AI guidance, farm records, disease support, live data, multilingual access and farmer–consumer connection** into one understandable platform.

<div align="center">

### 🌱 VidhAI — Smarter decisions from seeding to selling.

</div>
