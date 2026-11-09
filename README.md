# 🌍 U-Net-Based Oil Spill Detection and Segmentation

**Deep Learning | Remote Sensing | Sentinel-2 | Edge AI**

## 📌 Project Overview

This project focuses on detecting and segmenting marine oil spills from satellite imagery using a custom U-Net deep learning architecture.

The objective is to support maritime environmental monitoring through AI-based satellite image analysis and efficient model deployment on edge computing devices.

## 🎯 Objectives

- Detect and segment oil spills in satellite images.
- Develop and train a custom U-Net architecture.
- Evaluate different model precision formats.
- Optimize inference for embedded AI platforms.
- Explore Edge AI deployment using Raspberry Pi 5 and Hailo-8.

## 🛰️ Dataset

**MADOS – Marine Debris and Oil Spill Dataset**

- Satellite imagery from Sentinel-2.
- Multispectral image analysis.
- Semantic segmentation.
- 16 segmentation classes.

The dataset is not included in this repository.

## 🧠 Deep Learning Model

A custom U-Net architecture was developed for semantic segmentation.

Available model artifacts:

| File | Description |
|---|---|
| `mados_model.h5` | Trained Keras model |
| `mados_unet_fp32.tflite` | FP32 TensorFlow Lite model |
| `mados_unet_int8.tflite` | INT8 quantized model |
| `mados_scaler.pkl` | Data normalization scaler |

## ⚙️ Technologies

- Python
- TensorFlow / Keras
- TensorFlow Lite
- U-Net
- NumPy
- Computer Vision
- Edge AI
- Raspberry Pi 5
- Hailo AI Accelerator

## 📊 Results and Demonstration

The repository includes visual comparisons and a video demonstration.

- `avant_entrainement.png`
- `apres_entrainement.png`
- `mados_comparison.mp4`

## 🚀 Edge AI Deployment

The project explores deploying optimized segmentation models on embedded platforms, including Raspberry Pi 5 with Hailo acceleration.

The goal is to achieve efficient inference with reduced latency and computational requirements.

## 📁 Repository Structure

```text
U-Net-Oil-Spill-Segmentation/
│
├── apres_entrainement.png
├── avant_entrainement.png
├── img1.jpeg
├── img2.jpeg
├── img3 (2).jpeg
├── img4.jpeg
├── mados_comparison.mp4
├── mados_model.h5
├── mados_scaler.pkl
├── mados_unet_fp32.tflite
├── mados_unet_int8.tflite
├── .gitattributes
└── .gitignore
```

## 👩‍💻 Author

**Eya Mtiraoui**

Computer Science Engineer – IoT & Robotics  
AI | Embedded Systems | Edge AI | Computer Vision

- GitHub: https://github.com/EYAMTIRAOUI
- LinkedIn: https://www.linkedin.com/in/mtiraoui-eya-1628b3220/

---

## ⚡ Performance Evaluation: FPS, Inference Time & Latency

An important part of this project is evaluating the computational performance of the U-Net segmentation model on different inference configurations.

The objective is to compare model precision formats and hardware acceleration to identify the most efficient solution for real-time Edge AI applications.

### Performance Metrics

- **FPS (Frames Per Second):** Number of images processed per second.
- **Inference Time:** Time required by the model to generate a prediction for one image.
- **Latency:** End-to-end delay between image acquisition and availability of the segmentation result.

### Experimental Results

| Configuration | Threads | Throughput (FPS) | Inference Time (ms) |
|---|---:|---:|---:|
| FP32 | 1 | 2.22 | 450.0 |
| FP32 | 4 | 4.21 | 237.8 |
| FP16 | 1 | 3.51 | 285.1 |
| FP16 | 4 | 7.01 | 142.6 |
| INT8 | 1 | 4.64 | 215.4 |
| INT8 | 4 | 10.93 | 91.5 |
| Hailo Accelerator | — | 63.64 | 10.12 |

### Key Findings

- FP16 and INT8 quantization improve inference efficiency compared with FP32 in the tested configurations.
- Multi-threading improves CPU inference throughput.
- Hailo hardware acceleration achieves 63.64 FPS with a measured inference time of 10.12 ms.
- Hardware acceleration makes the segmentation pipeline more suitable for real-time maritime monitoring applications.

### Edge AI Optimization

The deployment process explores optimized inference on Raspberry Pi 5 with Hailo AI acceleration.

The main objective is to reduce inference latency, increase throughput, and maintain an efficient computational footprint for embedded AI applications.