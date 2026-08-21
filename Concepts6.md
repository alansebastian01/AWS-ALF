### 1. Image generation: generation steps

For image-generation models, the **generation step** controls how many refinement steps the model uses while producing the image.

Generally:

* more generation steps → potentially more refined/detail-oriented result
* fewer steps → faster, potentially less detailed

Q251 asks which parameter controls how detailed or abstract an image appears, and the relevant concept is **generation step**. 

Don't confuse this with:

**Batch size** → how many items are processed together
**Token length** → text token limits
**Checkpoint** → saved model state/version

---

### 2. AWS PrivateLink

PrivateLink is extremely testable.

Think:

> **AWS service access without traffic traversing the public internet**

Q252 says API calls between generative AI applications and foundation models must not travel over the public internet → **AWS PrivateLink**. 

Q278 reinforces the exact same concept for private access between a VPC and Amazon Bedrock.

Memory:

> private VPC → AWS service → **PrivateLink**

---

### 3. Bedrock Guardrails

Again:

> **Guardrails = control/filter generative AI inputs and outputs**

Q253 specifically wants to filter harmful content from both user prompts and chatbot responses → **Amazon Bedrock Guardrails**. 

Typical Guardrails use cases:

* harmful content
* unwanted topics
* sensitive information
* content safety
* responsible AI policies

---

### 4. Amazon Bedrock PartyRock

PartyRock is designed as an easy environment to **experiment with generative AI applications**.

Q254 asks for a cost-effective experimental environment to learn about generative AI → **Amazon Bedrock PartyRock**.

Think:

> experiment / learn / prototype GenAI → **PartyRock**

Don't confuse it with:

**Q Developer** → developer/coding assistance

**Q Business** → enterprise assistant over business information

**SageMaker JumpStart** → pretrained ML/FMs and solutions

---

### 5. Training data should match the task/domain

If you're training an AI assistant for a specific content area, your training dataset should contain **relevant, representative examples from that domain**.

Q255 wants an assistant for a specific content area, so diverse conversations containing the relevant terminology are the logical dataset.

General principle:

> Good training data is **relevant + representative + diverse**

---

### 6. Fairness starts with data

Q256 asks how to make a loan-approval AI system responsible and fair.

The important concept is:

> inspect the training data for bias and include diverse demographics.

Responsible AI isn't achieved by merely using a deeper neural network.

Fairness problems often originate in:

* missing populations
* historical bias
* class imbalance
* poor sampling

---

### 7. SageMaker Ground Truth vs Guardrails vs Clarify

The hotspot on page 3 reinforces three very important mappings:

**SageMaker Ground Truth**
→ human feedback/data labeling

**Bedrock Guardrails**
→ safeguards aligned with responsible-AI policies

**SageMaker Clarify**
→ detect bias / explain predictions

The visual explicitly places these three capabilities against human feedback, safeguards, and bias detection. 

Memorize:

> label data → **Ground Truth**

> detect bias → **Clarify**

> block harmful GenAI content → **Guardrails**

---

### 8. SageMaker Canvas

Q258:

> minimal ML experience + predict something + no coding

→ **SageMaker Canvas**

Canvas provides a visual/no-code ML experience.

Think:

> **No-code ML → Canvas**

---

### 9. Responsible AI training

If an organization wants developers to build fair and explainable AI systems, teams need awareness of:

* bias
* fairness
* explainability
* responsible AI principles

Q259 directly asks this and points toward **bias awareness and responsible AI training**. 

---

### 10. Interpretability

**Model interpretability** means understanding how or why a model makes predictions.

Q260 defines it directly. 

Example:

A model rejects a loan.

Interpretability asks:

> Which factors caused the rejection?

Related terms:

**Explainability**
→ ability to communicate why a prediction happened

**Interpretability**
→ ability to understand model behavior

For AIF-C01, they are closely related.

---

### 11. K-means clustering

Q261 asks how to identify customer groups based on demographics and buying patterns.

That is a classic **K-means** clustering use case. 

Recall:

**K-means**
→ unsupervised clustering

**k-NN**
→ predicts using nearby labeled examples

---

### 12. Temperature

Again:

> **Temperature controls diversity/randomness**

Q262 says the outputs aren't diverse enough → adjust **temperature**. 

Higher temperature:

* more varied
* more creative
* less predictable

Lower temperature:

* more consistent
* more deterministic

---

### 13. Negative prompting

