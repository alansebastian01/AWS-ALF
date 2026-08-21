
### 1. Multimodal models

A **multimodal model** can work with more than one type of input or output, such as:

* text
* images
* audio
* video

Q201 describes an application where the user can enter either **text or a picture**, and the application gives a written answer. That is a **large multimodal language model** use case. 

Think:

> text + image together → multimodal model

---

### 2. Generative AI lifecycle: evaluation

The lifecycle includes stages such as:

**data selection → pre-training → fine-tuning → evaluation → deployment**

The **evaluation** stage is where you test how well the model performs.

Q202 explicitly asks which stage examines model accuracy: **evaluation**. 

Exam shortcut:

> "Test accuracy/performance" → **Evaluation**

---

### 3. Embeddings

This page reinforces embeddings heavily.

An embedding represents information as a **high-dimensional numeric vector** that captures semantic meaning.

For example:

`"car" → [0.23, -0.11, 0.89, ...]`

`"automobile" → [0.21, -0.10, 0.86, ...]`

Those vectors should be mathematically close because the concepts are similar.

Q203 defines embeddings as high-dimensional vectors that capture semantic relationships. 

Important distinction:

**Embedding**
→ vector representation

**Vector database**
→ stores/searches those vectors

**RAG**
→ uses retrieval, often based on those vectors

---

### 4. Text embedding models

If you specifically need to convert text into vectors, use a **text embeddings model**.

Q215 asks which type of FM converts private text into a vector representation before storage. That's the text embeddings model concept. 

Think:

> text → numbers/vector → embeddings model

---

### 5. Temperature

Temperature controls the **randomness/creativity** of model output.

General pattern:

**temperature ↓**
→ more stable
→ more deterministic
→ less creative

**temperature ↑**
→ more varied
→ more creative
→ less predictable

Q204 wants responses to be as stable and deterministic as possible, so the relevant idea is setting **temperature to 0**.

Q224 asks for more creative/diverse outputs, so increase temperature. 

Memorize:

> **Low temperature = predictable**

> **High temperature = creative**

---

### 6. Top K

Top K controls **how many possible next tokens the model considers**.

Suppose the next-token probabilities are:

`the = 35%`
`a = 20%`
`this = 15%`
`one = 10%`
etc.

If:

`Top K = 3`

the model only considers the top three candidate tokens.

Q214 asks exactly this definition. 

Don't confuse:

**Temperature**
→ randomness among choices

**Top K**
→ number of candidate tokens considered

**Maximum tokens**
→ how long the generated response may be

---

### 7. Inference speed

**Inference** means using a trained model to generate a prediction or output.

If your application must respond in **real time**, model **inference speed / latency** matters.

So:

> user is waiting for an answer → inference speed matters

Training time matters before deployment, but it does not determine how quickly users get responses afterward.

---

### 8. What is inference?

Training:

`historical examples → model learns`

Inference:

`new input → trained model → prediction`

For example:

Historical patient data trains a readmission model.

Then a new patient arrives.

The trained model predicts:

`78% chance of readmission`

That prediction is **inference**.

Q247 uses exactly that distinction: using a trained model to predict patient readmission. 

---

### 9. Batch inference

Batch inference is appropriate when predictions can be processed together at scheduled intervals.

Example:

`Every midnight → process yesterday's 5 million records`

Q210 has gigabytes of data and asks for predictions **once each day**. That is **batch inference**. 

Think:

> scheduled bulk predictions → batch

> immediate user response → real-time

---

### 10. Prompt

A **prompt** is simply the instruction/input sent to the foundation model.

Example:

`Summarize this document in three bullet points.`

That entire instruction is the prompt.

AIF-C01 questions may make this sound more complicated than it is.

---

### 11. Few-shot vs one-shot vs zero-shot

These are worth knowing precisely.

**Zero-shot**

No examples.

`Classify this review as positive or negative.`

**One-shot**

Give **one example**.

`Great product → Positive`

then ask for a new prediction.

**Few-shot**

Give **several examples**.

Q216 says the company will give the LLM example product descriptions following a format. That's the general **few-shot prompting** idea. 

Exam pattern:

> several examples → few-shot

> one example → one-shot

> no examples → zero-shot

---

### 12. ReAct prompting

**ReAct = Reasoning + Acting**

The model doesn't just think about the answer; it can also interact with external tools/systems and use the results.

Conceptually:

`Question: Where is cereal?`

Model reasoning:

`I need current inventory information.`

