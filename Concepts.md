If you mean the **AWS Certified AI Practitioner exam (AIF-C01)**, the exam focuses on understanding **AI, machine learning, generative AI, foundation models, responsible AI, and AWS AI services**. You generally don't need deep ML mathematics or heavy coding.

The main concepts break down like this:

| Domain                               | Approx. exam weight | What to know                                                                               |
| ------------------------------------ | ------------------: | ------------------------------------------------------------------------------------------ |
| **1. AI & ML Fundamentals**          |                 20% | AI vs ML vs deep learning, supervised/unsupervised learning, inference, basic ML lifecycle |
| **2. Generative AI Fundamentals**    |                 24% | Generative AI, foundation models, LLMs, tokens, embeddings, transformers, prompting        |
| **3. Foundation Model Applications** |                 28% | Amazon Bedrock, RAG, vector databases, prompt engineering, model selection/customization   |
| **4. Responsible AI**                |                 14% | Bias, fairness, hallucinations, explainability, transparency, safety                       |
| **5. Security & Governance**         |                 14% | IAM, encryption, privacy, compliance, data governance, shared responsibility               |

### 1. AI and Machine Learning Fundamentals

Make sure you understand the hierarchy:

**Artificial Intelligence → Machine Learning → Deep Learning → Generative AI**

Know common ML types:

* **Supervised learning** — learns from labeled data

  * Classification: spam/not spam
  * Regression: predict house price
* **Unsupervised learning** — discovers patterns without labels

  * Clustering
* **Reinforcement learning** — learns through rewards/penalties
* **Inference** — using a trained model to make predictions
* **Training** — teaching the model from data

Also understand basic concepts such as **features, labels, training datasets, validation/testing, overfitting, underfitting, and model evaluation**.

### 2. Generative AI

This is a major part of AIF-C01.

Know these terms especially well:

**Foundation Model (FM):** A large model trained on broad datasets that can be adapted to many tasks.

**Large Language Model (LLM):** A foundation model designed primarily around language.

**Tokens:** Pieces of text processed by an LLM.

**Context window:** How much information the model can consider at once.

**Embedding:** Numerical/vector representation of information such as text.

**Transformer:** Architecture behind most modern LLMs.

You should understand GenAI use cases such as summarization, chatbots, question answering, code generation, content generation, classification, and information extraction.

### 3. Prompt Engineering

Know the differences between:

* **Zero-shot** — instruction without examples
* **One-shot** — one example
* **Few-shot** — several examples
* **Chain-of-thought/reasoning techniques**
* **Prompt templates**
* **Negative prompting**

A good prompt commonly includes **instructions + context + input + desired output format**.

### 4. RAG — Very Important

**Retrieval-Augmented Generation (RAG)** is one of the highest-value concepts to understand.

Think:

**Question → retrieve relevant company documents → add them to prompt/context → foundation model → answer**

RAG allows an FM to answer using external/proprietary information without necessarily retraining the model.

Know:

**Documents → chunking → embeddings → vector store → similarity search → retrieved context → LLM**

Also understand the distinction between **RAG and fine-tuning**.

**RAG:** Give the model relevant information at inference time. Good when knowledge changes frequently.

**Fine-tuning:** Modify the model using additional training data. Good when you want to change/model specialized behavior or task performance.

### 5. Amazon Bedrock

This is probably the **single most important AWS service** for AIF-C01.

Amazon Bedrock provides managed access to foundation models from AWS and other model providers.

Know concepts including:

* Foundation models
* Bedrock Knowledge Bases
* Bedrock Agents
* Guardrails for Amazon Bedrock
* Model evaluation
* RAG
* Prompt management
* Model customization

Understand the difference between **Amazon Bedrock and Amazon SageMaker AI**:

**Bedrock → easiest way to build GenAI applications using foundation models.**

**SageMaker AI → broader ML platform for building, training, deploying, and managing ML models.**

### 6. AWS AI Services

Be able to recognize which service fits a scenario.

| AWS service             | Main purpose                     |
| ----------------------- | -------------------------------- |
| **Amazon Bedrock**      | Build generative AI applications |
| **Amazon SageMaker AI** | Build/train/deploy ML models     |
| **Amazon Q**            | Generative AI assistant          |
| **Amazon Rekognition**  | Image/video analysis             |
| **Amazon Textract**     | Extract text/data from documents |
| **Amazon Comprehend**   | NLP/text analysis                |
| **Amazon Transcribe**   | Speech → text                    |
| **Amazon Polly**        | Text → speech                    |
| **Amazon Translate**    | Language translation             |
| **Amazon Lex**          | Conversational/chat interfaces   |

Expect questions like:

> A company needs to extract fields from thousands of scanned invoices. Which AWS service should they use?

→ **Amazon Textract**

### 7. Responsible AI

Know these concepts:

* **Fairness**
* **Bias**
* **Explainability**
* **Transparency**
* **Privacy**
* **Safety**
* **Robustness**
* **Human oversight**

Also understand **hallucinations**: an LLM can generate an answer that sounds convincing but is incorrect.

Ways of reducing problems can include RAG/grounding, better prompts, guardrails, model evaluation, human review, and appropriate data quality.

### 8. Security

Know the standard AWS security concepts as they apply to AI:

**IAM → who can access what**

**KMS → encryption keys**

**CloudTrail → auditing/API activity**

**Encryption at rest/in transit**

**Least privilege**

**Data privacy**

**AWS Shared Responsibility Model**

Also understand that organizations need to think carefully about **sensitive information/PII being included in prompts or training data**.

### What I'd prioritize for the exam

If you're studying efficiently, I'd put the most effort into:

**Amazon Bedrock → RAG → Foundation Models/LLMs → Prompt Engineering → Responsible AI → AWS AI services → Security/IAM → Basic ML concepts**

And memorize these comparisons:

**AI vs ML vs Deep Learning vs GenAI**
**Training vs Inference**
**Supervised vs Unsupervised learning**
**RAG vs Fine-tuning**
**Bedrock vs SageMaker AI**
**Tokens vs Embeddings**
**Temperature vs other inference parameters**
**Hallucination vs Bias**
**Textract vs Comprehend vs Rekognition**
**Transcribe vs Polly**

If you can explain each of those comparisons and recognize the appropriate AWS service from a scenario, you'll have covered a large portion of what AIF-C01 is testing.
