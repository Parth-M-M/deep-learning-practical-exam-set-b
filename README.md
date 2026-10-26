# 🎓 Deep Learning Practical Exam — Set B (`deep-learning-practical-exam-set-b`)

Complete, reproducible submission for the **6-Hour Deep Learning Practical Exam (Set B)** covering Artificial Neural Networks (ANN), OpenCV Image Preprocessing, Convolutional Neural Networks (CNN), Recurrent Neural Networks (LSTM & SimpleRNN), and Hugging Face Transformers (Sentiment Analysis, WordPiece Tokenization & Named Entity Recognition).

---

## 📂 Repository Structure

```text
deep-learning-practical-exam-set-b/
├── DeepLearning_Practical_Exam_SetB.ipynb   # Single fully executed Jupyter Notebook (Steps 1–6)
├── ann_cancer_model.h5                      # Step 1 saved Keras ANN model (Breast Cancer Wisconsin)
├── cnn_fashion_model.h5                     # Step 3 saved Keras CNN model (Fashion-MNIST)
├── rnn_imdb_model.h5                        # Step 4 saved Keras LSTM model (IMDB Movie Reviews)
├── images/                                  # 5 raw input object images for Step 2 (OpenCV)
│   ├── coin.png
│   ├── apple.png
│   ├── leaf.png
│   ├── phone.png
│   └── book.png
├── outputs/                                 # All generated plots & OpenCV 5x5 preprocessed images
│   ├── step1_class_distribution.png
│   ├── step1_ann_accuracy.png
│   ├── step1_ann_loss.png
│   ├── step1_ann_confusion_matrix.png
│   ├── step2_raw_images.png
│   ├── step2_5x5_summary_grid.png
│   ├── step2_color_histogram.png
│   ├── step2_augmentation_comparison.png
│   ├── <object>_1_original.png ... <object>_5_contour.png
│   ├── step3_sample_images.png
│   ├── step3_cnn_accuracy.png
│   ├── step3_cnn_loss.png
│   ├── step3_cnn_confusion_matrix.png
│   ├── step3_test_predictions.png
│   ├── step4_review_lengths_hist.png
│   ├── step4_rnn_accuracy.png
│   ├── step4_rnn_loss.png
│   ├── step4_rnn_confusion_matrix.png
│   ├── step4_lstm_vs_simplernn.png
│   └── step5_sentiment_confidence.png
├── summary_report.md                        # ~450-word executive reflection & technical report
├── requirements.txt                         # Python package dependencies
└── README.md                                # Project documentation, setup guide & results summary
```

---

## 🔗 Datasets & Pre-Trained Models Used

