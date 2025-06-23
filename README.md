
# 🧠 AI Watermark Remover with Brush Tool

A powerful web-based image cleanup tool built on top of [lama-cleaner](https://github.com/Sanster/lama-cleaner), enhanced with:

- ✅ Input/output folder automation
- ✅ Brush-based UI (with inpainting model)
- ✅ "Next image" workflow
- ✅ Image saving to output folder

---

## 🧰 Features

- Drag & brush to remove watermarks or objects
- Use arrow buttons or "Next" to auto-load next image
- Saves cleaned images to your chosen output directory
- Runs locally with a clean UI (no need to upload to cloud)

---

## 🧪 Requirements

- OS: Linux/macOS (Windows works with WSL)
- Python 3.10+
- Git
- Chrome or modern browser

---

## 🧱 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/ItsChriszz/AiWaterMarkRemover.git
cd AiWaterMarkRemover
```

### 2. Set Up Virtual Environment

```bash
python3 -m venv lama-env
source lama-env/bin/activate
```

### 3. Install Dependencies

```bash
pip install --upgrade pip

# Core packages
pip install torch==2.7.1 torchvision==0.22.1
pip install Pillow==11.2.1 opencv-python==4.11.0.86

# AI models
pip install diffusers==0.16.1 transformers==4.27.4

# Web server & utilities
pip install flask flask-cors flask-socketio loguru
```

---

## 🚀 Usage

### Input/Output Folder Mode

```bash
source lama-env/bin/activate

python3 lama_cleaner/server.py \
  --input-dir /absolute/path/to/input \
  --output-dir /absolute/path/to/output \
  --port 8081
```

Then open your browser to:  
👉 http://127.0.0.1:8081

### Workflow

1. Use the brush tool to mask the area to remove
2. Click **Inpaint**
3. Click **Next** to save and load the next image from your input folder

---

## 📁 Project Structure

```
AiWaterMarkRemover/
├── lama_cleaner/          # Main backend code
│   └── server.py          # Modified server with folder support
├── app/                   # React UI frontend
├── lama-env/              # Your virtualenv (excluded from Git)
└── README.md
```

---

## 💡 Tips

- Use `--port 9090` if you have port conflicts
- Works offline (no internet required after model is downloaded)
- Supports drag-and-drop or browsing images in a folder