Action:

`Query inventory system`

Observation:

`Cereal: aisle 7`

Answer:

`Cereal is in aisle 7.`

Q218 asks for a chatbot that must **check inventory in real time** and then tell the customer where the product is. That's the ReAct idea. 

Think:

> Reason + use a tool/API + respond → **ReAct**

---

### 13. RAG

Again, a major AIF-C01 topic.

RAG lets an FM answer using external/private/current information.

Typical architecture:

`documents → chunks → embeddings → vector database`

At query time:

`question → retrieve relevant chunks → provide them to LLM → generate answer`

Q231 describes an HR chatbot with a large documentation base. That points toward RAG. 

---

### 14. Bedrock Knowledge Bases

Amazon Bedrock Knowledge Bases help implement RAG.

If a company already has a foundation model but wants it to answer using **company information**, Knowledge Bases are often the straightforward answer.

Q228 says the company wants to add company context to a pretrained FM **most cost-effectively** → Bedrock Knowledge Bases.

So think:

> company documents + Bedrock + context → **Knowledge Bases / RAG**

---

### 15. Frequently changing data → RAG

This keeps appearing because it matters.

Q243 says company policies are updated frequently and answers must reflect changes **near real time**.

That is exactly the scenario where RAG is better than repeatedly fine-tuning the model.

The PDF specifically includes a **Bedrock Knowledge Bases RAG workflow** among the options. 

Concept:

> changing knowledge → retrieve it

> don't constantly retrain the model

---

### 16. RAG vs fine-tuning

This is probably the most important distinction across all these pages.

**RAG**

Changes what the model **knows at inference time** by providing external context.

Use for:

* HR policies
* inventory
* product manuals
* current company data
* frequently changing knowledge

**Fine-tuning**

Changes how the model **behaves/performs**.

Use for:

* desired tone
* task specialization
* formatting
* industry-specific behavior

Quick memory:

> **Knowledge problem → RAG**

> **Behavior problem → fine-tuning**

---

### 17. Fine-tuning training data

For supervised fine-tuning, you normally need examples pairing:

**input → desired output**

For example:

`Input: Rewrite this customer message professionally.`

`Output: Thank you for contacting...`

Q246 asks what data is needed to fine-tune a model's output style: **pairs of input and output messages**. 

---

### 18. Fine-tuning lifecycle

Q244 describes:

> supervised learning + small labeled dataset + target-specific task

That corresponds to **fine-tuning**. 

Again:

**Pre-training**
→ huge general dataset

**Fine-tuning**
→ smaller task-specific labeled data

---

### 19. Personally identifiable information (PII)

If sensitive personal data is present in training data, a strong privacy strategy is to **remove PII before training/fine-tuning**.

Examples of PII:

* names
* account identifiers
* addresses
* phone numbers
* email addresses

Q217 specifically describes preventing private customer data from leaking after fine-tuning. The concept being tested is removing PII before training. 

Encryption protects stored/transmitted data, but it doesn't prevent a model from learning sensitive text that you intentionally fed into training.

---

### 20. Bedrock data privacy

Q219 tests an important Bedrock privacy idea:

The prompt inputs and model outputs aren't passed to third-party model providers for their own use.

The question frames this around confidential-document analysis with a third-party FM. 

For the exam, associate Bedrock with managed access to FMs while preserving customer data isolation/privacy controls.

---

### 21. IAM and model access

**AWS Identity and Access Management (IAM)** controls who can access AWS resources and what actions they can perform.

Q212 asks how to restrict employees to specific models in Amazon Bedrock.

The key concept:

> **Access permissions → IAM policies**



Think:

**IAM**
→ who can do what

**STS**
→ temporary credentials

**Inspector**
→ vulnerability management

---

### 22. Supervised vs unsupervised

Again:

**Supervised**
→ labeled outputs

Q213 explicitly defines supervised learning as using training data labeled with the correct output values. 

Example:

`transaction → fraud`

`transaction → not fraud`

**Unsupervised**
→ no target labels

Used to find hidden patterns/groups.

---

### 23. Clustering

If you want to **group similar things automatically**, think clustering.

Q221 says:

> group customers based on purchase history and preferences

That's a clustering problem. 

Clustering is usually:

> **unsupervised learning**

Q238 reinforces that: automatically grouping similar customers/products corresponds to unsupervised learning. 

---

### 24. Classification metrics

This page reinforces several metrics.

#### Accuracy

Accuracy means:

`correct predictions / all predictions`

