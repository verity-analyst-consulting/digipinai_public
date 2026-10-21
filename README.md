# DIGIPIN AI 📍 — Intelligent Digital Address & Location Platform

![Status: Live / Production](https://img.shields.io/badge/status-Live%20%2F%20Production-brightgreen.svg)
![Owner: Verity Analyst Consulting Inc.](https://img.shields.io/badge/owner-Verity%20Analyst%20Consulting%20Inc.-indigo.svg)
![Website: digipinai.in](https://img.shields.io/badge/website-digipinai.in-blue.svg)
![License: Proprietary Enterprise](https://img.shields.io/badge/license-Proprietary-lightgrey.svg)

🌐 **Live Website:** [https://digipinai.in](https://digipinai.in)

---

## 1. What is DIGIPIN AI?

**DIGIPIN (Digital Postal Index Number)** is a modern way to find any exact spot in India using a short, 10-character code (such as `4PJ-779-9TJT`). Think of it like a super-precise digital address for every single home, shop, park, tree, or building! The underlying grid concept was created by the **Department of Posts (Government of India)** and **IIT Hyderabad** so anyone can share and find locations easily.

**DIGIPIN AI** turns this digital address system into a smart, conversational chat assistant. Instead of struggling with long, confusing street addresses or complicated GPS coordinates, you simply type a place name, street address, coordinate, or DIGIPIN into the chat box. DIGIPIN AI instantly finds the spot, shows it on an interactive map, explains nearby landmarks in plain English, and gives you a one-click QR code or Google Maps link to share.

---

## 2. How the Magic of 4×4 Grids Works (In Plain English)

Imagine you want to tell a friend *exactly* where you are standing on a giant playground map:

1. **First Box:** DIGIPIN starts by dividing the entire map of India into **16 big boxes** (a 4×4 grid). Each box is given a special letter or number from a 16-character set (`2, 3, 4, 5, 6, 7, 8, 9, C, F, J, K, L, M, P, T`) following a spiral path from the center outward.
2. **Zoom In:** Once you pick the box where your location sits (for example, box `4`), we dive inside that box! That single box is divided *again* into 16 smaller boxes, and we pick the matching one (say, `P`).
3. **Repeat 10 Times:** Big box → Smaller box → Tiny box. We repeat this zoom-in process **10 times**. By the 10th character, the code points to a tiny square on the ground that is just **4 steps wide** (about 4 meters by 4 meters)!

> **What about Latitude & Longitude?**
> Think of them as the hidden lines on the map itself. **Latitude** is like rungs on a ladder going Up and Down (North/South), and **Longitude** is long lines going Left and Right (East/West). DIGIPIN uses these lines behind the scenes to draw the 16 boxes in the exact same spot every time.

### Real-World Example from the About Page

* **Place:** **ISKCON Temple, Bengaluru**
* **GPS Coordinates:** `13.0098°N, 77.5511°E`
* **DIGIPIN:** `4PJ-779-9TJT`

As DIGIPIN zooms in 10 times to find the temple:
* **Step 1 (`4`):** Narrowed down to a ~1,000 km region of Southern/Central India.
* **Step 2 (`P`):** Narrowed down to a ~250 km box covering Southern Karnataka.
* **Step 3 (`J`):** Narrowed down to a ~63 km box around Bengaluru.
* **Step 4 (`7`) → Step 6 (`9`):** Narrowed down to the neighborhood (~978 meters).
* **Step 7 (`9`) → Step 10 (`T`):** Pinpointed right to the **~4-meter spot** at ISKCON Temple (`4PJ-779-9TJT`)!

---

## 3. Purpose: Why Use DIGIPIN AI?

1. **Pinpoint Accuracy (4m × 4m):**
   Standard 6-digit postal pincodes cover a huge neighborhood. A DIGIPIN points to a specific 4-meter doorstep—reducing confusion for food deliveries, couriers, and emergency ambulances in remote or crowded areas.
2. **Covers Every Corner of India:**
   Works everywhere across India, including rural villages, farms, dense forests, and even out at sea where street names and house numbers do not exist.
3. **Permanent & Future-Proof:**
   Even if a road name changes or new buildings are constructed, a location's DIGIPIN never changes because it is based purely on its spot on the Earth.
4. **Private & Safe:**
   A DIGIPIN only identifies a physical spot on a map. It never stores or exposes anyone's name, phone number, or personal details.
5. **Smart AI Assistance:**
   Real-world Indian addresses often include landmarks like *"near Mamta Hospital"* or *"3rd Cross"* that confuse regular maps. DIGIPIN AI uses **Google Gemini** and **local AI models (Ollama)** along with **LocationIQ** to clean up messy addresses, find nearby landmarks, and locate your spot reliably.

---

## 4. Usage Guide & Examples

Simply open the chat window on [digipinai.in](https://digipinai.in) and type what you want to find, or click one of the starter buttons.

### A. Encoding (Turn an Address or GPS Coordinate into a DIGIPIN)

* **Landmark / Address to PIN:**
  ```text
  Encode ISKCON Temple, Bengaluru
  ```
  ```text
  Encode Shree Ramjanmbhumi Temple Ayodhya
  ```
  ```text
  Encode Rani Chennamma Circle, Belagavi
  ```
* **Standard GPS Coordinates to PIN:**
  ```text
  Encode 27.1751, 78.0421
  ```
  ```text
  Encode 15.867287, 74.5117036
  ```
* **Directional Coordinates to PIN:**
  ```text
  Encode 13.0098°N, 77.5511°E
  ```

### B. Decoding (Turn a DIGIPIN Back into a Map Location & Address)

* **PIN to Location & AI Landmark Summary:**
  ```text
  Decode 4PJ-779-9TJT
  ```
  ```text
  Decode 4K8-9ML-82K7
  ```
  ```text
  Decode XJ7-89L-KK
  ```

### C. Asking General Questions

You can also ask everyday questions in the chat box:
```text
Where is this PIN located?
```
```text
Why are these two coordinates different for the same landmark?
```

### D. Useful One-Click Tools in Every Reply

Whenever DIGIPIN AI finds a location, it displays an interactive map along with five handy buttons right below the message:
* **QR Code:** Generates a scannable QR code for the DIGIPIN that you can download as a PNG image.
* **Copy Info:** Copies the DIGIPIN, street address, landmark, and Google Maps link to your clipboard in one click.
* **Maps:** Opens the exact coordinates directly in Google Maps.
* **Share:** Lets you send the DIGIPIN and map link directly via **WhatsApp** or **Email**.
* **JSON:** Displays the clean technical details for software developers.

---

## 5. Running Locally (For Developers)

If you want to run DIGIPIN AI on your own computer, you only need two terminal windows: one for the **Backend (Port 8000)** and one for the **Frontend (Port 5173)**.

### Prerequisites
* **Python 3.11+**
* **Node.js v18+**
* **Ollama** (optional, for local AI fallback) and/or a **Google Gemini API Key**

### Step 1: Start the Backend Service (Port 8000)
```bash
cd apps/ai_orchestrator
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

# Configure your environment variables (GEMINI_API_KEY, LOCATIONIQ_API_KEY, OLLAMA_URL)
cp .env.example .env

# Start the server
uvicorn main:app --reload --port 8000
```

### Step 2: Start the Frontend Web App (Port 5173)
```bash
cd apps/frontend
npm install
export VITE_API_BASE=http://localhost:8000
npm run dev
```
Open your browser and visit `http://localhost:5173`.

---

## 6. Acknowledgements

* **Department of Posts, Government of India**
* **Indian Institute of Technology (IIT), Hyderabad**
* **National Remote Sensing Centre (NRSC), ISRO**

*(Note: DIGIPIN AI is an independent intelligent platform built on top of the open-source Apache 2.0 DIGIPIN grid specification and is not officially affiliated with India Post.)*

---

## 7. Intellectual Property & Ownership Notice

**PROPRIETARY & CONFIDENTIAL — VERITY ANALYST CONSULTING INC.**

* **Conceived, Architected, and Owned By:** Verity Analyst Consulting Inc. / Pavan Praveen Kulkarni.
* **Initial Inception:** 2025–2026.
* **Corporate Namespace:** `github.com/verity-analyst-consulting/digipinai` (Private Restricted Repository).
* **Scope of Protection:** This document, the DIGIPIN AI orchestration engine, multi-stage AI geocoding fallback logic, interactive 10-step grid visualizer, web application interface, and all forthcoming derivative works, source code modules, and associated documentation are the sole intellectual property of **Verity Analyst Consulting Inc.**
* **Clean-Room Development Assurance:** Conceived and developed entirely independently on personal equipment and outside business hours, without the use of third-party employer resources, proprietary networks, confidential databases, or corporate assets.

*© 2026 Verity Analyst Consulting Inc. All rights reserved.*
