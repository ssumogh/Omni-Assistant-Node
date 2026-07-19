# Omni-Assistant-Node
A voice-controlled assistant that listens, understands intent using an LLM, and triggers a real physical action — bridging speech processing, language models, and embedded hardware into one working pipeline.
**Status:** 🚧 In progress — build log below updates as work happens.

---

## What it does

Say something like *"I'm going to sleep"* → the system transcribes your voice, sends it to an LLM to extract intent, and sends a signal over serial to an ESP32, which triggers a physical action (e.g. an LED turns off, a servo rotates to close a curtain).

## Why this project

This isn't a pure software project or a pure hardware project — it's built to sit at the intersection of both, reflecting an ECE background with a focus on Generative AI:

- **Signal processing (ECE):** handling real microphone input, filtering noise (SNR handling) before it ever reaches a speech-to-text model
- **Applied GenAI:** using an LLM for intent recognition from transcribed speech — not just calling an API, but reasoning about how to make it reliable on ambiguous input
- **Embedded systems (ECE):** UART serial communication between a computer and an ESP32, PWM control for a servo motor

## Architecture

```
Mic Input → Noise Filtering (DSP) → Speech-to-Text → LLM Intent Recognition → Serial (UART) → ESP32 → Physical Action (LED / Servo)
```

## Tech stack

- **STT:** [TBD — Whisper API / AssemblyAI]
- **LLM:** Hosted API (Gemini / Groq) for intent recognition
- **DSP:** Python (basic noise filtering / SNR handling before STT)
- **Hardware:** ESP32, servo motor, LED, USB microphone
- **Comms:** UART serial between host machine and ESP32

## Build plan

- [ ] **Phase 1 — Thinking:** LLM intent recognition from text input (hardcoded test strings first)
- [ ] **Phase 2 — Senses:** Mic input pipeline with noise filtering, connect to STT
- [ ] **Phase 3 — Action:** ESP32 serial communication, PWM servo control
- [ ] **Integration:** End-to-end pipeline, mic → intent → hardware action
- [ ] **Polish:** Improve noise handling, expand intent vocabulary, clean up code

## Build log

*Updates as the project progresses — decisions made, problems hit, what was learned.*

---

**Author:** Sumogh — ECE undergrad, Generative AI minor, IIIT Dharwad