Q209 defines exactly this ratio. 

#### F1 score

F1 balances:

**precision + recall**

Useful for binary classification, especially when class balance or both false positives and false negatives matter.

Q208 and Q227 both connect churn prediction with F1.  

#### RMSE/MSE

These are mainly for **regression/numeric predictions**, not standard binary classification.

---

### 25. BLEU

BLEU is strongly associated with **machine translation evaluation**.

The basic idea is to compare machine-generated translation against reference/human translation.

Q223 explicitly compares translation-tool responses with human responses and offers BLEU as the translation-quality metric. 

Memory trick:

> **BLEU → translation**

---

### 26. BERTScore

BERTScore evaluates **semantic similarity**.

That means it cares more about whether the meaning is similar than whether every exact word matches.

This is useful when different wording can still convey essentially the same information.

Your Q232 asks about evaluating whether a chatbot captures a desired language style and includes BERTScore among the metrics. 

---

### 27. Responsible data collection

Bias can start with the dataset.

Q207 asks how to decrease model bias during collection.

The concept:

> gather **balanced, diverse, representative data**

If one group is missing or underrepresented, the model may perform poorly or unfairly for that population.

---

### 28. Dataset diversity

Q230 explicitly names this characteristic.

If you want all demographics represented:

> **dataset diversity**

Balanced representation can help reduce demographic bias.

---

### 29. Fairness and transparency

Q226 asks which responsible-AI dimensions matter in hiring.

Two high-value concepts:

**Fairness**
→ equitable outcomes/treatment

**Transparency**
→ information about how AI works and makes decisions



For hiring, lending, healthcare, and similar high-impact settings, AWS exam questions frequently emphasize fairness.

---

### 30. SageMaker Clarify

Q211 asks about **bias and drift** in a production model and lists Clarify among the choices. 

Remember the broader distinction:

**Clarify**
→ bias + explainability

**Model Monitor**
→ production quality/drift monitoring

**Model Cards**
→ documentation

The exact wording in questions determines which one AWS wants.

---

### 31. Shapley values / SHAP

This page introduces a very important explainability concept.

**Shapley values** estimate how much each feature contributed to a model prediction.

Example:

Loan denied because:

`Debt-to-income ratio: -40% contribution`

`Credit history: -30%`

`Income: +10%`

This helps explain **why** a prediction occurred.

Q237 specifically says presenting Shapley values provides transparency and explainability. 

Think:

> **SHAP / Shapley values → feature contribution → explainability**

---

### 32. SageMaker Ground Truth

**SageMaker Ground Truth** is for **data labeling**.

Examples:

* label images
* classify objects
* label text
* create training datasets

Q225 asks for a user-friendly interface for labeling computer-vision data → SageMaker Ground Truth. 

Think:

> Need labels → **Ground Truth**

---

### 33. SageMaker Model Registry

Model Registry helps:

* store models
* manage models
* version models
* track approval status
* support model lifecycle workflows

Q236 explicitly asks for storing, managing, and versioning ML models → **SageMaker Model Registry**.

Also, the hotspot on page 9 visually contrasts:

**Model Registry**
→ manage versions

**Serverless Inference**
→ make predictions

---

### 34. SageMaker Serverless Inference

Serverless inference lets you deploy a model for inference without managing the underlying serving infrastructure.

Useful when traffic may be intermittent or unpredictable.

Conceptually:

`request arrives → infrastructure handles inference → you pay/use managed capacity`

No need to provision and continuously manage servers yourself.

---

### 35. Amazon SageMaker Canvas

Q250 introduces another easy AWS-service association:

> **SageMaker Canvas = build ML models without writing code**



Think:

**Canvas**
→ no-code ML

**Ground Truth**
→ data labeling

**Model Registry**
→ model versions

**Model Monitor**
→ production monitoring

---

### 36. Amazon Q Business

Amazon Q Business is designed for enterprise AI assistance over organizational information.

Q249 asks for an AI assistant that lets employees query **internal data** → Amazon Q Business. 

Think:

> Employee AI assistant + enterprise/internal knowledge → **Amazon Q Business**

---

### 37. Amazon Transcribe

For subtitles, you need to convert spoken audio into text.

So:

> **audio → subtitles/transcript = Amazon Transcribe**

Q220 directly tests this mapping. 

For multilingual subtitles, a common workflow is:

`audio → Transcribe → text → Translate`

---

### 38. Amazon Polly

Polly does the reverse:

