Here are the concepts I would learn from this page.

### 1. Responsible AI: bias, fairness, explainability

This is a major theme.

**Amazon SageMaker Clarify** is the AWS service to associate with:

> **Bias + explainability → SageMaker Clarify**

For example, Q101 describes a loan model where the company needs both bias detection and explanations of predictions. That points to **SageMaker Clarify**. 

Know the distinction:

| Concept              | Meaning                                                                |
| -------------------- | ---------------------------------------------------------------------- |
| **Bias**             | Systematic unfairness in data/model behavior                           |
| **Fairness**         | Different groups should receive appropriately equitable treatment      |
| **Explainability**   | Understanding *why* the model made a prediction                        |
| **Transparency**     | Making information about the model, its development, and use available |
| **Privacy/security** | Protecting data and systems                                            |

Q148 gives you a classic fairness scenario: resumes used for training are **not representative of all demographics**. That's a **fairness/bias** problem. 

Also remember:

**More complex model → generally harder to explain.**

Simple models such as linear/logistic regression are easier to interpret than deep neural networks.

---

### 2. SageMaker Model Cards vs SageMaker Clarify

These are easy to confuse.

**SageMaker Clarify**
→ analyzes **bias and explainability**

**SageMaker Model Cards**
→ **documents** a model.

Model Cards standardize information about things such as:

* model purpose
* intended use
* performance
* limitations
* risk information

That's exactly what Q145 is testing. 

Think:

**Clarify = analyze the model**
**Model Card = document the model**

---

### 3. Amazon Bedrock

You should know Bedrock very well for AIF-C01.

**Amazon Bedrock = AWS managed service for building generative AI applications with foundation models.**

You don't have to build an FM from scratch.

You'll see questions involving:

**Bedrock foundation models**
→ generate text/images/etc.

**Bedrock Knowledge Bases**
→ connect an FM to external/company information, commonly for **RAG**

**Agents for Amazon Bedrock**
→ allow an AI application to reason about requests and interact with information/systems to accomplish tasks.

For example, Q120 asks about employees checking claims and accessing claim documents. The combination is **Agents for Amazon Bedrock + Bedrock Knowledge Bases**. 

A useful mental model:

**Bedrock = brain/model access**
**Knowledge Base = company knowledge**
**Agent = takes actions / orchestrates tasks**

---

### 4. RAG — Retrieval Augmented Generation

This is one of the highest-value concepts to understand.

RAG essentially does:

**User question → retrieve relevant information → put information into prompt → FM generates answer**

Suppose your company's FAQ changes every week.

Instead of constantly retraining the model, store the current information somewhere the application can retrieve it.

Then:

> "What's our current refund policy?"

The application retrieves the current refund policy and supplies it as context to the FM.

That's why Q147's changing FAQ scenario points toward **RAG + prompt engineering**, rather than continually fine-tuning the model. 

Exam shortcut:

**Changing/current proprietary knowledge → think RAG.**

---

### 5. Prompt engineering vs fine-tuning vs training

AWS loves asking you to choose between these.

**Prompt engineering**

Change the instructions given to the model.

Cheap, fast, no model retraining.

Example:

`Summarize this review in exactly 3 bullet points.`

Q150 explicitly asks for the **most cost-effective** way to improve an FM's responses. Among fine-tuning, retraining, training a new FM, and prompt engineering, you should recognize **prompt engineering** as the lightweight first approach. 

**Fine-tuning**

Further train an existing model using a smaller task/domain-specific dataset.

Use it when you need the model's **behavior/style/task performance** customized more substantially.

**Pre-training / training a new FM**

Extremely expensive and data/compute intensive.

For AIF-C01, if AWS says:

> "MOST cost-effective"

creating a new FM is almost never going to beat prompt engineering or RAG.

---

### 6. Prompt engineering techniques

Several questions on your page hit this.

#### Zero-shot prompting

Give instructions with **no examples**.

`Classify this review as positive or negative: ...`

#### Few-shot prompting

Give the model **examples first**.

`Review: Great product → Positive`
`Review: Terrible product → Negative`
`Review: Pretty useful → ?`

#### Chain-of-thought prompting

