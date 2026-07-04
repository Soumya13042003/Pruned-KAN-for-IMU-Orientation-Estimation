# Pruned-KAN for IMU Orientation Estimation

This project focuses on IMU-based orientation estimation using a **Pruned-KAN (Kolmogorov-Arnold Network)** model. The model predicts **Roll, Pitch, and Yaw** angles from quaternion-based IMU sensor data and compares its performance with traditional filtering methods such as the **Madgwick Filter** and **Complementary Filter**.

---

## Overview

Orientation estimation plays an important role in robotics, motion tracking, AR/VR, and navigation systems. This project proposes a deep learning-based approach using Pruned-KAN to improve orientation prediction accuracy from IMU sensor data.

The proposed model is trained using Room_1 dataset and tested on Room_2 and Room_3 datasets.

---

## Dataset

- **Training Dataset:** Room_1  
- **Testing Dataset:** Room_2, Room_3  

The datasets contain IMU sensor readings and quaternion-based orientation information.

---

## Features

- IMU sensor data preprocessing  
- Linear interpolation for missing values  
- Quaternion-based orientation prediction  
- Roll, Pitch, and Yaw estimation  
- Comparison with Madgwick and Complementary filters  
- Quaternion error analysis  

---

## Tech Stack

- Python  
- Google Colab  
- NumPy  
- Pandas  
- Matplotlib  
- Scikit-learn  
- TensorFlow / PyTorch  

---

## How It Works

1. Load IMU sensor datasets from Room_1, Room_2, and Room_3.
2. Preprocess the data using linear interpolation.
3. Use previous quaternion outputs as input features.
4. Train the Pruned-KAN model using Room_1 dataset.
5. Predict orientation angles (Roll, Pitch, Yaw).
6. Test model performance on Room_2 and Room_3 datasets.
7. Compare results with Madgwick Filter and Complementary Filter.
8. Analyze quaternion prediction error.

---

## Results

### Room 2 Performance
- Pruned-KAN closely follows Ground Truth across Roll, Pitch, and Yaw.
- Madgwick Filter shows noticeable deviation, especially in Yaw estimation.
- KAN achieves lower overall prediction error.

### Room 3 Performance
- Pruned-KAN maintains good tracking performance.
- Madgwick Filter shows increasing drift over time.
- Quaternion error analysis indicates better overall stability of KAN.

---

## Output Visualization

- Roll Comparison Plot  
- Pitch Comparison Plot  
- Yaw Comparison Plot  
- Quaternion Error Plot  

---

## Project Structure

```bash
├── dataset/
│   ├── room_1
│   ├── room_2
│   └── room_3
├── notebooks/
│   └── KAN_NEW.ipynb
├── results/
├── figures/
└── README.md
```

---

## installation
```bash
!pip install --upgrade pip
!pip uninstall -y sympy 
``` 
# Uninstall any sympy version
# Reinstall sympy to a version compatible with torch, or let pip decide the latest compatible version
# (Often, not specifying sympy version will lead to a torch-compatible one)
```bash
!pip install sympy
```
# Uncommented to explicitly reinstall sympy, allowing pip to resolve version
```bash
!pip install git+https://github.com/KindXiaoming/pykan.git
!pip install ahrs
!pip install scipy
```
# Verification steps
```bash
print('\n--- Verifying pykan/kan installation ---')
!pip show pykan
try:
    import kan
    print('Successfully imported kan module.')
except ImportError:
    print('Failed to import kan module. Please check installation logs.')
```
## License

This project is intended for academic and research purposes only.

---

## Authors

- Soumyadip Paul  
- Arnab Sinha (Supervisor)