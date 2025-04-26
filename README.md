# Apnea_Detection
Apnea Detection from Simulated ECG

Introduction

Sleep apnea is a condition where breathing pauses during sleep, often leading to health complications. Electrocardiography (ECG) signals, which measure heart electrical activity, can help detect apnea through changes in heart rate patterns. This project simulates ECG signals over a 4-hour duration and uses signal processing techniques to detect apnea episodes.

The ECG signal is synthetically generated using sine waves and random noise to mimic heart activity. Apnea periods are simulated by reducing signal strength and introducing random missing beats, reflecting the physiological disturbances seen during apnea.

The detection method analyzes the dominant frequency in 60-second ECG segments. Apnea is predicted when the dominant frequency drops below 1.0 Hz, indicating slower or irregular heart activity typical of apnea.

Key Outputs:
Average heart rate plot
Power spectrum analysis
Spectrogram of frequency over time
Detected vs. actual apnea events plot
Detection accuracy percentage

Main Steps
Generate Simulated ECG: 
- A base ECG signal is created using two sine components (1.2 Hz and 2 Hz) and noise to simulate a normal heart rate of ~72 BPM.
- During apnea, the signal is weakened, and beats are randomly removed to mimic irregular heart activity.

Preprocessing:
- The signal is resampled from 100 Hz to 500 Hz to align with standard ECG analysis practices.
- A low-pass Butterworth filter (30 Hz cutoff) is applied to remove high-frequency noise.

Feature Extraction:
- R-peaks are detected to compute RR intervals and heart rate for each 60-second window.
- Heart rate variability (HRV) metrics are calculated but not used in this simple detection method.

Apnea Detection:
- The Fast Fourier Transform (FFT) is applied to each 60-second window.
- Apnea is detected if the dominant frequency is less than 1.0 Hz, based on the simulation’s design (normal: 1.2 Hz, apnea: 0.8 Hz).

Evaluation:
- Predicted apnea labels are compared to true labels from the simulation.
- Detection accuracy is calculated and visualized alongside other results.



Technologies Used
Python 3
NumPy
Pandas
SciPy
Matplotlib



Important Notes
- The ECG signals and apnea events are fully simulated and do not represent real patient data.
- Detection accuracy is high because the method is tailored to the simulation’s clear frequency distinction. Real-world scenarios would require more advanced features (e.g., HRV metrics) and machine learning techniques.
- Future Work: Consider adding heart rate variability features, testing with real ECG data, or exploring machine learning models for detection.