The exam associates this with asking the model to reason through a problem **step-by-step**. Your PDF explicitly tests that association in Q133. 

#### Negative prompting

Tell a generative model what should **not** appear.

For image generation:

`Create a professional office photo. No text, no logos, no distorted hands.`

Q107 uses unrelated generated images as the scenario—the concept being tested is **negative prompting** to discourage unwanted content.

---

### 7. Temperature and hallucinations

**Temperature controls randomness/creativity.**

Think of it as:

**Lower temperature → more predictable**
**Higher temperature → more varied/creative**

So:

`temperature ↓ → randomness ↓`

If an LLM is hallucinating and you need more conservative output, **decreasing temperature** can help.

But don't interpret this as "temperature completely eliminates hallucinations." It doesn't.

---

### 8. Generative AI evaluation metrics

Your page tests several metrics.

#### BERTScore

Measures **semantic similarity** between generated and reference text.

It uses contextual embeddings, so sentences can receive a good score even if they don't use exactly the same words.

Q102 specifically asks about evaluating a Bedrock text summarization model and includes **BERTScore** among the choices. 

#### ROUGE

Commonly evaluates generated text against reference text based on overlap, especially in **summarization**.

Think:

> **ROUGE → summarization/reference similarity**

Your PDF uses ROUGE in a question about comparing generated readable text against provided examples. 

#### F1 score

Combines:

**precision + recall**

Conceptually:

`F1 = harmonic mean of precision and recall`

You don't need heavy math for AIF-C01. Remember:

> **F1 balances precision and recall.**

Q146 directly tests this definition. 

#### AUC

Area Under the ROC Curve.

Used primarily to evaluate **binary classification discrimination**, not generative text quality.

---

### 9. Supervised vs unsupervised learning

Very important basic ML concept.

**Supervised learning**

Training data contains **labels**.

Examples:

`email → spam`
`image → cat`
`customer → churn / no churn`

Therefore:

> **Labeled data → supervised learning**

Classification and regression are generally supervised-learning tasks.

**Unsupervised learning**

Training data doesn't contain target labels.

The model tries to discover patterns.

Examples:

* clustering
* dimensionality reduction

Your PDF's Q135 contrasts these directly: binary/multiclass classification versus K-means and dimensionality reduction. 

Memorize:

| Problem                   | Learning             |
| ------------------------- | -------------------- |
| Binary classification     | Supervised           |
| Multiclass classification | Supervised           |
| Regression                | Supervised           |
| K-means clustering        | Unsupervised         |
| Dimensionality reduction  | Usually unsupervised |

---

### 10. Classification vs regression vs clustering

This distinction will get you several questions.

**Classification**

Predict a **category**.

Examples:

`fraud / not fraud`
`cat / dog / bird`
`customer churn / no churn`

**Regression**

Predict a **number**.

Examples:

`House price = $425,000`

`Tomorrow's demand = 1,250 units`

**Clustering**

Find natural **groups** without predefined labels.

Example:

You have customer demographics and purchasing behavior and want to discover customer groups.

→ **K-means**

Your PDF explicitly asks for an algorithm to group customers by demographics and buying patterns—this is the classic K-means use case.

---

### 11. k-NN vs K-means

The names look similar but they're very different.

**k-Nearest Neighbors (k-NN)**

Typically supervised.

It looks at the nearest labeled examples and uses them to predict the new example's class/value.

Your flower example in Q103 asks you to classify flowers using petal/sepal measurements. That's a natural **k-NN classification** scenario. 

**K-means**

Unsupervised clustering.

No labels required.

Think:

**k-NN → predict a label from neighbors**
**K-means → discover groups**

---

### 12. Overfitting and regularization

Another important exam concept.

**Overfitting:**

> Model performs great on training data but poorly on new/unseen data.

Your Q109 describes exactly this situation.

Regularization discourages excessive model complexity.

Generally:

**more regularization → simpler model → potentially less overfitting**

So remember:

> **Great training performance + bad new-data performance = overfitting**

Potential solutions include regularization, simplifying the model, obtaining more representative training data, etc.

---

### 13. ML lifecycle

Your page tests the general ML lifecycle.

A simplified version is:

**Business problem → Develop/train model → Deploy → Monitor → iterate**

