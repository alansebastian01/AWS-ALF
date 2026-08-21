### 1. ML lifecycle: prepare → train → test → deploy

The hotspot in Q351 gives four stages after the company already has its data.

The correct conceptual order is:

**Prepare the data → Train the model → Test the model → Deploy the model**

Do not deploy before evaluating the model.

Think:

> data preparation → training → evaluation/testing → production



---

### 2. Time-sensitive applications and model selection

Q352 describes an emergency system that must respond within **30 seconds**.

The key idea is that requirements such as speed, cost, and deployment constraints should guide model selection.

Among the options in this question, **model size** matters because it can influence computational requirements and response speed.

Important broader concept:

> strict response-time requirement → think **latency/inference performance**

You'll see that more explicitly later on this page.

---

### 3. Amazon Q Business application guardrails

Bedrock is not the only AWS service with guardrail-style controls.

Q353 asks how to restrict an **Amazon Q Business** assistant to company-approved topics.

→ **Amazon Q Business application guardrails**. 

Distinguish:

**Bedrock Guardrails**
→ safety controls around foundation-model applications

**Q Business application guardrails**
→ control interactions in Q Business

---

### 4. Intelligent Document Processing — IDP

Q354 asks for an IDP use case.

Think:

> **extract structured information from documents automatically**

Examples:

`scanned invoice → vendor, amount, date`

`PDF form → fields and values`

The PDF's example is automatically extracting and formatting information from scanned files. 

Don't confuse IDP with:

* fraud prediction
* recommendation systems
* sentiment analysis

---

### 5. Prompt injection

Q355 gives the textbook example:

> "Ignore all previous instructions..."

That's **prompt injection**. 

Memorize:

**Prompt injection**
→ attacker/user tries to override model instructions

**Hallucination**
→ model generates false or unsupported information

**Bias**
→ unfair/systematically skewed behavior

---

### 6. Fine-tuning = labeled task-specific data

Q356 says the company has a **high-quality labeled dataset** and wants to customize an FM.

→ **Fine-tuning**. 

This page reinforces one of the most important distinctions:

| Data/situation                               | Technique                  |
| -------------------------------------------- | -------------------------- |
| Labeled task-specific examples               | **Fine-tuning**            |
| Unlabeled domain data                        | **Continued pre-training** |
| Knowledge from external documents at runtime | **RAG**                    |

---

### 7. Customize in SageMaker, import to Bedrock

Q357 describes a foundation model that needs customization and then deployment through Amazon Bedrock.

The question's workflow is:

> **Customize in SageMaker AI → import trained model into Amazon Bedrock**



The conceptual lesson is that SageMaker provides broader model-building/customization capabilities, while Bedrock can be used to consume supported FMs and custom models.

---

### 8. Conversion rate = business impact on sales

Q358 asks whether personalized AI recommendations improve **sales revenue**.

A useful metric is:

> **Conversion rate**



For example:

`users who buy after AI recommendation / users exposed to recommendation`

This is a **business metric**, not an ML metric.

---

### 9. SageMaker governance tools

Q359 asks about approved data and compliance with organizational policy and ethical guidelines. The question includes:

* SageMaker Catalog
* Clarify
* Model Registry
* Model Cards



Know the broader mapping:

**SageMaker Catalog**
→ discover/govern approved data and AI assets

**Clarify**
→ bias/explainability

**Model Registry**
→ model lifecycle/version/approval

**Model Cards**
→ documentation/governance information

---

### 10. Bedrock Agents

Q360 says the travel assistant must:

`understand request → invoke API → complete reservation`

That's an **Amazon Bedrock Agent**. 

Exam shortcut:

> FM needs to **take actions** → Agent

> FM only needs company knowledge → Knowledge Base/RAG

---

### 11. MLOps includes continuous production monitoring

Q361 asks what must happen after deploying an ML solution.

The key MLOps practice:

> **continuously monitor production outputs**



ML systems are not:

`deploy → forget`

They are:

`deploy → monitor → detect drift/problems → improve → redeploy`

---

### 12. Custom Bedrock models and Provisioned Throughput

Q362 asks how to actually use a customized model on Amazon Bedrock.

The question associates custom-model inference with purchasing:

> **Provisioned Throughput**



Remember from earlier:

**On-demand**
→ variable/general usage

**Provisioned Throughput**
→ reserved throughput, including supported custom-model usage scenarios

---

### 13. Multimodal chatbot

Q363 says the chatbot must accept:

* text
* images

and generate responses.

That is a **multimodal generative AI** scenario, and the AWS service in the question is **Amazon Bedrock**.

Think:

> multiple input modalities + foundation models → Bedrock

---

