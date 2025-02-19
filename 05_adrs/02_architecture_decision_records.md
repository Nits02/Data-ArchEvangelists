____________________________

# 🏗 Architecture Decision Records (ADR) - AI-Powered Certification Evaluation System

## **ADR-002: Selection of AI Model for Automated Grading**

### 📅 Date: 2025-02-16
### 🎯 Status: ✅ Accepted

### **📌 Context**
Manual grading of certification submissions is **slow, inconsistent, and unscalable**. To improve efficiency, **an AI-powered grading system** is needed to automate evaluations while ensuring **fairness and explainability**.

### **💡 Decision**
We will use **GPT-4** for analyzing text-based responses and **Graph Neural Networks (GNNs)** for evaluating architecture diagrams. The AI grading system will be supplemented with **human review for low-confidence cases**.

### **🛠 Technologies**
- **NLP Models:** GPT-4, Hugging Face Transformers (BERT, T5, RoBERTa)
- **Diagram Analysis:** YOLO/Detectron2 for architecture recognition
- **Model Hosting:** Azure OpenAI / AWS SageMaker

### **🚀 Consequences**
✅ Faster grading (~80-90% reduction in grading time)  
✅ Standardized and unbiased evaluations  
✅ Reduces expert workload by focusing on edge cases  
❗ Requires cloud hosting and periodic retraining

### **📌 Alternatives Considered**
1️⃣ **Fully Manual Grading** – Slow, costly, and not scalable ❌  
2️⃣ **Rule-Based AI** – Limited adaptability, hard to maintain ❌  
3️⃣ **Hybrid AI + Human Review (Chosen Approach)** – Best balance of speed and quality ✅

---

## **ADR-002: AI-Driven Feedback Generation**

### 📅 Date: 2025-02-16
### 🎯 Status: ✅ Accepted

### **📌 Context**
Manual feedback generation is inconsistent and delays certification. AI-generated feedback can **improve response time and maintain quality**.

### **💡 Decision**
An **AI-based feedback engine** will automatically generate **personalized, structured feedback** for candidates based on predefined rubrics and best practices.

### **🛠 Technologies**
- **Text-Based Feedback:** GPT-4 fine-tuned for grading responses
- **Explainability (XAI):** SHAP, LIME for transparency in feedback
- **Feedback Storage:** NoSQL (MongoDB, DynamoDB) for scalability

### **🚀 Consequences**
✅ 80% reduction in feedback response time  
✅ More structured and actionable feedback for candidates  
✅ Scalable for high submission volumes  
❗ Requires monitoring to avoid AI hallucinations

### **📌 Alternatives Considered**
1️⃣ **Manual Feedback** – Too slow and inconsistent ❌  
2️⃣ **Template-Based AI Responses** – Lacks personalization ❌  
3️⃣ **AI-Generated + Expert Validation (Chosen Approach)** – Ensures efficiency with quality control ✅

---