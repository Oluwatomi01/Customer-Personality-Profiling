# Customer-Personality-Profiling

**Call Center Audio Processing & Personality Profiling Workflow**

## **📌 Overview**

This project processes **financial call center conversations** to:

1. **Transcribe** customer-agent conversations from dual-channel audio(i.e agent and customer)
2. **Extract features** from both **audio** (pitch, energy, speaking rate) and **text** (sentiment, n-grams).
3. **Predict the customer’s personality category** into one of **5 profiles**:

   * Cooperative
   * Short-tempered
   * Reserved
   * Neutral
   * Friendly
     
4. **Generate practical agent engagement suggestions** based on predicted temperament.

The pipeline transforms raw audio into helpful insights for **improved customer experience and agent performance**.


## **The Goals**

* Build an **end-to-end pipeline** for:
  ✅ **ASR (Automatic Speech Recognition)**
  ✅ **Feature Engineering** (Audio + Text)
  ✅ **Personality Classification**
  ✅ **Agent Tip Generation**
  
* Output **structured JSON reports** containing:

  ```json
  {
    "call_id": "12345",
    "transcript": "...",
    "personality_label": "Cooperative",
    "suggestions": ["Maintain calm tone", "Provide detailed steps"]
  }
  ```

## **📂 Project Structure**

```
├── data/                # Audio files & metadata
├── notebooks/           # Jupyter notebooks for EDA, modeling
├── src/                 # Core pipeline scripts
│   ├── asr.py           # Whisper-based transcription
├── models/              # Trained models
├── requirements.txt
└── README.md
```

## **Pipeline Workflow**

### **1. Data Ingestion**

* Input: **Dual-channel call audio (Agent & Customer)**
* Files normalized to **16kHz mono**

### **2. Automatic Speech Recognition (ASR)**

* **Whisper** model for transcription
* Output: Clean text for each call

### **3. Feature Extraction**

* **Audio-based**: Pitch, energy, speaking rate using `librosa`
* **Text-based**: Sentiment scores, n-grams using `scikit-learn`

### **4. Personality Classification**

* Machine Learning models: **Logistic Regression**, **Random Forest**, **XGBoost**
* Target: 5 personality classes

### **5. Suggestion Engine**

* Maps predicted personality to **engagement strategies** for agents



## **My Tools & Libraries**

* **Audio Processing:** `librosa`, `pydub`
* **ASR:** `openai-whisper`
* **Feature Engineering:** `openSMILE`, `scikit-learn`
* **Modeling:** `scikit-learn`, `xgboost`


## **📊 Metrics for Evaluation**

* **ASR:** Word Error Rate (**WER**)
* **Personality Model:** Accuracy, F1-score
* **Pipeline Performance:** Average processing time per call

--

## **🚀 How to Run**

1. **Clone this repository**:

   ```bash
   git clone https://github.com/your-username/customer-personality-profiling.git
   cd customer-personality-profiling
   ```
2. **Install dependencies**:

   ```bash
   pip install -r requirements.txt
   ```
3. **Prepare your dataset** under `data/`
4. **Run the pipeline**:

   ```bash
   python src/main.py
   ```

---

## **✅ Example Output**

```json
{
  "call_id": "A001",
  "transcript": "Hello, I can’t access my account...",
  "personality_label": "Short-tempered",
  "suggestions": [
    "Stay calm and acknowledge frustration",
    "Provide clear and quick solutions"
  ]
}
```

## **📌 Future Improvements**

* Real-time streaming for **live call analysis**
* Integration with **CRM systems**
* Use of **transformer-based personality models**

---

## **📜 License**

This project is licensed under the **MIT License**.