Q263 uses Amazon Nova Canvas and asks how to prevent certain objects from appearing.

Answer concept:

> **Negative prompt**

Example:

`Create a city skyline. No cars, no people, no text.`

A negative prompt tells the image model what to **avoid**.

---

### 14. Binary classification vs multiclass vs regression

The hotspot on page 5 gives very clean examples.

**Binary classification**

Two categories.

`answer correct / incorrect`

**Multiclass classification**

More than two categories.

`car model A / B / C / D`

**Regression**

Predict numeric quantities.

`number of species in an area`

So memorize:

> 2 categories → binary classification

> 3+ categories → multiclass classification

> number → regression

---

### 15. SageMaker Ground Truth Plus

Q265 asks for labeling training datasets using human feedback while the company does **not** want to build labeling apps or manage the workforce.

That's **SageMaker Ground Truth Plus**. 

Difference:

**Ground Truth**
→ data-labeling capability/workflows

**Ground Truth Plus**
→ more managed labeling service, including workforce/operations

---

### 16. Amazon OpenSearch Service for vectors

OpenSearch supports vector search and nearest-neighbor similarity queries.

Q266 asks for:

* vector database
* similarity search
* nearest-neighbor queries

→ **Amazon OpenSearch Service**. 

Think:

> embeddings + vector search → OpenSearch

---

### 17. SageMaker Data Wrangler

The hotspot on page 6 introduces this clearly.

**Data Wrangler**
→ prepare, transform, and analyze data through low-code/no-code tools

So:

> prepare data visually → **Data Wrangler**

Meanwhile:

**Clarify**
→ bias

**Model Cards**
→ model documentation

The visual explicitly contrasts those three. 

---

### 18. Continued pre-training

Q268 says the company wants to customize an FM using **internal documents**.

The option the PDF associates with this is **continued pre-training**. 

Conceptually:

> continued pre-training = expose the FM to more domain-specific usually unlabeled text

Use this to deepen domain knowledge.

Remember:

**Fine-tuning**
→ behavior/task specialization

**Continued pre-training**
→ domain knowledge

---

### 19. Model drift → retrain with fresh data

Q269 says SageMaker Model Monitor detects data drift beyond a threshold.

What should you do?

> Retrain the model with fresh data.



Why?

The original training distribution no longer matches reality.

Example:

`2023 buying patterns ≠ 2026 buying patterns`

The model needs newer data.

---

### 20. Model Monitor

Q271 reinforces:

> production model quality degrades → retrain + monitor drift with SageMaker Model Monitor



Think:

**Clarify**
→ bias/explainability

**Model Monitor**
→ production drift/performance

---

### 21. Explainable AI

Q270 asks how to make credit-limit decisions more transparent.

The key idea:

> show users which factors influenced the model's decision.



Examples:

`income contributed +20%`

`debt ratio contributed -35%`

`payment history contributed +15%`

That is explainable AI.

---

### 22. Unsupervised learning

Q272 and Q284 both reinforce the same concept:

> grouping unlabeled data based on similarity = **unsupervised learning**

 

Examples:

* customer clustering
* anomaly discovery
* segmentation

---

### 23. ROUGE

Q273 asks for a metric to evaluate text summarization.

The expected metric is:

> **ROUGE**



Memory:

**ROUGE**
→ summarization

**BLEU**
→ commonly translation

**F1**
→ classification

**MSE**
→ regression

---

### 24. Human model evaluation in Amazon Bedrock

Q274 says scientists will manually assess outputs from several generative AI models.

The relevant capability is:

> **Amazon Bedrock model evaluation**



This reinforces that model evaluation can involve human judgment, especially for things difficult to measure with a simple automated metric.

---

### 25. Business metrics: CTR, AOV, retention

The hotspot on page 9 introduces business metrics rather than ML metrics.

**Click-through rate (CTR)**
→ how many people click recommendations

Measures **engagement**

**Average order value (AOV)**
→ average dollar/value amount per purchase

Measures purchasing value

**Retention rate**
→ whether users keep returning

Measures long-term engagement/loyalty

This matters because AWS may ask:

> Did the AI model actually improve the business?

not only:

> Is the model mathematically accurate?

---

### 26. SageMaker Clarify for prediction explanations

Q276 says stakeholders need explanations of model predictions.

→ **SageMaker Clarify**. 

Again:

> Bias + explainability → Clarify

---

### 27. Sentiment analysis = NLP

Q277:

