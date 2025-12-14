

# 🚀 vLLM Model Serving & Deployment

High-performance **LLM inference and serving** using **vLLM**, with practical examples for loading, serving, and testing large language models efficiently.

This repository focuses on **production-ready model serving**, not just experimentation.

---

## ✨ Features

* ⚡ **Fast inference** with vLLM (PagedAttention)
* 🧠 Supports **large open-source LLMs**
* 🔌 Easy integration with **OpenAI-compatible APIs**
* 🐳 Ready for **Docker / cloud deployment**
* 🧪 Includes notebook for **local testing & experimentation**

---

## 📂 Repository Structure

```
.
├── vllm_serving_models.ipynb   # Main notebook (model loading & serving)
├── README.md                  # Project documentation
└── requirements.txt           # Python dependencies (optional)
```

---

## 🧠 What the Notebook Does

The notebook demonstrates:

* Loading LLMs with **vLLM**
* Running an **inference server**
* Sending prompts and receiving completions
* Optimizing performance for:

  * throughput
  * latency
  * GPU memory usage

⚠️ **Note:**
GitHub cannot render notebooks with broken widget metadata.
If you see a rendering error, download the notebook and open it locally.

---

## 🛠️ Installation

### 1️⃣ Create a virtual environment (recommended)

```bash
python -m venv venv
source venv/bin/activate   # Linux / macOS
venv\Scripts\activate      # Windows
```

### 2️⃣ Install dependencies

```bash
pip install vllm torch transformers
```

> For GPU support, ensure CUDA is installed correctly.

---

## ▶️ Running vLLM Server

Example command:

```bash
python -m vllm.entrypoints.openai.api_server \
  --model meta-llama/Llama-2-7b-hf \
  --host 0.0.0.0 \
  --port 8000
```

The server will expose an **OpenAI-compatible API**.

---

## 🧪 Example API Request

```bash
curl http://localhost:8000/v1/completions \
  -H "Content-Type: application/json" \
  -d '{
    "model": "meta-llama/Llama-2-7b-hf",
    "prompt": "Explain vLLM in simple terms",
    "max_tokens": 100
  }'
```

---

## 📊 Performance Highlights

* 🚀 PagedAttention for efficient KV-cache usage
* 📉 Reduced GPU memory fragmentation
* 📈 Higher throughput than standard Hugging Face pipelines

---

## 🔒 Requirements

* Python 3.9+
* CUDA-enabled GPU (recommended)
* NVIDIA driver + CUDA toolkit

---

## 🧯 Troubleshooting

### GitHub Notebook Rendering Error

If you see:

```
Invalid Notebook: metadata.widgets missing state
```

✔️ The notebook is safe
✔️ Code is not broken
❌ GitHub preview is limited

**Fix:**
Download and open locally in Jupyter or use the cleaned notebook version.

---

## 📌 Best Practices

* Use **quantized models** for production
* Pin model versions for reproducibility
* Monitor GPU memory with `nvidia-smi`
* Use batching for high-throughput workloads

---

## 📄 License

MIT License — feel free to use, modify, and deploy.

---

## 🙌 Acknowledgements

* vLLM authors and contributors
* Open-source LLM community


