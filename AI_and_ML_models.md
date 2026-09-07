
````markdown
# 🌳 AI / ML Model Hierarchy with Real-World Examples

```text
🤖 ARTIFICIAL INTELLIGENCE (AI)
│
│   Example → Self-driving car making intelligent driving decisions
│
└── 📊 MACHINE LEARNING (ML)
    │
    │   Example → Netflix learning what movies you might enjoy
    │
    ├── 🎓 SUPERVISED LEARNING
    │   │
    │   │   Training data has known answers (labels)
    │   │
    │   ├── 📈 REGRESSION → Predict a NUMBER
    │   │   │
    │   │   └── Linear Regression
    │   │       └── 🏠 Example → Predict house price: $625,000
    │   │
    │   └── 🎯 CLASSIFICATION → Predict a CATEGORY
    │       │
    │       ├── Logistic Regression
    │       │   └── 📧 Example → Email: SPAM or NOT SPAM
    │       │
    │       ├── Decision Tree
    │       │   └── 💳 Example → Loan: APPROVE or REJECT
    │       │
    │       ├── Random Forest
    │       │   └── 🚨 Example → Transaction: FRAUD or NORMAL
    │       │
    │       ├── Gradient Boosting
    │       │   └── 🏦 Example → Predict customer's loan default risk
    │       │
    │       ├── K-Nearest Neighbors (KNN)
    │       │   └── 🍎 Example → Unknown fruit classified from similar fruits
    │       │
    │       └── Support Vector Machine (SVM)
    │           └── 🛡️ Example → Website: MALICIOUS or SAFE
    │
    ├── 🕵️ UNSUPERVISED LEARNING
    │   │
    │   │   Training data does NOT have known labels
    │   │
    │   └── K-Means Clustering
    │       └── 🛒 Example → Group customers by shopping behavior
    │
    ├── 🎮 REINFORCEMENT LEARNING
    │   │
    │   │   Learn through rewards and penalties
    │   │
    │   └── Reinforcement Learning Agent
    │       └── 🏎️ Example → AI learns to drive in a racing game
    │
    └── 🧠 DEEP LEARNING
        │
        │   Uses multi-layer neural networks
        │
        ├── Artificial Neural Network (ANN)
        │   └── ✍️ Example → Recognize handwritten digits
        │
        ├── Convolutional Neural Network (CNN)
        │   └── 🏭 Example → Detect defective products from factory images
        │
        ├── Recurrent Neural Network (RNN)
        │   └── 📈 Example → Predict future sales from previous sales
        │
        ├── Long Short-Term Memory (LSTM)
        │   └── ⚡ Example → Forecast electricity demand using historical data
        │
        ├── Autoencoder
        │   └── 💳 Example → Detect unusual/anomalous transactions
        │
        ├── Transformer
        │   └── 💬 Example → Understand and generate natural language
        │
        └── ✨ GENERATIVE AI
            │
            │   Creates NEW content
            │
            ├── Large Language Model (LLM)
            │   └── 💬 Example → Chatbot generates an answer to a question
            │
            ├── Diffusion Model
            │   └── 🎨 Example → Generate an image from a text prompt
            │
            ├── Generative Adversarial Network (GAN)
            │   └── 👤 Example → Generate realistic synthetic human faces
            │
            └── Foundation Model
                └── 🏗️ Example → Amazon Bedrock model adapted for Q&A,
                                  summarization, extraction, or a chatbot
```

---

# 👁️ Computer Vision Tasks

Computer Vision is an **AI field** rather than one specific model.

Different models such as CNNs and Vision Transformers can be used to perform these tasks.

```text
👁️ COMPUTER VISION
│
├── 📷 Image Classification
│   │
│   └── Example → 🐕 Image → "DOG"
│
├── 🔎 Object Detection
│   │
│   └── Example → 🚗 Self-driving car finds:
│                 CAR    → [Bounding Box]
│                 PERSON → [Bounding Box]
│
└── 🖌️ Semantic Segmentation
    │
    └── Example → 🚗 Self-driving car labels individual pixels:
                  Road pixels   → ROAD
                  Car pixels    → CAR
                  Person pixels → PERSON
```