Q114 specifically gives these four stages to order:

**Define business goal and frame ML problem → Develop model → Deploy model → Monitor model**

The visual on page 5 shows those four choices in the hotspot. 

The first stage matters because you establish:

* business objectives
* success criteria
* constraints
* compliance/regulatory requirements
* whether ML is even appropriate

---

### 14. Continuous improvement

ML isn't necessarily:

`train → deploy → finished`

Real-world data changes.

Instead:

`new data → retrain/update → evaluate → redeploy → monitor`

Your PDF asks about continuously improving a food-waste prediction model. The important concept is **iterating with newer data**.

Also distinguish this from **continuous pre-training**, which updates an FM with newer data to keep it relevant. Q134 explicitly tests that terminology. 

---

### 15. Real-time inference vs batch inference

Very testable.

**Real-time inference**

Use when you need predictions immediately.

Examples:

`chatbot → answer now`

`fraud transaction → evaluate now`

`API → low latency`

**Batch inference / batch transform**

Use when you have lots of data and **don't need immediate results**.

Example:

`Process 2 TB of documents every Sunday night.`

Think:

**Need answer NOW → real-time**

**Large offline workload → batch**

Q125 in your PDF explicitly asks you to map chatbot/API low-latency cases versus a weekend gigabyte-scale text processing job to these inference modes. 

---

### 16. SageMaker endpoints

If you've trained an ML model and need a managed AWS deployment for predictions:

> **Amazon SageMaker endpoint**

Your Q119 describes deploying a real-estate prediction model **without managing servers/infrastructure**. SageMaker endpoint is the relevant concept. 

Don't confuse it with:

**EC2** → virtual servers you manage more directly
**EKS** → managed Kubernetes
**S3** → object storage
**CloudFront** → content delivery network

---

### 17. SageMaker automatic model tuning

Amazon SageMaker supports **hyperparameter tuning**.

Hyperparameters are settings controlling the learning process.

Examples might include:

* learning rate
* batch size
* regularization strength
* tree depth

SageMaker can automatically search combinations to find better-performing configurations.

Q122 directly associates **fully automated model tuning** with SageMaker. 

---

### 18. Embeddings and vector databases

Important generative-AI concept.

An **embedding** converts something such as text into a numerical vector representing semantic meaning.

For example:

`"AWS cloud computing" → [0.12, -0.48, 0.91, ...]`

Similar concepts should have vectors that are relatively close together.

This allows **semantic search**.

For example:

User asks:

`How can I change my password?`

Your knowledge base might contain:

`Steps for resetting account credentials`

The words differ, but their **meaning is similar**, so vector search can retrieve it.

Your Q110 asks about storing/querying embeddings as vectors. In that question, **Aurora PostgreSQL** is the relevant database choice because PostgreSQL can support vector capabilities.

---

### 19. AWS KMS

**AWS Key Management Service (KMS)** manages encryption keys.

Trigger words:

> encryption key
> customer-managed key
> encrypt data/model artifacts

→ think **AWS KMS**.

Q104 asks specifically for a company-managed encryption key for Bedrock customization artifacts. 

Don't confuse it with:

**Secrets Manager** → passwords/API keys/database credentials and other secrets

**Macie** → discover sensitive data, especially in S3

**Inspector** → vulnerability management

---

### 20. Amazon Macie

Think:

> **Macie = discover sensitive data in S3**

For example, customer emails stored in S3 might contain:

* names
* financial information
* credentials
* other sensitive data

Macie can automatically inspect S3 data for sensitive information.

That's the service your PDF associates with automated sensitive-information detection in uploaded S3 documents.

---

### 21. CloudWatch vs CloudTrail

This distinction is extremely important.

**Amazon CloudWatch**

> "How is my system performing?"

Think:

* metrics
* logs
* alarms
* operational monitoring
* performance

**AWS CloudTrail**

> "Who did what in AWS?"

Think:

* API activity
* auditing
* account actions
* governance/security investigations

A memory trick:

**CloudWATCH → watch performance**

**CloudTRAIL → trail of API actions**

Your PDF's Q126 asks about logging requests made to the Amazon Bedrock API; that wording should make you think **CloudTrail**. 

---

### 22. AWS Config vs Audit Manager