1. **Step 1 (ANN):** [Breast Cancer Wisconsin (Diagnostic) Dataset](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data) — loaded via `sklearn.datasets.load_breast_cancer(as_frame=True)` (`569` rows, `30` features).
2. **Step 2 (OpenCV):** 5 custom high-contrast object images (`images/coin.png`, `images/apple.png`, `images/leaf.png`, `images/phone.png`, `images/book.png`), inspired by the [Natural Images Dataset on Kaggle](https://www.kaggle.com/datasets/prasunroy/natural-images).
3. **Step 3 (CNN):** [Fashion-MNIST Dataset](https://github.com/zalandoresearch/fashion-mnist) — loaded via `tensorflow.keras.datasets.fashion_mnist` (`20,000` train / `4,000` test subset, `28×28` grayscale, `10` classes).
4. **Step 4 (RNN — LSTM):** [IMDB Movie Reviews Dataset](https://ai.stanford.edu/~amaas/data/sentiment/) — loaded via `tensorflow.keras.datasets.imdb` (`10,000` train / `5,000` test subset, `num_words=10000`, `maxlen=100`).
5. **Step 5 (Transformers):**
   - Sentiment Pipeline: [`cardiffnlp/twitter-roberta-base-sentiment-latest`](https://huggingface.co/cardiffnlp/twitter-roberta-base-sentiment-latest)
   - WordPiece Tokenizer: [`distilbert-base-uncased`](https://huggingface.co/distilbert-base-uncased)
   - NER Pipeline: [`dslim/bert-base-NER`](https://huggingface.co/dslim/bert-base-NER)

---

## ⚙️ Installation & How to Run

### 1. Clone the Repository & Create a Virtual Environment
```bash
git clone https://github.com/<your-username>/deep-learning-practical-exam-set-b.git
cd deep-learning-practical-exam-set-b
python3 -m venv venv
source venv/bin/activate   # On Windows: venv\Scripts\activate
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Launch Jupyter Notebook
```bash
jupyter notebook DeepLearning_Practical_Exam_SetB.ipynb
```
*(Note: The notebook `DeepLearning_Practical_Exam_SetB.ipynb` is already pre-executed with all cell outputs, tables, and plots embedded.)*

---

## 📊 Results Summary Table

| Step / Topic | Task Type | Dataset Used | Key Metric | Result Achieved | Time Taken |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Step 1 — ANN** | Tabular Binary Classification | Breast Cancer Wisconsin (569 rows × 30 features) | Test Accuracy, Precision, Recall, F1 | **97.37% Accuracy** (Precision: 97.26%, Recall: 98.61%, F1: 97.93%) | ~35 mins |
| **Step 2 — OpenCV** | Image Preprocessing & Feature Extraction | 5 Object Images (Coin, Apple, Leaf, Phone, Book) | Otsu Threshold & Largest Contour Area | **5/5 Segmented** (Contour Areas: 7,840.0 – 14,254.0 px²) | ~40 mins |
| **Step 3 — CNN** | 10-Class Image Classification | Fashion-MNIST (20,000 train / 4,000 test, 28×28×1) | Test Accuracy & Macro F1 | **89.45% Test Accuracy** (Macro F1: 89.44%) | ~50 mins |
| **Step 4 — RNN (LSTM)** | Text Sequence Classification | IMDB Movie Reviews (10,000 train / 5,000 test, `maxlen=100`) | Test Accuracy & F1-Score | **83.24% Test Accuracy** (`SimpleRNN` Bonus: 76.18%) | ~55 mins |
| **Step 5 — Transformer** | Zero-Training Sentiment & NER Inference | 20 Custom Reviews (+3 Hinglish) & 5 NER Sentences | Accuracy on Clear Reviews & Entity Recall | **100.0% (16/16)** on Clear POS/NEG; **16/16 Named Entities** Extracted | ~40 mins |

---

## 🎥 Video Walkthrough (Component B — Face + Screen Recording)

* **Video File Naming Convention:** `Practical_Exam_YourName_GRID.mp4`
* **Video Link (Google Drive / Unlisted YouTube):** `https://drive.google.com/file/d/YOUR_VIDEO_FILE_ID/view?usp=sharing` *(Replace with your uploaded recording URL before final submission)*

---

## ✅ Submission Checklist

- [x] Notebook `DeepLearning_Practical_Exam_SetB.ipynb` runs top-to-bottom without errors
- [x] **Step 1 (ANN):** `model.summary()` printed (`1,537` params), accuracy/loss curves and confusion matrix shown, saved as `ann_cancer_model.h5`
- [x] **Step 2 (OpenCV):** 5×5 preprocessing grid displayed (`outputs/step2_5x5_summary_grid.png`), BGR histogram and horizontal flip / 45° rotation shown
- [x] **Step 3 (CNN):** Hand-calculated layer shapes verified (`28 → 26 → 13 → 11 → 5 → 1600`), training curves, confusion matrix, and 10 test predictions (wrong in red) shown, saved as `cnn_fashion_model.h5`
- [x] **Step 4 (RNN):** Review length histogram, `LSTM(32)` + `SimpleRNN(32)` bonus comparison, test accuracy (`83.24%`), and 5 decoded review predictions shown, saved as `rnn_imdb_model.h5`
- [x] **Step 5 (Transformer):** 20-review DataFrame + 3 Hinglish bonus reviews, WordPiece `##` analysis, `dslim/bert-base-NER` output, and horizontal confidence bar chart displayed
- [x] **Step 6:** Results summary table, 7-point written reflection, and `summary_report.md` complete
