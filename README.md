# 🩺 Medical Image to Text Report Generation

This project builds a deep learning model to automatically generate medical textual descriptions from chest X-ray images, such as identifying diagnoses and modality. It follows an encoder-decoder architecture, combining a CNN-based image encoder with a Transformer-based text decoder.

## 🎯 Objective

Given a chest X-ray image, the model aims to generate a clinical-style textual report describing the condition shown in the image.

**Example Input**: A chest X-ray image  
**Example Output**: *Frontal chest X-ray showing cardiomegaly with pulmonary edema.*

---

## 📂 Project Structure

```bash
Final_X-ray-medical.ipynb       # Main notebook for training & inference
images/                         # Chest X-ray input images
captions.csv                    # Report captions per image
model/                          # Saved model checkpoints
utils.py                        # Image preprocessing and data utilities
```

---

## 🧠 Methodology

The notebook performs the following steps:

1. **Dataset Preparation**
   - Uses the [Indiana University Chest X-ray Collection (IU X-Ray)](https://openi.nlm.nih.gov/faq) dataset.
   - Includes X-ray image files and corresponding textual reports.

2. **Preprocessing**
   - Resize and normalize grayscale images.
   - Tokenize medical reports for training the decoder.

3. **Model Design**
   - Encoder: CNN (e.g., ResNet or CLIP-based feature extractor).
   - Decoder: Transformer or LSTM-based architecture for sequence generation.

4. **Training**
   - Uses cross-entropy loss between generated and reference reports.
   - Implements teacher forcing during training.

5. **Evaluation**
   - BLEU score for quality of generated captions.
   - Visual inspection of image + predicted report pairs.

---

## 📦 Dataset Access

The dataset is publicly available from the U.S. National Library of Medicine:  
🔗 https://openi.nlm.nih.gov/faq

Make sure to download:
- Chest X-ray images (PNG or JPEG)
- Associated captions or reports (CSV/XML)

---

## 🚀 How to Reproduce

1. Clone this repository and open the notebook:

```bash
git clone https://github.com/your-username/medical-xray-report-generator.git
cd medical-xray-report-generator
```

2. Upload the dataset to your Google Drive.

3. Run the notebook `Final_X-ray-medical.ipynb` in Google Colab.

4. Optional: Modify `model/` or `utils.py` to adjust architecture or tokenization rules.

---

## 🛠 Technologies Used

- Python, PyTorch
- CNN Encoder + Transformer Decoder
- Google Colab
- BLEU Score Evaluation
- Indiana University Chest X-ray Dataset

---

## ✨ Sample Result

![X-ray sample](images/sample-xray.png)

**Generated Report**: *Mild cardiomegaly. No evidence of active pulmonary disease.*

---

## 📬 Acknowledgments

- Dataset from [NIH Open-i](https://openi.nlm.nih.gov/)
- Inspired by recent medical captioning literature and encoder-decoder architectures.
