The two concepts here are **SageMaker Clarify for explainability** and **secure API access to deployed ML models**. 

### 1. SageMaker Clarify = explainability and bias

Q451 describes a social-media friend recommendation system. The company wants the model to be:

> **transparent and explainable**

The relevant service is:

> **Amazon SageMaker Clarify**

The question explicitly contrasts Clarify with Rekognition, Personalize, and Ground Truth. 

The key association to memorize is:

> **Bias + explainability → SageMaker Clarify**

Clarify helps you understand **why a model made a prediction** and can also help analyze bias.

For example, imagine a friend recommendation model says:

`Recommend User B to User A`

Clarify can help explain which features influenced that recommendation, such as:

* mutual connections
* similar interests
* shared groups
* interaction history

The general responsible-AI goal is that stakeholders should be able to understand the factors influencing a model's output.

---

### 2. Clarify vs Ground Truth

Q451 includes **SageMaker Ground Truth** as a distractor, so know this distinction instantly.

**SageMaker Clarify**
→ model **bias + explainability**

**SageMaker Ground Truth**
→ **label training data**

Think:

> "Why did the model decide this?" → **Clarify**

> "I need humans to label 50,000 images." → **Ground Truth**

---

### 3. Clarify vs Amazon Personalize

Another distractor in Q451 is **Amazon Personalize**.

Personalize is used to build personalized recommendations.

Examples:

* recommend movies
* recommend products
* recommend content

But if the company **already has a recommendation model** and simply wants to understand its predictions, migrating to Personalize doesn't solve the explainability requirement.

So:

> Create personalized recommendations → **Amazon Personalize**

> Explain model recommendations → **SageMaker Clarify**

---

### 4. Clarify vs Rekognition

Amazon Rekognition analyzes **images and video**.

For example:

* object detection
* facial analysis
* image labels
* content moderation

Analyzing profile pictures would not automatically make a recommendation model explainable.

So:

> Images/video → **Rekognition**

> Explainability/bias → **Clarify**

---

### 5. Secure access to a deployed ML model

Q452 says:

* the ML model is already deployed
* external customers need to access it
* customers use their own applications
* access must be secure

The correct architecture concept is:

> **Expose the model through a secure API endpoint**



Conceptually:

`Customer application`

↓ secure request

`API endpoint`

↓

`ML model`

↓

`prediction`

This is a standard production architecture.

---

### 6. Why use an API endpoint?

An API gives you a controlled interface between customers and the model.

It allows you to implement things such as:

* authentication
* authorization
* request validation
* rate limiting
* logging
* monitoring
* encryption
* versioning

The customer doesn't need direct access to the underlying model or infrastructure.

Think:

> **External application needs predictions → expose inference through an API**

---

### 7. Don't share model credentials

One distractor in Q452 says to directly share model credentials with customers.

That's a bad security design.

Credentials should not normally be:

> hardcoded or directly distributed to external users.

Instead, customers should authenticate to a controlled API.

A useful security principle:

> **Give access to the service, not the underlying credentials.**

---

### 8. Don't embed the model in every customer's app

Another option suggests embedding the model directly in each customer's application.

That creates problems:

* model copies become difficult to update
* potentially exposes intellectual property
* difficult to control access
* harder to monitor
* harder to patch
* potentially huge model size

A centralized API endpoint lets the company control one deployed model.

---

### 9. API endpoint vs SageMaker endpoint

The question itself says **secure API endpoint**, rather than naming a particular AWS architecture.

At the conceptual level:

**SageMaker endpoint**
→ hosts an ML model for inference.

An application-facing API can then provide controlled access to that model.

Think of the layers as:

`External customer`

→ `Secure API`

→ `Inference endpoint/model`

The exam may sometimes ask about these separately.

---

## Page 10 high-yield cheat sheet

| Exam wording                    | Think                        |
| ------------------------------- | ---------------------------- |
| Model transparency              | **SageMaker Clarify**        |
| Explain recommendations         | **SageMaker Clarify**        |
| Detect/analyze bias             | **SageMaker Clarify**        |
| Label training data             | **Ground Truth**             |
| Personalized recommendations    | **Amazon Personalize**       |
| Image/video analysis            | **Rekognition**              |
| External apps need model access | **Secure API endpoint**      |
| Don't expose credentials        | **Authenticate through API** |
| Centralized inference           | **API → model endpoint**     |

The **two distinctions to memorize from this final page** are:

**Clarify vs Ground Truth:**
Clarify = **explain predictions / analyze bias**.
Ground Truth = **label data**.

**Model endpoint vs customer access:**
The model can be hosted behind an inference endpoint, but external customers should access it through a **secure API interface**, not by receiving credentials or embedding the model directly.

That completes the question set through **#452**.