### 14. Amazon Q Developer

Q364:

> generate code to test applications + least operational effort

→ **Amazon Q Developer**

Memory:

**Q Developer**
→ software development/coding

**Q Business**
→ enterprise/business assistant

---

### 15. Amazon Bedrock for FM selection

Q365 asks which AWS service helps users select foundation models for generative-AI applications.

→ **Amazon Bedrock**

Bedrock provides access to multiple foundation models so you can choose according to:

* modality
* performance
* latency
* cost
* customization support
* context limits

---

### 16. Fine-tuning vs continued pre-training vs distillation

The hotspot in Q366 is very high-value.

It maps:

**Labeled data for specific-task performance**
→ **Fine-tuning**

**Unlabeled data for a specific domain**
→ **Continued pre-training**

**Transfer knowledge from a larger model to a smaller model**
→ **Distillation**

This is worth memorizing exactly. 

---

### 17. Model distillation

Distillation may be newer to you.

Conceptually:

`large, powerful teacher model`

teaches

`smaller student model`

The goal is often to preserve much of the larger model's capability while reducing:

* cost
* latency
* memory usage
* compute needs

Think:

> **big model → smaller model → distillation**

---

### 18. Hallucinations as a production disadvantage

Q367 asks for a disadvantage of generative AI in production.

→ **Hallucinations and inaccuracies**. 

A fluent response is not necessarily a factual response.

This is why production systems often use:

* RAG
* guardrails
* evaluation
* monitoring
* human review

---

### 19. Bedrock vs SageMaker

Q368 asks for FMs with the **least development effort**.

The relevant AWS service is **Amazon Bedrock**. 

A useful distinction:

**Bedrock**
→ easiest managed route for building generative-AI apps using FMs

**SageMaker AI**
→ broader ML platform with deeper training/custom development capabilities

---

### 20. Amazon Neptune

Q369 says:

> graph-based ML solution + relationships/patterns in fraudulent activity

→ **Amazon Neptune**

Neptune is AWS's graph database service.

Think:

> entities + relationships + graph → Neptune

Example:

`Customer → owns → Account`

`Account → transferred to → Account`

`Account → linked to → Device`

Graph structure can help reveal fraud networks.

---

### 21. LLM-as-a-judge evaluation

Q370 introduces another model-evaluation approach:

> use an LLM to evaluate another AI response.

The question asks which built-in metric measures how thoroughly the response addresses all parts of a prompt.

→ **Completeness**

Conceptually:

**Completeness**
→ Did the answer cover everything requested?

**Following instructions**
→ Did it obey the directions?

**Refusal**
→ Did it appropriately refuse?

---

### 22. Temperature + response length

Q371 wants:

> **creative + short**

So:

**Increase temperature**
→ more creativity/diversity

**Decrease response length**
→ shorter output

This gives the combination:

> **higher temperature + lower response length**

---

### 23. SageMaker Clarify for bias

Q372 describes stereotypically gendered product recommendations.

To investigate bias:

→ **SageMaker Clarify**

Again:

> **Bias + explainability = Clarify**

---

### 24. CloudTrail

Q373 asks for a record of actions performed by AI practitioners in an AWS account.

→ **AWS CloudTrail**

Think:

> **Who did what through AWS APIs? → CloudTrail**

---

### 25. Hallucinations can include wrong numbers

Q374 says the AI creates a budget with incorrect numbers.

The question classifies this as:

> **Hallucination**

This reinforces that hallucinations aren't only invented prose.

They can include:

* wrong facts
* nonexistent citations
* fabricated numbers
* incorrect calculations stated confidently

---

### 26. CloudTrail Lake

Q375 takes CloudTrail one step further.

The company wants a:

* tamper-resistant
* queryable
* centralized record

of API calls across SageMaker, Bedrock, and IAM.

The relevant service in the question is:

> **AWS CloudTrail Lake**



Think:

**CloudTrail**
→ activity history

**CloudTrail Lake**
→ store/query/analyze CloudTrail activity at scale

---

### 27. Linear regression and explainability

Q376 asks which technique offers the **most explainability**.

Among the listed options:

> **Linear regression**



Why?

Its coefficients directly describe relationships between features and the output.

General principle:

> simpler model → usually more interpretable

> deep neural network → usually less interpretable

---

### 28. AWS PrivateLink

Q377 requires SageMaker Studio → Bedrock traffic to traverse the company's VPC.

→ **AWS PrivateLink endpoints for Bedrock**



Remember:

**IAM**
→ authorization

**PrivateLink**
→ network path/private connectivity

These solve different problems.

---

### 29. Multimodal LLM

Q378 gives a tutoring application that accepts:

* text
* picture

