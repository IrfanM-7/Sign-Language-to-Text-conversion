# Sign Language to Text Conversion 🤟🔤

**Collaborative Project** by [Irfan](https://github.com/IrfanM-7),  [Sameera](https://github.com/sameera0602) &  [Shri Sudarsana](https://github.com/shrisudarsana)

A real-time sign language recognition system built using **MediaPipe**, **OpenCV**, and **scikit-learn**. This project captures hand landmarks from video input, extracts spatial features, and uses a Random Forest classifier to translate American Sign Language (ASL) gestures into text.

---

> [!NOTE]
> **Research Publication**  
> Our research paper **"Real-Time Sign Language to Text Conversion Using Mediapipe Hand Landmarks and Random Forest Classifier"** has been published in the *2026 6th International Conference on Trends in Material Science and Inventive Materials (ICTMIM)*.  
> 🔗 **[Read the paper on IEEE Xplore](https://ieeexplore.ieee.org/document/11507737)**

---

## 🌟 Key Features
- **Real-Time Hand Tracking**: Leverages Google's MediaPipe for highly accurate, low-latency hand landmark detection.
- **Robust Classification**: Uses a Random Forest Classifier to distinguish between complex sign language gestures based on extracted coordinate geometry.
- **Ready-to-Use Models**: Pre-trained model and label encoders included to get up and running instantly.
- **Research Notebook Included**: `Model_Training.ipynb` provides transparency on feature extraction, model selection, and training methodology.

---

## 🛠️ Architecture

1.  **Data Extraction Pipeline**: Parses raw image datasets, applying MediaPipe to isolate `x,y,z` landmark coordinates.
2.  **Feature Engineering**: Flattens structural hand data into 1D arrays for traditional Machine Learning processing.
3.  **Model Training**: Utilizes `RandomForestClassifier` with hyperparameter tuning to ensure robust generalization against varying lighting conditions and hand sizes.
4.  **Real-Time Inference**: Connects to the webcam stream to apply the trained classifier pipeline dynamically frame-by-frame.

---

## 🚀 Getting Started

### Prerequisites
Make sure you have Python 3.8+ installed.

### Installation

1.  **Clone the Repository**
    ```bash
    git clone https://github.com/IrfanM-7/Sign-Language-to-Text-conversion.git
    cd Sign-Language-to-Text-conversion
    ```

2.  **Create a Virtual Environment (Optional but Recommended)**
    ```bash
    python -m venv venv
    # On Windows:
    venv\Scripts\activate
    # On macOS/Linux:
    source venv/bin/activate
    ```

3.  **Install Dependencies**
    ```bash
    pip install -r requirements.txt
    ```

### Running the Application

To use the pre-trained model for real-time sign detection:
1. Ensure your webcam is connected.
2. The core logic for inference is detailed in the `Model_Training.ipynb`. (A dedicated inference script can be built using the saved `.pkl` files in the `models/` directory).

---

## 📂 Project Structure

```text
📦 Sign-Language-to-Text-conversion
 ┣ 📂 models/                 # Serialized models and encoders
 ┃ ┣ 📜 label_encoder.pkl     # Encoded ASL class mappings
 ┃ ┗ 📜 sign_language_model.pkl # Trained Random Forest model
 ┣ 📂 processed_combine_asl_dataset/ # (Ignored by Git) Dataset images
 ┣ 📜 Model_Training.ipynb    # Training & Feature Extraction Notebook
 ┣ 📜 README.md               # Project documentation
 ┣ 📜 requirements.txt        # Python dependencies
 ┗ 📜 .gitignore              # Ignored files configuration
```

---

## 🧠 Model Training details
The model was trained on a custom ASL dataset using the following features:
*   Extracting 21 3D landmarks for a single hand using MediaPipe.
*   The raw coordinates are normalized and fed into an SKLearn Random Forest.
*   Training metrics and grid-search cross-validation approaches can be reviewed in the provided Jupyter notebook.

## 📄 Citation

If you use this work or find our research helpful, please cite our paper:

### IEEE Format
```text
Shri Sudarsana H., Sameera M., Syed Irfan M. and Thurai Pandian M., "Real-Time Sign Language to Text Conversion Using Mediapipe Hand Landmarks and Random Forest Classifier," 2026 6th International Conference on Trends in Material Science and Inventive Materials (ICTMIM), Kanyakumari, India, 2026, pp. 1507-1512, doi: 10.1109/ICTMIM68190.2026.11507737.
```

### BibTeX
```bibtex
@INPROCEEDINGS{11507737,
  author={Shri Sudarsana H. and Sameera M. and Syed Irfan M. and Thurai Pandian M.},
  booktitle={2026 6th International Conference on Trends in Material Science and Inventive Materials (ICTMIM)}, 
  title={Real-Time Sign Language to Text Conversion Using Mediapipe Hand Landmarks and Random Forest Classifier}, 
  year={2026},
  volume={},
  number={},
  pages={1507-1512},
  keywords={Hands;Sign language;Modeling;Timing;Real-time systems;Random forests;Machine learning;Accuracy;Computers;Printing},
  doi={10.1109/ICTMIM68190.2026.11507737}}
```

---

## 🤝 Contributing
Contributions are welcome! If you want to add support for more gestures, improve the UI, or port the model to a Deep Learning architecture (like an LSTM or Transformer), feel free to open a Pull Request.
