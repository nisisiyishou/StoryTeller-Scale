# StoryTeller Scale

An interactive, AI-powered storytelling device for children that recognizes 3D-printed tokens and ambient light to generate and play custom audio stories—with matching LED visuals—via ChatGPT and Google Translate TTS. :contentReference[oaicite:0]{index=0}

---

## 🎬 Demo Video

[![Watch the demo](https://img.youtube.com/vi/4xTxv2r5DFQ/0.jpg)](https://youtu.be/4xTxv2r5DFQ)  
https://youtu.be/4xTxv2r5DFQ

---

## 🔍 Project Overview

StoryTeller Scale uses an ESP32, a load cell (HX711), a photoresistor, an 8×8 NeoPixel LED matrix and an I2S speaker to detect which animal token is placed and whether it’s day or night. It then:

1. Builds a prompt (“Tell me a 20-second nighttime story about a whale”)  
2. Calls OpenAI’s ChatGPT API to generate a concise narrative :contentReference[oaicite:1]{index=1}  
3. Segments the text and uses Google Translate TTS to play it back  
4. Displays pixel-art images and environmental sounds for immersion  
5. Resets to welcome state for the next interaction :contentReference[oaicite:2]{index=2}

---

## 🌟 Key Features

- **Object & Light Detection**  
  Weight thresholds distinguish tokens; light sensor toggles day/night. :contentReference[oaicite:3]{index=3}  
- **AI-Generated Stories**  
  Dynamic prompts sent to ChatGPT for on-the-fly story creation. :contentReference[oaicite:4]{index=4}  
- **TTS Playback**  
  Google Translate TTS API streams segmented audio via I2S. :contentReference[oaicite:5]{index=5}  
- **8×8 LED Matrix**  
  Pixel-art visuals map each token with color patterns converted via JSON. :contentReference[oaicite:6]{index=6}  
- **Finite-State Machine**  
  WELCOME → INIT → MEASURING → CHECK_LIGHT → OBJECT → STORY → RESET. :contentReference[oaicite:7]{index=7}  

---

## 📦 Hardware Components

- **ESP32 (FireBeetle 2 ESP32-E)** – controller & WiFi  
- **HX711 + Load Cell** – token weight measurement  
- **Photoresistor** – ambient light detection  
- **GlowBit 8×8 NeoPixel Matrix** – visual feedback  
- **MAX98357 I2S Amp & Speaker** – audio output  
- **Push Button** – start/reset interaction  
- **3D-Printed Enclosure & Tokens** – custom housings :contentReference[oaicite:8]{index=8}  

---

## ⚙️ Software & Code

- **Codebase**: Arduino sketch (`StoryTellerScale.ino`) with clear state-machine logic  
- **Libraries**:  
  - HX711 load-cell driver  
  - Adafruit_NeoPixel for LED matrix  
  - ArduinoJson for pixel-map JSON  
  - WiFi & HTTPClient for API calls  
  - ButtonDebounce for reliable input  
- **APIs**:  
  - **OpenAI ChatGPT** (`/v1/chat/completions`) for story text  
  - **Google Translate TTS** (`translate_tts`) for audio segments  
- **Image Conversion**: WLED-PixelArtConverter → JSON maps :contentReference[oaicite:9]{index=9}  

<details>
<summary>🔗 Source Code Repository</summary>

```text
https://github.com/nisisiyishou/StoryTeller-Scale
