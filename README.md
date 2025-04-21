
# Colorizing Historical Bangla Documentaries with Deep Learning

This project implements a deep learning-based approach to colorize historical black-and-white Bangladeshi documentary videos. Using convolutional neural networks (CNNs) and pre-trained feature extractors, the model predicts realistic colorizations for grayscale frames, bringing historical visuals to life.

---

## Model Overview

The model follows an **autoencoder-style architecture**:
- **Encoder**: Extracts low-level spatial features using stacked Conv2D layers.
- **Fusion Layer**: Combines encoder features with high-level semantic features from a pre-trained **InceptionResNetV2** model.
- **Decoder**: Reconstructs the color channels (`ab`) from grayscale (`L`) input using upsampling layers.

> The model was trained on screenshots taken from color documentary footage and tested on grayscale frames derived from black-and-white Bangladeshi historical videos.

---

## Repository Structure

```
historical-colorization/
├── model/              # TensorFlow.js compatible model (model.json + shards)
├── notebooks/          # Jupyter notebooks for preprocessing, training, and testing
├── requirements.txt    # Python dependencies
└── README.md           # This file
```

---

## Getting Started

### 1. Clone the Repository
```bash
git clone git@github.com:Marjan18101013/historical-colorization.git
cd historical-colorization
```

### 2. Install Dependencies
Make sure you have Python 3.6+ installed. Then run:
```bash
pip install -r requirements.txt
```

### 3. Open Notebooks
The notebooks are located in the `notebooks/` folder:
- `Preprocessing.ipynb` – convert video frames to training data
- `Train.ipynb`, `Train2.ipynb` – model training
- `Test.ipynb` – evaluate model predictions
- `Model.ipynb` – overall architecture definition

You can run them using Google Colab or JupyterLab.

---

## Model Files

The model is stored in TensorFlow.js format in the `model/` folder, including:
- `model.json` – architecture and weight manifest
- `group1-shard*.bin` – split binary weight data

> You can use TensorFlow.js to deploy this model in a browser. Or convert it back to Keras using `tensorflowjs_converter`.

---

## Dataset

- Training images were extracted from **color historical videos**
- Input grayscale (`L` channel) and predicted color (`ab` channels) use **Lab color space**
- Images were resized to **256x256** for model compatibility

---

## Results

Colorized outputs show strong visual realism, particularly on portraits, objects, and natural scenes. Some limitations remain due to dataset size and variation.

---

## Acknowledgements

This project was developed as part of our Bachelor of Science in CSE thesis at the **University of Asia Pacific**, titled:

**"Colorizing the Historical Bangla Documentary: A Deep Learning Based Approach"**  
Supervised by: *Hasan Murad, Lecturer, CUET*

**Authors:**
- Marjan Binte Halim Ashfi (ID: 18101013)  
- Yasir Iqbal Mredul (ID: 18101027)  
- Effat Jahan Manna (ID: 18101035)

---

## Future Work

- Improve accuracy with a larger, more diverse training set
- Add temporal consistency for smoother video colorization
- Build a browser app using TensorFlow.js to allow public use

---

## 📜 License

This project is part of academic research and is open for educational use. For commercial licensing or collaboration, please contact the authors.

```
