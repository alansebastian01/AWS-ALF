In ML, **inference** means using an already-trained model to make predictions on new data.

For AWS/ML exam purposes, the most important inference modes are **real-time inference, batch inference, asynchronous inference, and serverless inference**.

### 1. Real-time inference

Use this when you need a prediction **immediately** after sending input to the model.

**Flow:**

`User request → Model endpoint → Prediction immediately`

Example: A banking application receives a transaction and needs to determine instantly whether it's fraudulent.

> Transaction → Model → **Fraud / Not Fraud**

**Best for:** low-latency, interactive applications.

Examples:

* Fraud detection
* Product recommendations
* Chat applications
* Real-time image classification

**Exam clue:** **“immediate,” “real-time,” “low latency,” “milliseconds”**

---

### 2. Batch inference

Use this when you have a **large amount of data** and don't need predictions immediately.

Instead of sending one request at a time:

`Large dataset → Model → Predictions for entire dataset`

Example: A company has **2 million customers** and wants to predict which customers might churn next month.

It could process all customers overnight:

`2 million customer records → ML model → 2 million churn predictions`

There's no need for an always-running endpoint.

**Best for:** large datasets where immediate results aren't required.

Examples:

* Monthly customer churn predictions
* Overnight sales predictions
* Processing millions of stored images
* Large-scale offline predictions

**Exam clue:** **“large dataset,” “offline,” “scheduled,” “predictions don't need to be immediate”**

---

### 3. Asynchronous inference

This is useful when an individual inference request takes **a relatively long time to process**.

**Flow:**

`Request → Queue/process → Model works → Result available later`

The application doesn't need to keep waiting for an immediate response.

Example: Suppose an ML model processes a **large video file** and takes 2 minutes to produce a result.

Real-time inference isn't ideal because the request takes too long.

Instead:

`Large video → Submit request → Model processes → Result returned later`

**Best for:**

* Large payloads
* Long-running predictions
* Requests that can tolerate waiting

**Exam clue:** **“large payload,” “long processing time,” “results can be returned later”**

---

### 4. Serverless inference

Serverless inference is useful when traffic is **intermittent or unpredictable** and you don't want to manage dedicated inference infrastructure.

Conceptually:

`Request arrives → AWS provides compute → Model predicts → Resources scale as needed`

For example, an application receives:

`8 AM → 2 requests`
`9 AM → 100 requests`
`10 AM → almost no requests`

Serverless infrastructure can automatically scale according to demand.

**Best for:**

* Intermittent traffic
* Unpredictable workloads
* Applications that can tolerate serverless startup/latency characteristics
* Reducing infrastructure management

**Exam clue:** **“unpredictable traffic,” “intermittent requests,” “automatically scale,” “no infrastructure management”**

---

## Compare all four

| Inference mode     | When to use                           | Easy keyword                      |
| ------------------ | ------------------------------------- | --------------------------------- |
| ⚡ **Real-time**    | Need prediction immediately           | **Low latency**                   |
| 📦 **Batch**       | Process lots of data together         | **Large dataset/offline**         |
| ⏳ **Asynchronous** | Individual requests take a long time  | **Large payload/long processing** |
| ☁️ **Serverless**  | Traffic is intermittent/unpredictable | **Auto scaling**                  |

### Don't confuse training and inference

This distinction is very important:

**Training:**

`Training data → ML algorithm → Trained model`

The model is **learning**.

**Inference:**

`New data → Trained model → Prediction`

The model is **using what it learned**.

For example:

`10,000 labeled cat/dog images → TRAINING → Model`

Then:

`New image → INFERENCE → "Dog: 97%"`

### AWS exam memory trick

Remember **R-B-A-S**:

**R** = Real-time → **Right now** ⚡
**B** = Batch → **Big datasets** 📦
**A** = Asynchronous → **Await the result** ⏳
**S** = Serverless → **Scale automatically** ☁️

For AWS AI/ML exam questions, identifying keywords such as **latency, traffic pattern, payload size, and volume of predictions** will usually tell you which inference option to choose.
