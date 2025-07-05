# 💬 Sentiment Analysis of GoPay App Reviews using Deep Learning

<p align="center">
  <img src="https://brandlogos.net/wp-content/uploads/2022/10/gopay-logo_brandlogos.net_gph3u.png" alt="GoPay Logo" width="200"/>
</p>

## 📌 Background

Digital payment systems like **GoPay** play a pivotal role in Indonesia's financial ecosystem. To maintain user satisfaction and product quality, it's essential to **analyze user feedback** effectively. This project performs **sentiment analysis** on GoPay app reviews scraped from the Google Play Store, classifying them as **positive** or **negative** using several deep learning models.

## 🛠 Methodology

The end-to-end pipeline involves the following stages:

1. **Data Collection**:

   * Reviews are scraped from the Google Play Store using `Data Scraping.ipynb`.
   * The dataset is stored as `gopay_app_reviews.csv`.

2. **Text Preprocessing**:

   * Includes lowercasing, tokenization, stopword removal, and normalization using `kamuskatabaku.xlsx`.

3. **Modeling**:

   * Three different RNN-based architectures are trained using TensorFlow/Keras:

     * **LSTM** (`model_lstm.h5`)
     * **GRU** (`model_gru.h5`)
     * **Simple RNN** (`model_rnn.h5`)
   * Tokenizer used for training is saved in `tokenizer.pickle`.

4. **Model Inference**:

   * `Inference.ipynb` demonstrates how to load the models and tokenizer for real-time sentiment prediction.

5. **Evaluation**:

   * Each model is evaluated on metrics like **accuracy**, **loss**, and **F1-score**.
   * The best-performing model is selected for deployment.

## 🔍 Key Insights

* **LSTM outperformed GRU and Simple RNN**, offering better accuracy and generalization.
* Proper text normalization (using the standard word list from `kamuskatabaku.xlsx`) significantly improved classification quality.
* The model can effectively classify sentiment from short user reviews in Bahasa Indonesia.

## 🧪 Project Structure

```
📦 Sentiment Analysis GoPay
├── Models/
│   ├── model_gru.h5
│   ├── model_lstm.h5
│   └── model_rnn.h5
├── Scraping/
│   └── Data Scraping.ipynb
├── gopay_app_reviews.csv
├── Inference.ipynb
├── Analisis Sentimen Pengguna App.ipynb
├── kamuskatabaku.xlsx
├── tokenizer.pickle
├── requirements.txt
├── Pipfile
└── README.md
```

## 📈 Example Output

* Input: *"Aplikasinya gampang digunakan dan sangat membantu!"*
* Prediction: **Positive**
