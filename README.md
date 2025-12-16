# Industrial Pump Predictive Maintenance (Project 2 – 62FIT4ATI)

This repository contains our implementation of **Project 2: Industrial Pump Predictive Maintenance** for the course **62FIT4ATI**.  
We use an **LSTM-based neural network** to classify the machine status (`NORMAL`, `BROKEN`, `RECOVERING`) from multivariate time-series sensor data.

---

## 1. Environment Setup

### 1.1. Python & virtual environment (recommended)

```bash
# Create and activate venv (Linux / macOS)
python -m venv venv
source venv/bin/activate

# On Windows (PowerShell)
python -m venv venv
venv\Scripts\Activate.ps1
```

### 1.2. Install dependencies

```bash
pip install -r requirements.txt
```


## 2. Data Preparation

1. Obtain the dataset file: **`sensor.csv`** (from the course’s shared drive).
2. Place it project's root, example:

```text
project_root/
├── notebook.ipynb
├── sensor.csv
├── report.docx
└── trained_model.h5
```

## 3. Running the notebook (Local)

1. Start Jupyter:

```bash
jupyter notebook
```

2. Open **`notebook.ipynb`**.
3. Run all cells **in order** from top to bottom:
   - Data loading & exploratory analysis  
   - Preprocessing & sequence creation  
   - LSTM model definition  
   - Training (with class weights and callbacks)  
   - Evaluation (metrics + confusion matrix)  
   - Inference on new data  

4. At the end, the notebook will:
   - Print evaluation metrics on the test set  
   - Show training curves and confusion matrix  
   - Demonstrate inference on a sample sequence  
   - Save the trained model

---

## 4. Running the notebook (Google Colab)

1. Upload `notebook.ipynb` to Colab or open it directly from GitHub.
2. Upload `sensor.csv` to Colab or mount Google Drive.
3. Run all cells in sequence as in the local setup.
4. To save the trained model:
   - Download it from the Colab file browser, or  
   - Save it to your Google Drive from the notebook.

---

## 5. Reproducing Results

To approximately reproduce our results:

1. Keep the same:
   - `WINDOW_SIZE` (sequence length)  
   - Train/validation/test split strategy  
   - Batch size, number of epochs, optimizer (Adam)  
   - Class-weight computation  
   - Callbacks: **EarlyStopping** and **ReduceLROnPlateau**  

2. Run the notebook end-to-end without changing randomization logic.

You should obtain similar:

- Accuracy  
- Balanced accuracy  
- Macro F1-score  
- Confusion matrix structure (especially class-wise behavior)

---

## 6. Files Overview

- `notebook.ipynb` – main notebook (full workflow)  
- `sensor.csv` – dataset (not included in repo; provided via course's drive)  
- `trained_model.h5` – saved trained models  

---

## 7. Authors

- Group #: **[Your Group Number]**  
- Members:
  - **Tran Duc Anh - 2201140007**  
  - **Nguyen Quoc Hoang An - 2201140011**  
  - **Pham Khanh Son - 2201140076**  
