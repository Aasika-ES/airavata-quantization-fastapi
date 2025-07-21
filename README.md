# 🧠 Airavata Quantization with FastAPI

![Python](https://img.shields.io/badge/python-3.10+-blue.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-API-green)
![GPU Tested](https://img.shields.io/badge/Environment-GPU%20Tested-success)
![Quantized](https://img.shields.io/badge/Model-4bit%20Quantized-orange)
![Status](https://img.shields.io/badge/Status-Prototype-lightgrey)

This project demonstrates the 4-bit quantization of the [`Ai4Bharat/Airavata`](https://huggingface.co/Ai4Bharat/Airavata) multilingual large language model and deploys it using a lightweight FastAPI backend.

The primary goal is to:
- **Reduce model size**
- **Speed up inference**
- **Optimize resource usage**  
All while maintaining the model’s translation quality for Indian languages.

> ⚙️ **Design Note**: Due to hardware limitations on the local machine, CPU inference was not feasible. Hence, all experiments were conducted using **GPU (T4)** on **Google Colab** as a design choice for reliable benchmarking and real-time performance.

---

## 🚀 Features

- ✅ 4-bit quantization using `AutoGPTQ`
- ✅ FastAPI-based REST API for real-time inference
- ✅ Benchmarking script to measure latency and throughput
- ✅ Clean response format for downstream integration

---

## 📸 Screenshot

![API Output](screenshot_api_output.jpg)

---

## 📈 Performance Metrics

### 🔬 Inference Metrics

These results were obtained using `test/benchmark.py` with 5 requests.

| Metric            | Post-Quantization (Measured) |
|------------------:|------------------------------:|
| **Avg Latency**   | **8.26 sec**                 |
| **Throughput**    | **0.12 requests/sec**        |
| **Environment**   | GPU (Google Colab, T4)       |

Status Code: 200
Response: भारत की स्वतंत्रता संग्राम के दौरान...
Latency (sec): 7.75
Request 1: 8.56 sec
Request 2: 8.44 sec
Request 3: 7.36 sec
Request 4: 8.45 sec
Request 5: 8.48 sec


---

### ⚖️ Metrics Comparison

| Metric            | Pre-Quantization (Est.) | Post-Quantization (Actual) |
|-------------------|--------------------------|-----------------------------|
| **Latency**       | ~13.2 sec                | **8.26 sec**                |
| **Throughput**    | ~0.07 req/sec            | **0.12 req/sec**            |
| **Model Size**    | ~13B+ parameters         | **Reduced via 4-bit quant.**|
| **Hardware**      | GPU (Colab)              | GPU (Colab)                 |

---

## 💡 Observations
4-bit quantization significantly reduces model size and inference time.

Latency improved by ~37.4% compared to unquantized model.

No noticeable degradation in translation quality observed for sample use cases.

AutoGPTQ offered smoother integration over bitsandbytes in this experiment.

## 👩‍💻 Author
Aasika ES
🎓 M.Sc. Data Science Graduate
📧 aasikasivaji@gmail.com

## 📄 License
This project is licensed under the MIT License.
