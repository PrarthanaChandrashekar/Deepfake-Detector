# 🎭 Deepfake Video Detection System

An AI-powered web application that analyzes uploaded videos and predicts whether they are **Real or Deepfake** using a VideoMAE-based deep learning model.

The application is built with Python and Streamlit, providing an interactive dashboard with video analysis results, confidence metrics, representative video frames, and visualizations.

## 🚀 Features

- **Video Upload:** Upload videos in MP4, AVI, MOV, MKV, and WEBM formats.
- **Video Frame Extraction:** Extracts 16 uniformly sampled frames from the uploaded video using OpenCV.
- **AI-Based Detection:** Uses a pretrained VideoMAE deepfake classification model.
- **Binary Classification:** Predicts whether the video is Real or Deepfake.
- **Confidence Metrics:** Displays Real and Deepfake class probabilities.
- **Analyzed Frames:** Displays representative frames used during video analysis.
- **Interactive Dashboard:** Presents results through a Streamlit interface.
- **Data Visualization:** Includes a confidence doughnut chart and prediction probability bar graph.
- **Video Information:** Displays resolution, FPS, duration, total frame count, and processing time.

> **Face Detection Note:** The current VideoMAE implementation extracts and analyzes video frames directly. It does not perform a separate face-detection step. OpenCV Haar Cascade face detection was used in an earlier version but is not part of the current pipeline.

## 🧠 Model and Technologies

| Technology | Purpose |
|---|---|
| Python | Main programming language |
| VideoMAE | Video-based deepfake classification |
| PyTorch | Deep learning model execution |
| Hugging Face Transformers | Loading the pretrained VideoMAE model and processor |
| OpenCV | Video reading, metadata extraction, and frame sampling |
| NumPy | Numerical operations |
| Pillow (PIL) | Image processing |
| Streamlit | Interactive web application |
| Plotly | Confidence charts and visualizations |

### Pretrained Model

**Model:** `Vansh180/VideoMae-ffc23-deepfake-detector`

The model is based on VideoMAE and fine-tuned for binary deepfake classification using the FaceForensics++ C23 dataset.

## ⚙️ How the System Works

1. The user uploads a video through the Streamlit application.
2. OpenCV reads the video and extracts its metadata.
3. The system samples 16 frames uniformly across the video.
4. The VideoMAE processor prepares the frames for model input.
5. The pretrained VideoMAE model analyzes the video frames.
6. The model generates classification outputs for Real and Deepfake.
7. Softmax converts the model outputs into class probabilities.
8. The application displays the prediction, confidence metrics, analyzed frames, and charts.

## 📊 Dashboard Output

The dashboard provides:

- Final prediction: REAL or DEEPFAKE
- Real and Deepfake probabilities
- Number of frames analyzed
- Model confidence
- Processing time
- Representative analyzed frames
- Confidence doughnut chart
- Prediction probability bar graph
- Video metadata
- Model information and analysis interpretation

## 📁 Project Structure

```text
deepfake-video-detector/
│
├── app.py
├── detector.py
├── requirements.txt
├── README.md
│
└── .streamlit/
    └── config.toml
```

## 💻 Installation and Setup

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
```

### 2. Navigate to the project directory

```bash
cd deepfake-video-detector
```

### 3. Create a virtual environment (recommended)

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the application

```bash
python -m streamlit run app.py
```

### 6. Open the application

Streamlit will provide a local URL, usually:

```text
http://localhost:8501
```

Upload a video and click **Analyze Video** to view the prediction and dashboard results.

## 📈 Understanding the Results

The system displays the predicted probabilities for both classes.

For example:

- Deepfake Probability: 53.55%
- Real Probability: 46.45%

In this example, the model predicts **DEEPFAKE** because the Deepfake class has the higher probability.

**Note:** These percentages represent the model's predicted probabilities for an individual video. They are not the overall accuracy of the model.

## ⚠️ Limitations

- Prediction quality may vary depending on video resolution, compression, lighting, and visual quality.
- The model may not generalize equally well to every deepfake generation technique.
- The current implementation uses a fixed 16-frame input.
- Model predictions should be treated as an assistive detection result, not definitive proof of authenticity.

## 🔮 Future Enhancements

- Integrate a dedicated face-detection module.
- Evaluate the model on additional real-world deepfake datasets.
- Improve detection performance across different video qualities and manipulation techniques.
- Add more explainability and detailed analysis features.
- Explore real-time video deepfake detection.

## 👩‍💻 Author

**Prarthana Chandrashekar**

Developed as an AI/ML project using Python, VideoMAE, PyTorch, OpenCV, and Streamlit.

---

⭐ If you find this project interesting, feel free to explore the repository and share your feedback!
