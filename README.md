# Heart Sound Analysis | PCG Signal Processing

**Biomedical Signal Processing · Digital Phonocardiography · Internet of Medical Things (IoMT)**

A course project from the **Laboratory of Internet of Medical Things (IoMT)** at **Politecnico di Milano (2025/2026)**. This repository presents the **Python-based heart-sound analysis** component of a group project investigating a digital phonocardiography (PCG) prototype.

> **Research and education only.** This analysis is not a clinically validated medical device and must not be used for diagnosis.

## Project overview

The project explores how recorded heart sounds can be filtered, segmented, and analyzed to extract cardiac timing and acoustic features. The primary input is a **PCG audio recording (WAV)**.

### Processing pipeline

```text
PCG recording (WAV)
        |
        v
Band-pass + notch filtering
        |
        v
Wavelet denoising
        |
        v
Shannon-energy envelope
        |
        v
Candidate S1 / S2 detection
        |
        v
Cardiac-cycle segmentation
        |
        v
Heart-rate, temporal & spectral features
```

## Signal-processing methods

| Stage | Method | Purpose |
| --- | --- | --- |
| Preprocessing | Butterworth band-pass (**25–200 Hz**) | Retain the main PCG frequency range |
| Interference removal | **50/100/150 Hz** notch filtering | Reduce mains-related spectral interference |
| Denoising | Wavelet-based denoising | Suppress background noise |
| Envelope extraction | Shannon-energy envelope | Highlight potential heart-sound events |
| Segmentation | Candidate **S1/S2** detection | Identify heart-sound timing and cardiac cycles |
| Feature extraction | Timing, amplitude, spectral and morphology features | Characterize acoustic patterns |
| Visualization | Waveforms and spectrograms | Inspect processing stages and outputs |

## Example results

The accompanying course report describes one approximately **24.92-second recording**, sampled at **500 Hz**, with:

- **29** detected S1/S2 pairs and extracted cardiac cycles
- An estimated heart rate of approximately **73.4 bpm**

These results describe **one exploratory recording**, not diagnostic accuracy or clinical validation.

## IoMT prototype context

The broader **group project** also documented the design of a connected PCG prototype involving:

- **Arduino Nano ESP32** microcontroller
- **SEN-14262** acoustic sensor
- **Bluetooth Low Energy (BLE)** communication
- **OLED** display and an **Altium-designed PCB**

**Scope clarification:** this repository contains the Python signal-analysis material. Firmware, PCB design sources, and application source code are **not included**. The repository does not demonstrate a fully reproducible end-to-end medical device.

## Repository contents

| File | Description |
| --- | --- |
| `PCG_Analysis.ipynb` | Exploratory Jupyter notebook for PCG processing |
| `pcg_analysis.py` | Python script exported from the notebook |
| `requirements.txt` | Python dependencies (if present in this repository) |
| `PCG_Report_2026.pdf` | Course report (if included) |
| `PCG_Full_Professional_Presentation.pptx` | Course presentation (if included) |

## Installation and usage

**1. Install dependencies** (Python 3.10+ recommended):

```bash
pip install -r requirements.txt
```

**2. Provide an input recording.** Place a PCG WAV file that you have permission to use in the repository folder, named `Test Data.wav` (or adjust the path in the code).

**3. Run the notebook:**

```bash
jupyter lab
```

Open `PCG_Analysis.ipynb` and run the cells in order. Alternatively, execute the script:

```bash
python pcg_analysis.py
```

> The notebook and script have not been independently validated across environments. Some cells may require interactive execution or minor local path adjustments.

## Limitations

- S1/S2 segmentation and acoustic indicators are exploratory and can fail on noisy or unfamiliar recordings.
- No clinical sensitivity, specificity, or generalization claims are made.
- Publish physiological recordings only when you have appropriate permission and consent.
- The prototype must not be used to guide medical or patient-care decisions.

## Academic context

**Course:** Laboratory of Internet of Medical Things (IoMT)  
**Institution:** Politecnico di Milano  
**Academic year:** 2025/2026  
**Project type:** Student group project; the repository highlights its Python PCG-processing component.
