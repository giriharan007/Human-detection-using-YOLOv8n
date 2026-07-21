# 👤 Human Detection using YOLOv8n

A real-time computer vision application that detects **humans** from a live camera feed using the **Ultralytics YOLOv8 Nano (YOLOv8n)** model. The system performs efficient object detection, filters only the **person** class from the COCO dataset, draws bounding boxes around detected individuals, plays an audio alert, and automatically saves captured frames for future reference.

---

## 🚀 Features

- 🎥 Real-time human detection using a webcam
- 🤖 Powered by Ultralytics YOLOv8 Nano model
- 👤 Detects only the **Person (COCO Class 0)** category
- 📦 Draws bounding boxes around detected humans
- 🔊 Plays an audio alert when a person is detected
- 💾 Automatically saves captured images
- ⚡ Lightweight and optimized for real-time inference

---

## 🏗️ Project Workflow

```text
               Webcam Feed
                     │
                     ▼
             Capture Video Frame
                     │
                     ▼
          YOLOv8n Object Detection
                     │
                     ▼
          Filter Person Class (Class 0)
                     │
         ┌───────────┼───────────┐
         ▼           ▼           ▼
 Draw Bounding   Play Alert   Save Image
     Boxes         Sound      Automatically
         │
         ▼
     Display Output
```

---

## 🛠️ Technology Stack

| Component | Technology | Purpose |
|-----------|------------|---------|
| **Model** | Ultralytics YOLOv8n | Object detection engine |
| **Backend** | PyTorch | Deep learning framework |
| **Video Processing** | OpenCV (`cv2`) | Camera access, frame processing, visualization |
| **Audio** | Pygame Mixer | Alert sound playback |
| **Runtime** | Jupyter Notebook | Interactive execution environment |
| **Language** | Python 3.7+ | Application development |

---

## 📂 Project Structure

```text
Human-Detection-YOLOv8n/
│
├── human.ipynb          # Main notebook
├── yolov8n.pt           # Pre-trained YOLOv8 Nano model
├── alarm.mp3            # Audio alert
├── captured_images/     # Saved detection images
├── requirements.txt
└── README.md
```

---

## ⚙️ Prerequisites

Before running the project, ensure you have:

- Python **3.7 or later**
- A working webcam
- Internet connection (first-time model download if needed)

---

## 📦 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/<your-username>/Human-Detection-YOLOv8n.git
cd Human-Detection-YOLOv8n
```

### 2. Create a Virtual Environment (Optional)

**Windows**

```bash
python -m venv venv
venv\Scripts\activate
```

**Linux/macOS**

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies

```bash
pip install ultralytics
pip install opencv-python
pip install torch
pip install pygame
```

Or install everything from the requirements file:

```bash
pip install -r requirements.txt
```

---

## ▶️ How It Works

### Step 1 – Install YOLOv8 and Dependencies

Install all required Python libraries.

```bash
pip install ultralytics opencv-python torch pygame
```

---

### Step 2 – Load the Pre-trained YOLOv8 Model

Load the lightweight YOLOv8 Nano model.

```python
from ultralytics import YOLO

model = YOLO("yolov8n.pt")
```

---

### Step 3 – Detect Humans

The model processes each webcam frame and filters only the **Person** class (COCO Class ID `0`).

```python
results = model(frame)

for result in results:
    for box in result.boxes:
        if int(box.cls[0]) == 0:
            # Human detected
```

---

### Step 4 – Trigger Actions

When a human is detected, the application:

- Draws a bounding box
- Plays an audio alert
- Saves the detected frame
- Displays the annotated video feed

---

### Step 5 – Fine-tune the Model (Optional)

To improve performance for a custom environment:

- Collect and label your own dataset.
- Train or fine-tune YOLOv8 using Ultralytics.
- Replace the default `yolov8n.pt` model with your custom-trained weights.

For training:

```bash
yolo detect train data=data.yaml model=yolov8n.pt epochs=100 imgsz=640
```

---

## 🎯 Detection Pipeline

```text
Initialize Webcam
        │
        ▼
Capture Frame
        │
        ▼
YOLOv8n Inference
        │
        ▼
Filter Person Class
        │
        ▼
Human Detected?
      │       │
     No      Yes
      │       │
      ▼       ▼
 Continue   Draw Bounding Box
             │
             ▼
         Play Alert Sound
             │
             ▼
        Save Detection Image
             │
             ▼
       Display Output Frame
```

---

## 📸 Output

When a person is detected:

- ✅ Bounding box is drawn around the detected person.
- ✅ Confidence score is displayed.
- ✅ Alert sound is played.
- ✅ Detection image is saved locally.
- ✅ Live camera feed continues processing.

---

## 📋 Requirements

- Python 3.7+
- Ultralytics
- PyTorch
- OpenCV
- Pygame

Example:

```text
ultralytics
torch
opencv-python
pygame
```

---

## Further details:
https://app.devin.ai/org/giriharan007/wiki/giriharan007/Human-detection-using-YOLOv8n