### Memory Trick

```text
📷 Classification → WHAT?

🔎 Detection      → WHAT + WHERE?

🖌️ Segmentation  → WHICH PIXELS?
```

---

# 🧭 Embedding / Representation Models

Embedding models are especially important in modern Generative AI applications.

```text
🧭 EMBEDDING MODEL
│
│   Converts meaning into numerical vectors
│
└── 📚 Example → Semantic Search / RAG
```

Real-world example:

```text
Company Document:

"Employees receive 20 days of annual paid leave."


User:

"How much vacation do I get?"

             ↓

      Embedding Model

             ↓

"vacation" ≈ "annual paid leave"

             ↓

      Vector Search

             ↓

Find Relevant Document

             ↓

            LLM

             ↓

"Employees receive 20 days of annual paid leave."
```

### 🧠 Remember

> **Embedding = MEANING → VECTOR**

---

# 🚀 Ultra-Fast Reference

```text
MODEL / TECHNIQUE            THINK                 REAL EXAMPLE
────────────────────────────────────────────────────────────────────

Linear Regression      → NUMBER              → 🏠 House price

Logistic Regression    → CATEGORY            → 📧 Spam detection

Decision Tree          → IF / THEN           → 💳 Loan approval

Random Forest          → TREES VOTE          → 🚨 Fraud detection

Gradient Boosting      → FIX MISTAKES        → 🏦 Credit risk

KNN                    → NEIGHBORS           → 🍎 Fruit classification

SVM                    → BOUNDARY            → 🛡️ Malicious website

K-Means                → GROUPS              → 🛒 Customer segmentation

Reinforcement Learning → REWARDS             → 🏎️ Game-playing AI

ANN                    → COMPLEX PATTERNS    → ✍️ Handwriting recognition

CNN                    → IMAGE PATTERNS      → 🏭 Defect detection

RNN                    → SEQUENCE            → 📈 Sales forecasting

LSTM                   → LONG SEQUENCE       → ⚡ Electricity forecasting

Autoencoder            → RECONSTRUCT         → 💳 Anomaly detection

Transformer            → ATTENTION           → 💬 Language understanding

LLM                    → LANGUAGE            → 🤖 Chatbot

Diffusion              → GENERATE IMAGE      → 🎨 Text-to-image

GAN                    → GENERATOR vs JUDGE  → 👤 Synthetic faces

Embedding              → MEANING → VECTOR    → 📚 RAG / semantic search

Foundation Model       → GENERAL BASE MODEL  → 🏗️ Bedrock AI application

Image Classification   → WHAT?               → 🐕 "This is a dog"

Object Detection       → WHAT + WHERE?       → 🚗 Find pedestrian

Segmentation           → WHICH PIXELS?       → 🛣️ Identify road pixels
```

---

# 🧠 Exam Decision Tree

When you get a scenario question, start here:

```text
                     WHAT DOES THE COMPANY NEED?
                               │
          ┌────────────────────┼────────────────────┐
          │                    │                    │
          ▼                    ▼                    ▼
    Predict something?   Generate something?   Find patterns?
          │                    │                    │
          ▼                    ▼                    ▼
          ML               GENERATIVE AI       UNSUPERVISED
          │                    │                    │
    ┌─────┴─────┐         ┌────┴────┐              │
    ▼           ▼         ▼         ▼              ▼
 NUMBER?     CATEGORY?   TEXT?     IMAGE?        GROUPS?
    │           │         │         │              │
    ▼           ▼         ▼         ▼              ▼
Regression Classification LLM    Diffusion       K-Means
    │
    ▼
Linear Regression
    │
    └── 🏠 Example → Predict $625,000 house price
```
````