and produces:

* written answer
* explanation

→ **Multimodal LLM**



This repeats one of the most important multimodal patterns.

---

### 30. RAG

Q379 directly asks:

> what combines an LLM with an external knowledge base?

→ **Retrieval Augmented Generation (RAG)**. 

Again:

`user question`

→ retrieve relevant external data

→ add it to context

→ model generates grounded answer

---

### 31. SageMaker Model Monitor

Q380:

> application accuracy becomes worse over time + need alerts for drift

→ **SageMaker Model Monitor**



Memorize:

> drift/performance degradation → Model Monitor

---

### 32. Amazon Macie

Q381:

> inspect S3 before sharing and discover sensitive information

→ **Amazon Macie**



Think:

> sensitive data in S3 → Macie

---

### 33. Continued pre-training definition

Q382 gives one of the clearest definitions:

> provide **unlabeled data** to a pretrained language model to improve its **domain knowledge**



This is worth memorizing.

---

### 34. Feature engineering

Q383 asks what feature engineering actually means.

→ **create or select relevant features for training**. 

For example:

Raw data:

`date_of_birth = 1992-06-04`

Engineered feature:

`age = 34`

Another:

`purchase dates`

→

`days_since_last_purchase`

Good features can make patterns easier for the model to learn.

---

### 35. Multimodal = different data types

Q384 defines multimodal very cleanly:

> process different types such as **images, audio, and video**



It does not mean:

> multiple versions of the same model.

---

### 36. Inference latency

Q385 asks for the term describing how quickly a pretrained FM processes a request and delivers output.

→ **Inference latency**



Think:

> time between request and response → latency

---

### 37. Pre-training

Q386 says:

* huge web dataset
* randomly initialized weights
* train using a language-modeling objective

→ **Pre-training**



Pre-training is where a model learns broad language/world patterns initially.

Fine-tuning happens **after** this.

---

### 38. Core AI governance process

The hotspot in Q387 gives three governance activities:

* create a cross-functional AI governance group
* determine governance goals, risks, and policies
* set up monitoring mechanisms

The core idea is that governance is not merely a model feature.

It requires:

> **people + policies + ongoing monitoring**

A sensible governance flow is to establish responsible ownership, define risk/governance expectations, and continuously monitor the AI system.

---

### 39. Removing a feature does not automatically remove bias

Q388 is an important fairness lesson.

The training dataset is heavily concentrated in the middle-aged group. Simply deleting the explicit `age` feature does not magically create a representative dataset.

The model can still perform poorly for underrepresented groups.

The PDF asks about inaccurate outcomes for younger and older groups in this situation. 

Exam principle:

> **Fairness requires representative data, not merely removing protected attributes.**

---

### 40. Hallucination vs nondeterminism

Q389:

> generated data unrelated to the input/task

→ **Hallucination**



Q400:

> same input gives different outputs

→ **Nondeterminism**



This distinction is extremely important:

**Hallucination**
→ correctness problem

**Nondeterminism**
→ consistency problem

---

### 41. IAM

Q390 asks how to allow only authorized people to access training data.

→ **AWS Identity and Access Management (IAM)**. 

Think:

> **who is allowed to access what? → IAM**

Don't confuse:

**KMS**
→ encryption keys

**IAM**
→ access permissions

---

### 42. Dataset diversity and class representation

Q391 wants data that reflects global user diversity.

The relevant idea:

> **balanced class representation**



Bad practices would be:

* removing minorities
* oversampling the already dominant group
* using only one region

---

### 43. SageMaker Unified Studio

Q392 asks for a shared environment where different teams can:

* work with data
* build AI/ML models
* collaborate
* share generative-AI applications securely

The PDF points toward:

> **Amazon SageMaker Unified Studio**



Conceptually:

> unified collaborative data + AI development environment.

---

### 44. Denied topics with Guardrails

Q393 says the FM should not answer questions about politics.

The relevant solution:

> **Amazon Bedrock Guardrails**



This is a classic **denied-topic** scenario.

Trigger phrase:

> "The model must not discuss X"

→ think Guardrails / denied topics.

---

### 45. RAG document preparation: chunk → embedding

Q394 asks how documents become useful to a RAG knowledge system.

The relevant step:

> **create embeddings from document chunks**



Typical RAG preparation:

`document`

→ split into chunks

→ create embeddings

→ store in vector database

---

### 46. Amazon Q in QuickSight

Q395 asks for BI reports plus automatically generated executive summaries.

The relevant AWS feature is:

> **Amazon Q in QuickSight**



Think:

> business intelligence + natural-language insights/summaries → Q in QuickSight

---

### 47. Performance vs interpretability tradeoff

