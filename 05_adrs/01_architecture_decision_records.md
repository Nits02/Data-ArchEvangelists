# ADR-001: Selection of AI-Based Automated Grading

## 📅 Date
2025-02-16

## 🎯 Status
✅ Approved

## 📌 Context
Manual grading of short-answer and case-study-based certification tests is time-consuming, inconsistent, and prone to biases. An AI-powered grading system is required to ensure scalability, fairness, and efficiency.

## 💡 Decision
We will implement an AI-based grading engine using **Generative AI (GPT-4) and Transformer models (BERT, T5, RoBERTa)** to analyze responses. The system will include:
- **Text Preprocessing:** Normalizing responses by removing typos and irrelevant words.
- **Semantic Matching:** AI evaluates meaning using NLP, rather than exact words.
- **AI-Powered Rubric:** Assigns partial credit based on predefined scoring weightage.
- **Feedback Generation:** Personalized improvement suggestions from AI.

## 🛠 Technologies
- **NLP Models:** OpenAI GPT-4, Hugging Face Transformers (BERT, T5, RoBERTa)
- **Model Hosting:** Azure OpenAI / AWS SageMaker
- **Similarity Matching:** FAISS, SentenceTransformers

## 🚀 Consequences
✅ Faster grading (~80-90% efficiency improvement).  
✅ Ensures fairness and consistency.  
✅ Reduces expert workload.  
❗ Requires explainability mechanisms to ensure trust in AI-based grading.

## 📌 Alternatives Considered
1️⃣ **Traditional Rule-Based Grading** – Inflexible and does not capture meaning. ❌  
2️⃣ **Fully Manual Grading** – Not scalable for large volumes. ❌  
3️⃣ **Hybrid Approach** (AI + Human Review) – Selected as the best approach. ✅  

# ADR-002: Human-AI Hybrid Model for Complex Case Study Evaluations

## 📅 Date
2025-02-16

## 🎯 Status
✅ Approved

## 📌 Context
Case study-based certification tests require critical thinking evaluation, making full automation difficult. Some responses require human judgment to ensure correctness.

## 💡 Decision
We will use a **Human-AI Hybrid Model**:
- AI performs the initial grading and assigns a **confidence score**.
- Responses with **low-confidence scores** are escalated to expert reviewers.
- Experts validate AI-graded responses and provide feedback to improve model accuracy.

## 🛠 Technologies
- **AI-Based Grading:** OpenAI GPT-4, Hugging Face Transformers
- **Human-in-the-Loop (HITL) Pipeline:** Label Studio, Amazon Augmented AI (A2I)
- **Confidence Score Mechanism:** AI flags responses needing review

## 🚀 Consequences
✅ Balances automation and human expertise.  
✅ Continuous AI model improvement via expert feedback.  
✅ Ensures fairness in grading.  
❗ Increases complexity in system integration.

## 📌 Alternatives Considered
1️⃣ **Fully AI-Driven Grading** – Lacks human judgment, leading to potential misinterpretation. ❌  
2️⃣ **Fully Manual Grading** – Slow and costly. ❌  
3️⃣ **Human-AI Hybrid Approach** – Selected as the most efficient and fair solution. ✅  


# ADR-003: Scalable Cloud Infrastructure for AI Grading System

## 📅 Date
2025-02-16

## 🎯 Status
✅ Approved

## 📌 Context
The grading system must handle **high-volume certification requests**, requiring **scalability and cost efficiency**.

## 💡 Decision
We will deploy the AI grading models on a **cloud-native, serverless architecture**:
- **Compute:** Azure Machine Learning with AKS / AWS SageMaker with Lambda
- **Storage:** Vector databases (FAISS) for semantic similarity
- **Security:** Role-based access control (RBAC), encryption, audit logging

## 🛠 Technologies
- **Cloud Provider:** Azure / AWS / GCP
- **Serverless Execution:** Azure Functions, AWS Lambda
- **Containerization:** Kubernetes (AKS / EKS)

## 🚀 Consequences
✅ Scales dynamically with demand.  
✅ Reduces infrastructure cost via serverless execution.  
✅ Ensures high availability and fault tolerance.  
❗ Requires cloud cost monitoring and governance.

## 📌 Alternatives Considered
1️⃣ **On-Premises Deployment** – High maintenance, not scalable. ❌  
2️⃣ **Traditional VMs** – Inefficient and costly. ❌  
3️⃣ **Cloud-Native, Serverless Architecture** – Best for scalability and cost efficiency. ✅  