> sentiment analysis is part of **Natural Language Processing (NLP)**.



Because sentiment is extracted from language/text.

Examples:

`I love this product`
→ positive

`It's terrible`
→ negative

`It's okay`
→ neutral

---

### 28. Unstructured text + sentiment

Q279 asks how to analyze large amounts of unstructured user feedback.

The core AI field is:

> **NLP / language models**

Sentiment analysis is a text-understanding problem.

---

### 29. Zero-shot vs few-shot vs RAG

The page 10 hotspot gives a useful comparison.

**RAG**
→ enhance LLM with external sources

**Zero-shot**
→ ask a model to perform an unseen task without examples

**Few-shot**
→ give a limited number of examples

The visual explicitly compares these use cases.

High-yield:

> external source → RAG

> no examples → zero-shot

> a few examples → few-shot

---

### 30. Modality

Q281 asks which FM characteristic describes the model's output types.

That's **modality**. 

Examples of modalities:

* text
* images
* audio
* video

A multimodal model may handle multiple modalities.

---

### 31. Sentiment as classification

Q282 asks whether reviews are:

* neutral
* positive
* negative

That's a **classification** problem. 

Because the output is one of a predefined set of categories.

---

### 32. AI vs ML vs deep learning

The hotspot on page 11 tests the hierarchy:

**Artificial Intelligence**
→ broadest field, machines simulating intelligent behavior

**Machine Learning**
→ systems learn patterns from data

**Deep Learning**
→ subset of ML using complex multilayer neural networks

Conceptually:

`AI`
contains
`ML`
contains
`Deep Learning`

Think:

> all deep learning is ML, but not all ML is deep learning.

---

### 33. Amazon Kendra

Q285 asks about **enterprise search** across large volumes of documents.

→ **Amazon Kendra**. 

Memory:

**Kendra**
→ enterprise intelligent search

**Comprehend**
→ NLP analysis

**Textract**
→ extract text/forms/tables from documents

**Personalize**
→ recommendations

---

### 34. Amazon Nova Reel

Q286 asks for a model that can directly generate video in the most operationally efficient way.

The PDF points to:

> **Amazon Nova Reel**



Mappings:

**Nova Canvas**
→ images

**Nova Reel**
→ video

---

### 35. F1 with imbalanced classes

Q287 says some classes contain many more examples than others.

The company wants a metric that balances detecting and correctly labeling classes.

→ **F1 score**. 

F1 combines:

`precision + recall`

This is especially useful when accuracy could be misleading due to class imbalance.

---

### 36. Data labeling

Q288 says the company adds labels such as:

`personal`

or

`business`

to transaction records.

That's **data labeling**. 

Don't confuse:

**Labeling**
→ assign target/category

**Encoding**
→ convert data into numeric/machine-readable representation

**Normalization**
→ scale values

**Balancing**
→ adjust class distribution

---

### 37. Summarization

Q289:

> extract key insights from large policy documents

→ **summarization**. 

This is a classic generative AI use case.

---

### 38. Feature influence → SageMaker Clarify

Q290 asks how to show the influence of input features on model behavior.

Again:

> **SageMaker Clarify**



Think SHAP/Shapley-value-style explanations.

---

### 39. Data types

The hotspot on page 14 is very useful.

It maps:

**Social media sentiment**
→ text data

**Traffic sign recognition**
→ image data

**Customer demographics + purchase history**
→ tabular data

**Historical stock prices**
→ time-series data



This is worth memorizing.

---

### 40. Time-series data

Q292 describes internet speeds measured repeatedly throughout each day and used to predict future disruptions.

That's **time-series data**. 

Time series:

> measurements associated with time/order.

Examples:

* hourly stock prices
* daily sales
* temperature every minute
* network latency over time

---

### 41. Autoencoders and anomaly detection

Q293 asks for detecting unusual patterns in sensor data **without labeled training data**.

The relevant technique is:

> **Autoencoder**



The concept:

An autoencoder learns the normal structure of data.

If new input is very different from what it learned, reconstruction error can be high.

That makes autoencoders useful for **anomaly detection**.

---

### 42. Conversion rate

Q294 asks for the **direct impact of an AI shopping assistant on sales**.

The correct kind of metric is:

> customers who purchase after interacting with the assistant → **conversion rate**



This is a business KPI, not an ML accuracy metric.

---

### 43. OpenSearch for Bedrock/RAG vector storage

Q295 and Q297 both reinforce:

> vector database / embeddings / similarity search → **Amazon OpenSearch Service**

 

This is a very high-yield association.

---

### 44. Practical generative AI use case

Q296 asks which scenario is actually generative AI.

A chatbot generating **human-like responses** is generative AI. 

Compare:

**Forecast product demand**
→ predictive ML

**Traffic dashboard**
→ analytics

**Rule-based recommendation**
→ deterministic rules

**Generate conversational answer**
→ generative AI

---

### 45. Amazon Personalize

Q298:

> recommend movies from user history

→ **Amazon Personalize**. 

Think:

> personalized recommendations → Personalize

---

### 46. SageMaker Model Cards

Q299 asks for a transparent, explainable loan model whose decision-making process must be documented for audits.

→ **SageMaker Model Card**. 

Model Cards document things like:

* model purpose
* performance
* limitations
* intended use
* governance information

---

### 47. Context window vs latency vs concurrency

The final hotspot on page 17 is especially valuable.

**Context window**
→ amount of information that fits in a single prompt

**Latency**
→ how long it takes the model to return output

**Concurrency**
→ multiple users invoking an endpoint simultaneously

The page 17 visual maps these definitions directly. 

Memorize:

> prompt size → context window

> response time → latency

> simultaneous users → concurrency

---

## Page 6 high-yield cheat sheet

| Exam wording                        | Think                                |
| ----------------------------------- | ------------------------------------ |
| More image refinement/detail        | **Generation steps**                 |
| Don't traverse public internet      | **AWS PrivateLink**                  |
| Filter harmful GenAI inputs/outputs | **Bedrock Guardrails**               |
| Experiment with GenAI               | **PartyRock**                        |
| Fair training data                  | **Diverse/representative data**      |
| Human labeling                      | **Ground Truth / Ground Truth Plus** |
| No-code ML                          | **SageMaker Canvas**                 |
| Understand prediction               | **Interpretability**                 |
| Group similar customers             | **K-means**                          |
| More diverse LLM output             | **Increase temperature**             |
| Exclude image elements              | **Negative prompt**                  |
| 2 categories                        | **Binary classification**            |
| Many categories                     | **Multiclass classification**        |
| Numeric prediction                  | **Regression**                       |
| Vector similarity search            | **OpenSearch**                       |
| Prepare data visually               | **Data Wrangler**                    |
| Domain knowledge from documents     | **Continued pre-training**           |
| Production drift                    | **Model Monitor**                    |
| Fix drift                           | **Retrain with fresh data**          |
| Explain feature influence           | **Clarify / explainable AI**         |
| Summary quality                     | **ROUGE**                            |
| User clicks                         | **CTR**                              |
| Purchase value                      | **AOV**                              |
| Users return                        | **Retention rate**                   |
| Sentiment                           | **NLP / classification**             |
| External knowledge                  | **RAG**                              |
| Output type                         | **Modality**                         |
| Enterprise search                   | **Amazon Kendra**                    |
| Generate video                      | **Nova Reel**                        |
| Imbalanced-class metric             | **F1**                               |
| Assign categories to records        | **Data labeling**                    |
| Long-document insights              | **Summarization**                    |
| Time-ordered measurements           | **Time-series data**                 |
| Unlabeled anomaly detection         | **Autoencoder**                      |
| Sales effect                        | **Conversion rate**                  |
| Recommendations                     | **Amazon Personalize**               |
| Audit/model documentation           | **Model Cards**                      |
| Prompt capacity                     | **Context window**                   |
| Response time                       | **Latency**                          |
| Simultaneous requests               | **Concurrency**                      |

The **six distinctions I'd memorize from this page** are:

**Clarify vs Model Monitor:**
Clarify = **bias/explainability**.
Model Monitor = **production drift**.

**Ground Truth vs Ground Truth Plus:**
Ground Truth = **labeling workflows**.
Ground Truth Plus = **more fully managed labeling**.

**RAG vs continued pre-training:**
RAG = **retrieve external knowledge at inference time**.
Continued pre-training = **teach the model more domain knowledge through additional training**.

**Binary vs multiclass vs regression:**
2 labels = **binary**.
3+ labels = **multiclass**.
Number = **regression**.

**Context window vs latency vs concurrency:**
Context window = **how much fits**.
Latency = **how long it takes**.
Concurrency = **how many simultaneous users**.

**OpenSearch vs Kendra:**
OpenSearch = **vector/search infrastructure**.
Kendra = **enterprise document search**.