Also know these for governance.

**AWS Config**

Tracks and evaluates **AWS resource configurations**.

Think:

> "Are my AWS resources configured according to our rules?"

**AWS Audit Manager**

Helps collect evidence and assess controls for **audits/compliance**.

Your Q149 specifically asks which AWS services help continuously assess compliance with company policies and industry regulations, with **Audit Manager and Config** among the choices. 

---

### 23. Data residency

**Data residency** means controlling the geographical location where data is stored/processed.

Exam trigger:

> "Data cannot leave the country."

→ **Data residency**

This differs from:

**Data quality** → correctness/completeness of data

**Data discoverability** → ability to locate and understand data

**Data enrichment** → adding additional information to data

---

### 24. Amazon Personalize

Think:

> **Personalize = recommendations personalized for users**

Examples:

`Recommended products for Alan`

`Movies you may like`

`Personalized ecommerce results`

Don't confuse it with:

**Kendra** → intelligent enterprise search
**Rekognition** → image/video analysis
**Transcribe** → speech → text

---

### 25. Computer vision

Computer vision allows AI systems to understand visual information.

Examples:

* defect detection
* object detection
* image classification
* facial analysis
* manufacturing inspection

Your Q121 asks about inspecting products for damage/defects. That's **computer vision**. 

---

### 26. AI governance

AI governance is about establishing controls around how AI is built and used.

Think:

* policies
* responsible AI
* transparency
* compliance
* risk management
* data governance
* accountability

So when AWS asks what characterizes an **AI governance framework**, look for language about:

> **policies + guidelines + data + transparency + responsible AI + compliance**

rather than revenue or business-growth goals.

---

### 27. Human-in-the-loop

Human-in-the-loop means humans review, validate, or intervene in AI decisions/output.

This can be useful for:

* sensitive decisions
* harmful/toxic content
* uncertain predictions
* quality control
* responsible AI

Your Q123 specifically connects human review to reducing bias/toxicity during **post-processing**. 

---

## The high-yield cheat sheet

For this particular set, I'd memorize these associations:

| If the question says...                        | Think...                  |
| ---------------------------------------------- | ------------------------- |
| Bias + explainability                          | **SageMaker Clarify**     |
| Document model purpose/performance/limitations | **Model Cards**           |
| Foundation models on AWS                       | **Amazon Bedrock**        |
| Current/private knowledge for an FM            | **RAG / Knowledge Bases** |
| AI performs tasks/actions                      | **Bedrock Agents**        |
| Cheapest way to improve instructions/output    | **Prompt engineering**    |
| Examples included in prompt                    | **Few-shot**              |
| No examples                                    | **Zero-shot**             |
| Step-by-step reasoning                         | **Chain-of-thought**      |
| Tell image model what to avoid                 | **Negative prompt**       |
| Reduce randomness                              | **Lower temperature**     |
| Semantic text similarity                       | **BERTScore**             |
| Precision + recall                             | **F1**                    |
| Labeled training data                          | **Supervised learning**   |
| Discover groups                                | **K-means**               |
| Classify from nearby examples                  | **k-NN**                  |
| Training good, test/new data bad               | **Overfitting**           |
| Reduce model complexity                        | **Regularization**        |
| Immediate prediction                           | **Real-time inference**   |
| Large offline processing                       | **Batch inference**       |
| Managed ML deployment                          | **SageMaker endpoint**    |
| Automated hyperparameter tuning                | **SageMaker**             |
| Semantic numerical representations             | **Embeddings**            |
| Encryption keys                                | **KMS**                   |
| Sensitive data in S3                           | **Macie**                 |
| Performance/metrics/alarms                     | **CloudWatch**            |
| AWS API activity/audit trail                   | **CloudTrail**            |
| Resource configuration/compliance              | **AWS Config**            |
| Audit evidence/compliance assessment           | **Audit Manager**         |
| Data can't leave country                       | **Data residency**        |
| Personalized recommendations                   | **Amazon Personalize**    |
| Images/defects/objects                         | **Computer vision**       |

If you're studying specifically for **AIF-C01**, these associations are more useful than memorizing the wording of the questions because AWS can change the scenario while testing the same underlying concept.