# ADR-004: Explainable AI (XAI) for Trust & Transparency in Grading

## 📅 Date
2025-02-16

## 🎯 Status
✅ Approved

## 📌 Context
Candidates and reviewers need visibility into AI-driven grading decisions to **ensure trust and fairness**.

## 💡 Decision
We will implement **Explainable AI (XAI) techniques** to make AI grading decisions **auditable and interpretable**:
- **SHAP (SHapley Additive Explanations)** for feature importance analysis.
- **LIME (Local Interpretable Model-Agnostic Explanations)** to generate interpretable output.
- **Grading Breakdown Dashboard** for candidates to review score justifications.

## 🛠 Technologies
- **Explainability Frameworks:** SHAP, LIME
- **Dashboard Implementation:** React, Flask / FastAPI
- **Logging & Auditability:** ELK Stack (Elasticsearch, Logstash, Kibana)

## 🚀 Consequences
✅ Builds trust with candidates and reviewers.  
✅ Provides auditability for certification programs.  
✅ Improves AI model interpretability.  
❗ Adds computational overhead for XAI processing.

## 📌 Alternatives Considered
1️⃣ **No Explainability (Black Box AI)** – Lacks transparency, reduces trust. ❌  
2️⃣ **Rule-Based Explainability** – Too rigid for AI grading. ❌  
3️⃣ **XAI Techniques (SHAP, LIME, Dashboard)** – Best for transparency and fairness. ✅  

____________________________

# 🏗 Architecture Decision Records (ADR) - AI-Powered Certification Evaluation System

## **ADR-001: Selection of AI Model for Automated Grading**

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

## **ADR-003: Cloud-Native Infrastructure for AI Grading**

### 📅 Date: 2025-02-16
### 🎯 Status: ✅ Accepted

### **📌 Context**
The system needs to scale efficiently as certification requests increase. A **cloud-based approach** ensures **high availability, auto-scaling, and cost-effectiveness**.

### **💡 Decision**
The AI grading and feedback system will be deployed on **Azure Kubernetes Service (AKS) / AWS SageMaker** with **serverless execution using Azure Functions / AWS Lambda**.

### **🛠 Technologies**
- **Model Deployment:** Azure ML, AWS SageMaker
- **Serverless Execution:** Azure Functions, AWS Lambda
- **Storage:** Azure Blob / AWS S3 for file handling

### **🚀 Consequences**
✅ Handles peak loads dynamically  
✅ Reduces operational costs via serverless execution  
✅ Supports multi-region deployments for better performance  
❗ Requires cloud cost monitoring and security governance

### **📌 Alternatives Considered**
1️⃣ **On-Premises Deployment** – High maintenance, lacks elasticity ❌  
2️⃣ **Traditional VMs** – Costly and inefficient for scaling ❌  
3️⃣ **Cloud-Native, Serverless Architecture (Chosen Approach)** – Most efficient and scalable ✅

---

## **ADR-004: Explainable AI (XAI) for Transparent Grading**

### 📅 Date: 2025-02-16
### 🎯 Status: ✅ Accepted

### **📌 Context**
AI grading needs to be **transparent and interpretable** for candidates and auditors. Explainable AI (XAI) techniques are required to **justify AI-driven grading decisions**.

### **💡 Decision**
We will implement **SHAP (SHapley Additive Explanations)** and **LIME (Local Interpretable Model-Agnostic Explanations)** to **break down AI grading logic** into human-understandable formats.

### **🛠 Technologies**
- **XAI Frameworks:** SHAP, LIME
- **Interactive Dashboard:** React.js, Flask/FastAPI for score explainability
- **Logging & Auditability:** ELK Stack (Elasticsearch, Logstash, Kibana)

### **🚀 Consequences**
✅ Builds trust in AI grading outcomes  
✅ Enables candidates to understand their scores  
✅ Allows auditors to validate AI decisions  
❗ Adds computational overhead for explainability processing

### **📌 Alternatives Considered**
1️⃣ **No Explainability (Black Box AI)** – Lacks transparency ❌  
2️⃣ **Rule-Based Explainability** – Too rigid for AI grading ❌  
3️⃣ **XAI Techniques (SHAP, LIME, Dashboard) (Chosen Approach)** – Best for transparency ✅

---
