# Multimodel_Emotional_Analysis.ipyn
 Overview
This project performs emotion classification from speech using the RAVDESS dataset. It processes .wav audio files, extracts MFCC features, and trains a Support Vector Machine (SVM) classifier to predict emotions.

📂 Dataset: RAVDESS
Name: Ryerson Audio-Visual Database of Emotional Speech and Song

Format: .wav

Classes: 8 emotions – Neutral, Calm, Happy, Sad, Angry, Fearful, Disgust, Surprised

Source: Zenodo - RAVDESS

⚙️ Workflow
Download Dataset

The dataset is downloaded directly in the notebook using:

bash
Copy
Edit
wget -O ravdess.zip ...
unzip ravdess.zip -d /content/ravdess/
Explore Audio

Files are played using IPython widgets to verify and explore the recordings.

Feature Extraction

MFCCs (Mel-Frequency Cepstral Coefficients) are extracted using librosa.

Each audio clip is represented by the mean of its MFCCs.

Label Parsing

Emotion labels are derived from the file name’s third segment (e.g., 03-01-06... → label 6).

Model Training

Uses SVC (Support Vector Classifier) with RBF kernel.

Trains and tests on the extracted features.

Evaluation

Prints accuracy and a classification report.

Supports prediction on new audio samples.

📊 Sample Output
plaintext
Copy
Edit
🎯 Model Accuracy: 0.88

📊 Classification Report:
              precision    recall  f1-score   support
     Neutral       0.90      0.90      0.90        20
     Happy         0.85      0.90      0.87        20
     ...
🧪 Predict Emotion from New File
python
Copy
Edit
file_path = "/content/ravdess/Actor_03/03-01-06-01-02-01-03.wav"
predicted_emotion = predict_emotion(file_path)
print(f"🎭 Predicted Emotion: {predicted_emotion}")
🧰 Requirements
Install required packages:

bash
Copy
Edit
pip install librosa numpy pandas scikit-learn matplotlib
🔍 Potential Improvements
Add visual and text modalities for true multimodal analysis.

Use deep learning (CNN, LSTM, transformers).

Visualize MFCC spectrograms for data insight.