Q396 compares:

**decision tree**
→ more explainable

with

**neural network**
→ higher accuracy but less explainable

The tradeoff is:

> **higher performance for lower interpretability**



This is a classic responsible-AI/model-selection tradeoff.

---

### 48. Bedrock Prompt Management

Q397 wants:

* reusable common instructions
* variable product descriptions inserted each time

→ **Amazon Bedrock Prompt Management**



Think:

> reusable prompt template + variables → Prompt Management

---

### 49. Transparency improves governance

Q398 asks what increasing model transparency achieves.

The key benefit:

> easier to detect bias and improve governance.



Transparency does **not** magically:

* eliminate all bias
* eliminate audits
* eliminate validation

It makes oversight easier.

---

### 50. RLHF

Q399 introduces:

> **Reinforcement Learning from Human Feedback (RLHF)**

The company wants moderation behavior aligned with its ethics while adapting to new problematic content.

The question points toward incorporating feedback from skilled human moderators. 

Conceptually:

`model produces answer`

→ human evaluates/preferences

→ feedback becomes reward signal

→ model behavior improves

Think:

> **human preferences shape model behavior → RLHF**

---

## Page 8 high-yield cheat sheet

| Exam wording                     | Think                               |
| -------------------------------- | ----------------------------------- |
| ML lifecycle                     | **Prepare → Train → Test → Deploy** |
| Q Business approved topics       | **Q Business guardrails**           |
| Scanned document extraction      | **IDP**                             |
| "Ignore previous instructions"   | **Prompt injection**                |
| Labeled customization data       | **Fine-tuning**                     |
| Sales impact                     | **Conversion rate**                 |
| AI calls transactional APIs      | **Bedrock Agents**                  |
| Production lifecycle practice    | **Continuous monitoring**           |
| Use custom Bedrock model         | **Provisioned Throughput**          |
| Text + image chatbot             | **Multimodal / Bedrock**            |
| Coding assistant                 | **Amazon Q Developer**              |
| Labeled task data                | **Fine-tuning**                     |
| Unlabeled domain data            | **Continued pre-training**          |
| Big model → small model          | **Distillation**                    |
| Incorrect generated content      | **Hallucination**                   |
| Graph relationships              | **Amazon Neptune**                  |
| Answer covers entire question    | **Completeness**                    |
| Creative output                  | **Temperature ↑**                   |
| Short output                     | **Response length ↓**               |
| Investigate bias                 | **SageMaker Clarify**               |
| AWS user/API activity            | **CloudTrail**                      |
| Queryable API audit history      | **CloudTrail Lake**                 |
| Most explainable simple model    | **Linear regression**               |
| Private AWS networking           | **PrivateLink**                     |
| LLM + external knowledge         | **RAG**                             |
| Production drift alerts          | **Model Monitor**                   |
| Sensitive S3 data                | **Macie**                           |
| Create/select useful variables   | **Feature engineering**             |
| Response speed                   | **Inference latency**               |
| Initial huge-data training       | **Pre-training**                    |
| Authorized access                | **IAM**                             |
| Representative dataset           | **Balanced diversity**              |
| Unified data/AI environment      | **SageMaker Unified Studio**        |
| Block a topic                    | **Bedrock Guardrails**              |
| RAG preparation                  | **Chunks + embeddings**             |
| BI executive summaries           | **Amazon Q in QuickSight**          |
| Accuracy up, explanation down    | **Performance vs interpretability** |
| Reusable prompt templates        | **Prompt Management**               |
| Human preferences train behavior | **RLHF**                            |
| Same prompt, different answer    | **Nondeterminism**                  |

The **seven distinctions I'd memorize from this page** are:

**Fine-tuning vs continued pre-training vs distillation:**
Fine-tuning = **labeled task data**.
Continued pre-training = **unlabeled domain data**.
Distillation = **large model teaches smaller model**.

**Hallucination vs nondeterminism:**
Hallucination = **wrong/unrelated output**.
Nondeterminism = **different output for same input**.

**IAM vs KMS vs PrivateLink:**
IAM = **who can access**.
KMS = **encryption keys**.
PrivateLink = **private network connectivity**.

**CloudTrail vs CloudTrail Lake:**
CloudTrail = **AWS API activity history**.
CloudTrail Lake = **query/analyze retained activity records**.

**Agents vs RAG:**
Agent = **perform actions/call APIs**.
RAG = **retrieve knowledge to improve answers**.

**Clarify vs Model Monitor:**
Clarify = **bias/explainability**.
Model Monitor = **production drift**.

**Feature engineering vs pre-training:**
Feature engineering = **create/select useful input variables**.
Pre-training = **initial large-scale model training**.
