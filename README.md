Heart Sound Analysis — Phonocardiography (PCG) Signal Processing
Course project for Laboratory of Internet of Medical Things (IoMT), Politecnico di Milano (2025/26). This repository contains the Python signal-processing component of a group project investigating a digital phonocardiography (PCG) prototype.
Overview
The pipeline processes WAV heart-sound recordings to explore cardiac acoustic signal structure and derive research-oriented, non-diagnostic descriptors.
Signal-processing workflow
1. Load and inspect a PCG waveform.
2. Preprocess and denoise the signal using a 25–200 Hz Butterworth band-pass, 50/100/150 Hz notch filters, and wavelet denoising.
3. Extract a Shannon-energy envelope and identify candidate S1/S2 heart sounds.
4. Segment cardiac cycles and compute timing, amplitude, spectral and morphology features.
5. Estimate heart rate and short-window variability descriptors; explore rule-based signal-quality and murmur-like acoustic activity indicators.
6. Visualize signals, spectrograms and analysis outputs.
Methods are implemented in PCG_Analysis.ipynb; pcg_analysis.py is a script exported from the notebook.
Files
- PCG_Analysis.ipynb — exploratory PCG analysis notebook
- pcg_analysis.py — corresponding Python analysis script
- requirements.txt — Python package dependencies
The wider group project also documented an Arduino Nano ESP32 / SEN-14262 sensing architecture, an OLED display, a PCB designed in Altium, BLE communication and a software interface. The firmware, Altium PCB source files and application source code are not included in this repository, so the repository should not be interpreted as a fully reproducible end-to-end medical device.
Running the analysis
1. Install Python 3.10+ and the dependencies: pip install -r requirements.txt.
2. Place an appropriately licensed or consented PCG WAV recording in the repository directory named Test Data.wav. The original sample recording is deliberately omitted from this shareable package pending confirmation of permission to publish it.
3. Run jupyter lab and execute the notebook from top to bottom, or run python pcg_analysis.py in an environment capable of displaying plots.
The notebook contains saved exploratory visual outputs from prior execution; they are not evidence of clinical validation, and the full workflow has not been independently rerun in preparing this repository package. Some notebook cells may require interactive execution or environment-specific adjustments.
Example results reported in the course report
For one approximately 24.92 s, 500 Hz PCG recording, the report describes 29 S1/S2 pairs, 29 extracted cardiac cycles, and an estimated heart rate of 73.4 bpm. These are single-recording signal-processing results and do not establish diagnostic performance or generalization.
Limitations and responsible use
Educational and research prototype only. Not a medical device and not suitable for clinical diagnosis or patient decisions. Heart-sound segmentation, short-recording HRV-like measures, and murmur-like indicators are exploratory; external validation against expert annotations and larger datasets is required. Avoid committing identifiable health recordings or personal information without explicit rights and consent.
Academic context
Laboratory of Internet of Medical Things, Politecnico di Milano, academic year 2025/26. Developed as part of a student group project; see the full team report for authorship and individual contributions. Avoid representing all group hardware and software work as an individual implementation without documentation.
