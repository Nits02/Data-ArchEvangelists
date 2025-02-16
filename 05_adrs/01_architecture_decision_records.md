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

