# StoryTeller Scale

An interactive, AI-powered storytelling device for children that recognizes 3D-printed tokens and ambient light to generate and play custom audio stories - with matching LED visuals - using ChatGPT for story text and Google Translate TTS for audio.

---

## 🎬 Demo Video
[![Watch the demo](https://img.youtube.com/vi/4xTxv2r5DFQ/0.jpg)](https://youtu.be/4xTxv2r5DFQ)  
https://youtu.be/4xTxv2r5DFQ

---

## 🔍 Project Overview
StoryTeller Scale uses an ESP32, a load cell (HX711), a photoresistor, an 8×8 NeoPixel LED matrix, and an I2S speaker to detect which animal token is placed and whether it’s day or night. It then:
1. Builds a prompt (e.g., “Tell me a 20-second nighttime story about a whale”).  
2. Calls the OpenAI ChatGPT API to generate a concise narrative.  
3. Segments the text and uses Google Translate TTS to play it back.  
4. Displays pixel-art images and ambient effects on the LED matrix.  
5. Resets to a welcome state for the next interaction.

---

## 🌟 Key Features
- **Object & Light Detection:** Weight thresholds distinguish tokens; light sensor toggles day/night.  
- **AI-Generated Stories:** Dynamic prompts sent to ChatGPT for on-the-fly story creation.  
- **TTS Playback:** Google Translate TTS streams segmented audio via I2S.  
- **8×8 LED Matrix:** Pixel-art visuals mapped per token via JSON patterns.  
- **Finite-State Machine:** WELCOME → INIT → MEASURING → CHECK_LIGHT → OBJECT → STORY → RESET.

---

## 📦 Hardware Components
- ESP32 (FireBeetle 2 ESP32-E) — controller & Wi-Fi  
- HX711 + Load Cell — token weight measurement  
- Photoresistor — ambient light detection  
- GlowBit 8×8 NeoPixel Matrix — visual feedback  
- MAX98357 I2S Amp & Speaker — audio output  
- Push Button — start/reset interaction  
- 3D-Printed Enclosure & Tokens — custom housings

---

## ⚙️ Software & Code
- **Codebase:** Arduino sketch with clear state-machine logic.  
- **Libraries:** HX711, Adafruit_NeoPixel, ArduinoJson, WiFi, HTTPClient, (optional) debounce helper.  
- **APIs:**  
  - OpenAI ChatGPT (`/v1/chat/completions`) for story text  
  - Google Translate TTS (`translate_tts`) for audio segments  
- **Image Conversion:** Pixel-art to JSON maps for LED frames.

---

## 🗂 Folder Map (as committed)
- `Load cell frame - 4602226/`  
- `Picture/`  
- `model_stl/`  
- `model_rhino+gh/`  
- `video resource/`  
- `enclosure_laser cutting.dxf`  
- `model v1.f3d`, `model_final lasercutting v1.f3d`  
- `code.zip`  
- `video editing.wfp`

---

## 🔁 Clone with Git LFS
This repo includes large binaries (videos/CAD). To clone reliably:
```bash
git lfs install
git clone git@github.com:nisisiyishou/StoryTeller-Scale.git
