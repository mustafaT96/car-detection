# 🚗 Car Detection Using Azure Custom Vision

This project demonstrates how to detect cars in images and video frames using **Microsoft Azure Custom Vision Object Detection**.  
The system loads frames from a video, sends them to the Azure Custom Vision prediction API, receives bounding boxes, and visualizes detected objects in real time.

---

## 📌 Project Overview

This project includes:

- Using Microsoft Azure Custom Vision for object detection  
- Running inference on single images  
- Running inference on video frames  
- Drawing bounding boxes using `PIL` and `OpenCV`  
- Displaying detection results in real time  

---

## 🧠 Technologies & Tools Used

- **Python 3.x**
- **Azure Custom Vision Prediction API**
- **MS REST APIKeyCredentials**
- **OpenCV**
- **NumPy**
- **Pillow (PIL)**
- **Matplotlib**

---

## 📦 Installation

Install all required Python packages:

```bash
pip install azure-cognitiveservices-vision-customvision
pip install msrest
pip install opencv-python
pip install numpy
pip install pillow
pip install matplotlib
```

---

## 🔧 Configuration

Before running the script, replace the placeholders with your Azure Custom Vision details:

```bash
prediction_endpoint = 'https://<your-endpoint>.cognitiveservices.azure.com/'
prediction_key = 'add_your_prediction_key'
project_id = '<your-project-id>'
model_name = '<your-model-name>'
```

---

## 🖼️ Detecting Cars in an Image

The script loads a single frame and sends it to Azure:

```bash
image_file = 'path/to/your/image.jpg'
image = Image.open(image_file)

with open(image_file, mode="rb") as image_data:
    results = prediction_client.detect_image(project_id, model_name, image_data)
```

Each detection includes:

- Tag name
- Bounding box
 -Confidence
  
Bounding boxes are drawn using **PIL.ImageDraw**.

---

## 🎥 Real-Time Detection on Video Frames

The script processes a video file frame-by-frame:

```bash
video_capture = cv2.VideoCapture('Highway Traffic.mp4')
```

The helper function sends each frame to the Azure API:

```bash
def detect_objects(frame):
    # Encodes frame → sends to API → draws boxes
```

Bounding boxes and labels are drawn using OpenCV:

```bash
cv2.rectangle(...)
cv2.putText(...)
```
---

👤 Author

Mustafa Tariq

Master of Applied Artificial Intelligence

Azure • Python • Computer Vision • ML Engineering
