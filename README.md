# AirNote AI — Version 2.0 🚀

> **iQOO Hackathon 2026 Submission**  
> *A photo saves the final board. AirNote saves the way the teacher got there.*

[![Hackathon](https://img.shields.io/badge/iQOO--Hackathon-2026-blue)](https://github.com/Mithil-7/AirNote/tree/Version-2.0)
[![Branch](https://img.shields.io/badge/Branch-Version--2.0-indigo)](#)
[![On-Device](https://img.shields.io/badge/Compute-100%25%20On--Device%20NPU-success)](#)
[![License](https://img.shields.io/badge/License-MIT-lightgrey)](#)

---

## 📌 Overview

In fast, equation-dense lectures (JEE/NEET coaching, STEM degrees), students face an impossible tradeoff: **copy the board or listen to the explanation**. Doing both leads to missing half of each. 

Existing solutions fail in isolated silos:
* **Photo Scanners:** Save only the static, final state after intermediate steps are erased.
* **Audio Recorders:** Provide contextless transcripts without visual board synchronization.

**AirNote AI** bridges this gap. Running entirely on-device via the Snapdragon NPU, AirNote monitors the lecture board, detects new lines the moment they appear (occlusion-aware), and **fuses the exact sentence spoken by the instructor to the specific equation written on the board**.

---

## ✨ Key Features (v2.0)

* **📸 Occlusion-Aware Delta Detection:** Captures board updates only after the instructor steps away from the frame.
* **🎙️ Spoken-Context Fusion:** Time-aligns real-time on-device ASR (speech-to-text) directly to board step deltas.
* **📐 Equation & Math OCR:** Renders handwritten chalkboard math into clean LaTeX structures.
* **🧠 Conversational Study Layer (Stretch Goal):** Offline, on-device RAG enabling students to ask questions like *"What did sir say about eigenvalues?"* answered directly from their own lecture data.
* **🔒 100% On-Device & Private:** Zero internet required, zero cloud API latency, and zero recurring per-student costs. Built for tier-2/3 Indian classrooms with spotty connectivity.

---

## 🏗️ Architecture Flow

```text
[ Camera Preview ] ---> [ Frame Differencing ] ---> [ Occlusion Check ]
                                                               |
                                                     (Board Delta Captured)
                                                               |
[ On-Device Speech ] -> [ Timestamp Alignment ] ----> [ Fused Note Engine ]
                                                               |
                                                     [ Local Vector Store ]
                                                               |
                                                     [ Offline RAG / Tutor ]
