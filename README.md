# ⚡ Real-Time Hate Speech Detection System using BERT & AWS Serverless Stack

A production-grade, full-stack AI application that detects toxic and hateful comments in **real time**. This system uses a **BERT-based model** trained on the **Jigsaw Toxic Comment Classification** dataset and leverages **AWS Serverless Services** (SageMaker, Lambda, API Gateway, and S3) to deliver scalable, cost-efficient predictions without managing infrastructure.

---

## 🌐 Live Features

- 🧠 Real-time toxicity classification using **BERT**
- ☁️ End-to-end AWS serverless infrastructure
- 🖥️ Simple web-based UI for testing
- 🚀 Scalable, secure, and fully managed deployment
- 🔒 No backend servers — 100% serverless architecture

---

## 📦 Tech Stack

### 🔍 Machine Learning
- **TensorFlow/Keras / Hugging Face Transformers** – Deep learning & NLP frameworks
- **BERT** – Transformer-based model architecture for text classification
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

## 🧩 How It Works – End-to-End Pipeline

![WhatsApp Image 2025-04-30 at 10 24 14_f77d01fb](https://github.com/user-attachments/assets/6a013085-1e68-4fb8-bf4f-091936bd18e1)

---

## 🔧 Key Implementation Steps

### 1️⃣ Model Training (Local or Notebook)
- Preprocessed text using **BERT tokenizer** (wordpiece tokenization).
- Used a **pretrained BERT model (e.g., `bert-base-uncased`)** fine-tuned for multi-label classification.
- Applied **Sigmoid activation** for multi-label outputs.
- Used **Binary Cross-Entropy loss** function.
- Trained and saved the model as `bert_model.h5` or exported with `SavedModel`.



### 2️⃣ Packaging and Uploading
- Exported the model directory or `.tar.gz` archive using `transformers` + `TensorFlow SavedModel` format.
- Uploaded the archive to **Amazon S3** for SageMaker to access.

![image](https://github.com/user-attachments/assets/59d16faa-9087-4da3-a533-f950c5e39bfd)

### 3️⃣ Hosting with SageMaker
- Created a **TensorFlowModel** or Hugging Face model endpoint in SageMaker.
- Deployed the model on an `ml.m5.large` or similar instance.
- Configured a **SageMaker Endpoint** for real-time inference.

![image](https://github.com/user-attachments/assets/85576b5a-73e4-4b9f-b145-ab24fa14d098)

### 4️⃣ Lambda Backend
- Created a **Python-based AWS Lambda function**:
  - Receives user comment as input.
  - Tokenizes text using **BERT tokenizer** inside the Lambda or during preprocessing.
  - Sends payload to SageMaker endpoint.
  - Parses and returns prediction results.

![image](https://github.com/user-attachments/assets/260c0fbc-3e4a-482a-898f-d7dcfab97cef)

### 5️⃣ REST API via API Gateway
- Configured an **HTTP POST** method linked to the Lambda function.
- Enabled **CORS** for frontend communication.
- Deployed the API and generated a public **invoke URL**.

### 6️⃣ Web Interface
- Designed a clean and responsive UI using **HTML/CSS**.
- Integrated API calls using JavaScript `fetch()`.
- Displayed prediction results dynamically on the frontend.

![image](https://github.com/user-attachments/assets/952f5174-4965-4c27-8bab-0f3e4fee3860)

---

## 📈 Performance & Optimization

- ✅ Low-latency predictions due to SageMaker’s optimized transformer inference.
- ⚡ Instant scalability using AWS serverless services.
- 💸 Cost-effective: no always-on compute resources required.
- 🔐 IAM roles ensure secure communication between components.
- 🚀 Accuracy of about 92%

  ![ev](https://github.com/user-attachments/assets/170254a1-da8a-4c1f-9cd3-2f7808e75d1d)


---

## 🚀 Why This Project Matters

- Promotes **ethical AI** by identifying and flagging hate speech.
- Demonstrates **end-to-end deep learning model deployment**.
- Enables **real-time AI inference** via a lightweight, frontend-connected pipeline.
- Bridges the gap between **research models** and **practical applications** using **transformers**.

---

## 🎯 Learning Highlights

- Built a complete **MLOps pipeline** using managed AWS services.
- Learned infrastructure-free ML deployment with **SageMaker & Lambda**.
- Gained hands-on experience with **BERT-based multi-label classification**.
- Connected ML backend to a functional **real-time web interface**.

---

## 🛡️ Future Improvements

- 🔐 Add user authentication using AWS Cognito or Firebase.
- 💾 Store flagged results in DynamoDB or S3 for moderation review.
- 🤖 Upgrade to more advanced models like **RoBERTa**, **DeBERTa**, or **DistilBERT**.
- 📊 Visualize predictions using frontend charting libraries.
