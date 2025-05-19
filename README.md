# ⚡ Real-Time Hate Speech Detection System using **BiLSTM** & AWS Serverless Stack  
Visit at 👉 [https://priyanshu1512.github.io/hatespeech/](https://priyanshu1512.github.io/hatespeech/)

A production-grade, full-stack AI application that detects toxic and hateful comments in **real time**. This system uses a **BiLSTM-based model** trained on the **Jigsaw Toxic Comment Classification** dataset and leverages **AWS Serverless Services** (SageMaker, Lambda, API Gateway, and S3) to deliver scalable, cost-efficient predictions without managing infrastructure.

---

## 🌐 Live Features

- 🧠 Real-time toxicity classification using **BiLSTM**
- ☁️ End-to-end AWS serverless infrastructure
- 🖥️ Simple web-based UI for testing
- 🚀 Scalable, secure, and fully managed deployment
- 🔒 No backend servers — 100% serverless architecture

---

## 📦 Tech Stack

### 🔍 Machine Learning
- **TensorFlow/Keras** – Deep learning & NLP frameworks  
- **BiLSTM (Bidirectional Long Short-Term Memory)** – Sequence-based model architecture for text classification  
- **Jigsaw Toxic Comment Dataset** – Multi-label dataset for hate speech

### ☁️ Cloud Infrastructure (AWS)
- **Amazon S3** – Storage for model artifacts  
- **Amazon SageMaker** – Managed service to host and deploy ML models  
- **AWS Lambda** – Serverless inference logic  
- **API Gateway** – Exposes Lambda as a public REST API  

### 💻 Frontend
- **HTML/CSS/JavaScript** – Simple and responsive interface  
- **AJAX** – Asynchronous communication with API Gateway  

---

## 🧠 What is BiLSTM?

**BiLSTM (Bidirectional Long Short-Term Memory)** is a type of recurrent neural network (RNN) that processes input data in both **forward and backward directions**, capturing context from **past (left)** and **future (right)** tokens in a sequence. This dual context makes it especially powerful for natural language tasks like sentiment analysis or hate speech detection, where understanding the full context of a sentence is critical.

- ✅ Captures contextual information from both directions  
- ✅ Suitable for sequence modeling and text classification  
- 🚀 Lightweight compared to transformer-based models  

---

## 🧩 How It Works – End-to-End Pipeline

![Pipeline](https://github.com/user-attachments/assets/6a013085-1e68-4fb8-bf4f-091936bd18e1)

---

## 🔧 Key Implementation Steps

### 1️⃣ Model Training (Local or Notebook)
- Preprocessed text using standard tokenization and sequence padding
- Built and trained a **BiLSTM-based neural network** for multi-label classification
- Used **Sigmoid activation** for multi-label outputs
- Applied **Binary Cross-Entropy** loss function
- Trained and saved the model as `bilstm_model.h5` or `SavedModel` format

### 2️⃣ Packaging and Uploading
- Exported model directory as `.tar.gz`
- Uploaded to **Amazon S3** for SageMaker access

![Upload](https://github.com/user-attachments/assets/59d16faa-9087-4da3-a533-f950c5e39bfd)

### 3️⃣ Hosting with SageMaker
- Created a **TensorFlowModel** endpoint using SageMaker
- Deployed model on `ml.m5.large` or similar instance
- Enabled real-time inference via endpoint

![SageMaker](https://github.com/user-attachments/assets/85576b5a-73e4-4b9f-b145-ab24fa14d098)

### 4️⃣ Lambda Backend
- Created a **Python AWS Lambda function** to:
  - Accept comment input
  - Tokenize and vectorize for BiLSTM
  - Call SageMaker endpoint
  - Return predictions to frontend

![Lambda](https://github.com/user-attachments/assets/260c0fbc-3e4a-482a-898f-d7dcfab97cef)

### 5️⃣ REST API via API Gateway
- Configured **HTTP POST** endpoint
- Linked to Lambda function
- Enabled **CORS**
- Generated public URL for frontend calls

### 6️⃣ Web Interface
- Responsive UI with **HTML/CSS**
- Handled API calls using JavaScript `fetch()`
- Displayed results dynamically

![Frontend](https://github.com/user-attachments/assets/952f5174-4965-4c27-8bab-0f3e4fee3860)

---

## 📈 Performance & Optimization

- ✅ Low-latency inference using SageMaker
- ⚡ Scales instantly via AWS serverless
- 💸 Cost-effective: pay-per-use model
- 🔐 Secure via IAM roles and policies
- 🎯 Accuracy: ~72%( can be increased using BERT ) 

![Evaluation](https://github.com/user-attachments/assets/170254a1-da8a-4c1f-9cd3-2f7808e75d1d)

---

## 🚀 Why This Project Matters

- Promotes **ethical AI** by detecting hate speech
- Demonstrates **end-to-end ML deployment** in production
- Offers **real-time inference** using serverless AWS
- Converts research into **practical applications**

---

## 🎯 Learning Highlights

- Built a complete **MLOps pipeline** using AWS
- Learned **serverless ML deployment** using Lambda and SageMaker
- Hands-on with **BiLSTM multi-label classification**
- Connected ML backend to live frontend

---

## 🛡️ Future Improvements

- 🔐 Add authentication (e.g., AWS Cognito / Firebase)  
- 💾 Store flagged comments in DynamoDB or S3  
- 🤖 **Upgrade to transformer-based models like BERT, RoBERTa, or DeBERTa** for higher contextual accuracy  
- 📊 Add charts and visual insights in frontend  

---