> **text → speech**

For multilingual voice-over:

translated text → Polly-generated speech.

The PDF's filmmaker scenario combines **Transcribe + Translate** for subtitles and **Polly** for voice-over.

---

### 39. Amazon Translate

Translate converts text from one language to another.

Q239 asks about publishing English articles in other languages → **Amazon Translate**. 

Again memorize:

**Transcribe** → speech → text
**Translate** → language → language
**Polly** → text → speech

---

### 40. Private connectivity with AWS PrivateLink

Q241 asks about sensitive data inside a VPC that must stay on the company's private network.

The key concept:

> **AWS PrivateLink** provides private connectivity between a VPC and supported AWS services.

This avoids requiring public-internet paths for the service connection.

---

### 41. Amazon Augmented AI — A2I

Amazon A2I provides **human review workflows for ML predictions**.

Q248 says the company wants:

* human review
* confidence thresholds
* ability to adjust thresholds

That's exactly the A2I concept. 

Think:

> ML uncertain → send to human reviewer → **Amazon A2I**

---

### 42. Diffusion vs transformer vs object detection

The hotspot on page 11 compares model types for advertising tasks.

Conceptually:

**Diffusion model**
→ generate images

**Transformer-based model**
→ generate/contextualize text such as slogans

**Object detection model**
→ find/verify objects or brand elements inside images

That's a useful general mapping.

---

### 43. Hallucinations and Guardrails

A hallucination is when a generative model provides information that sounds plausible but is unsupported or incorrect.

The PDF's Q234 associates factual-response safeguards with **Amazon Bedrock Guardrails**.

For exam purposes, Guardrails are about controlling/assessing model inputs and outputs.

Be careful with the wording: guardrails can reduce or filter undesirable output, but generative AI generally cannot be guaranteed to literally **never** hallucinate.

---

## Page 5 high-yield cheat sheet

| Exam wording                     | Think                         |
| -------------------------------- | ----------------------------- |
| Image + text input               | **Multimodal model**          |
| Test model accuracy              | **Evaluation**                |
| Semantic vector representation   | **Embeddings**                |
| Convert text to vector           | **Text embeddings model**     |
| Stable/deterministic output      | **Temperature ↓ / 0**         |
| Creative/diverse output          | **Temperature ↑**             |
| Number of candidate next tokens  | **Top K**                     |
| Fast user-facing predictions     | **Inference speed**           |
| Use trained model for prediction | **Inference**                 |
| Process predictions once daily   | **Batch inference**           |
| Multiple examples in prompt      | **Few-shot**                  |
| Reason and use external tool     | **ReAct**                     |
| Current company knowledge        | **RAG**                       |
| Bedrock RAG                      | **Knowledge Bases**           |
| Changing policies/data           | **RAG**                       |
| Change model behavior/style      | **Fine-tuning**               |
| Fine-tuning examples             | **Input-output pairs**        |
| Sensitive training data          | **Remove PII**                |
| Control AWS access               | **IAM policies**              |
| Labeled training data            | **Supervised learning**       |
| Group similar users/items        | **Clustering / unsupervised** |
| Correct / total                  | **Accuracy**                  |
| Classification balance           | **F1**                        |
| Translation quality              | **BLEU**                      |
| Diverse demographic data         | **Fairness / diversity**      |
| Feature contribution             | **Shapley values**            |
| Label datasets                   | **SageMaker Ground Truth**    |
| Store/version models             | **Model Registry**            |
| No-code ML                       | **SageMaker Canvas**          |
| Employee internal-data assistant | **Amazon Q Business**         |
| Audio → text                     | **Transcribe**                |
| Text → speech                    | **Polly**                     |
| Text language translation        | **Translate**                 |
| Private VPC connection           | **PrivateLink**               |
| Human review workflow            | **Amazon A2I**                |

The **five distinctions I'd memorize immediately from this page** are:

**Temperature vs Top K:**
Temperature = **randomness**.
Top K = **how many token candidates are considered**.

**RAG vs fine-tuning:**
RAG = **give the model current knowledge**.
Fine-tuning = **change model behavior**.

**Ground Truth vs A2I:**
Ground Truth = humans **label training data**.
A2I = humans **review model predictions**.

**Model Registry vs Model Monitor:**
Registry = **store/version models**.
Monitor = **watch production models**.

**Transcribe vs Translate vs Polly:**
Transcribe = **speech → text**.
Translate = **text language → another language**.
Polly = **text → speech**.
