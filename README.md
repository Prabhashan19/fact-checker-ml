# fact-checker-ml

# 🧠 Political Fact-Checking with T5-small

This project demonstrates a fine-tuned [T5-small](https://huggingface.co/t5-small) model to classify political statements as **"true"** or **"false"** using the [PolitiFact Fact Check Dataset](https://www.kaggle.com/datasets/rmisra/politifact-fact-check-dataset/data). The goal is to develop an automated fact-checking system to combat the spread of misinformation.

---

## 🚀 Project Overview

Misinformation in politics can lead to widespread confusion and poor decision-making. This project tackles that issue by:
- Framing fact-checking as a **text-to-text classification** task
- Fine-tuning T5-small using Hugging Face's `Trainer` API
- Evaluating the model's ability to correctly identify factual vs false claims

---

## 📁 Files Included

- `Fact_Check_T5.ipynb` – Google Colab notebook used for model fine-tuning and evaluation
- `dataset/` – Folder containing the processed dataset
- `requirements.txt` – Python dependencies
- `README.md` – This documentation

---

## ⚙️ Technologies & Libraries

- Python (3.x)
- [Transformers](https://huggingface.co/transformers/) by Hugging Face
- [Datasets](https://huggingface.co/docs/datasets)
- Scikit-learn
- Google Colab (GPU acceleration)

---

## 🧪 Techniques Used

- Preprocessed data by removing duplicates, handling nulls, and balancing labels
- Tokenized inputs using `T5Tokenizer` with padding/truncation
- Fine-tuned using Hugging Face’s `Trainer` API with custom training arguments
- Applied class weighting to manage imbalance
- Evaluated with accuracy, precision, recall, and F1-score

---

## 📊 Results

- Trained on ~17,000 entries after cleaning and preprocessing
- Achieved around **67% accuracy**
- Resolved label decoding issues by constraining outputs to "true"/"false" tokens

---

## 🔍 Challenges Faced

- **Class Imbalance**: Resolved by applying class weights instead of discarding data
- **Unexpected Outputs**: Handled by constraining decoded predictions
- **Colab Limitations**: Used batch training and checkpoint saving to avoid timeouts

---

## 📌 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
   
2. Open the notebook in Google Colab or your preferred environment.
  
3. Install dependencies:
   
   ```bash
   !pip install transformers datasets scikit-learn --quiet

4. Run all cells in Fact_Check_T5.ipynb to train and evaluate the model.

📚 Dataset

- Source: PolitiFact Dataset on Kaggle
- Contains labeled political statements with associated metadata (speaker, date, source, etc.)

🤝 Acknowledgements

- Hugging Face
- Kaggle Dataset by Rohit Misra
