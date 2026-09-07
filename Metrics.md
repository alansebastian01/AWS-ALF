# LLM & ML Evaluation Metrics — Quick Reference

A practical reference for common machine learning and generative AI evaluation metrics.

---

## 📌 Quick Reference

| Metric | Best Used For | Main Idea |
|---|---|---|
| **F1 Score** | Classification | Balance precision and recall |
| **BERTScore** | Semantic similarity / LLM output | Does the generated text have the same meaning? |
| **ROUGE** | Summarization | How much of the reference content was captured? |
| **BLEU** | Machine translation | How closely does generated text match a reference? |

---

# 1. F1 Score

## What is it used for?

F1 Score is commonly used for **classification problems**, especially when both **precision and recall** are important.

Common examples include:

- Spam detection
- Fraud detection
- Sentiment classification
- Medical classification
- Imbalanced classification problems

## Example

Suppose there are **10 spam emails**.

The model predicts **8 emails as spam**:

- 6 are actually spam → **True Positives (TP)**
- 2 are not spam → **False Positives (FP)**
- 4 spam emails were missed → **False Negatives (FN)**

### Precision

> Of everything the model predicted as spam, how many were actually spam?

```text
Precision = TP / (TP + FP)

Precision = 6 / 8 = 75%
```

### Recall

> Of all the spam emails that actually existed, how many did the model find?

```text
Recall = TP / (TP + FN)

Recall = 6 / 10 = 60%
```

### F1 Score

F1 combines **precision and recall** using their harmonic mean.

```text
F1 = 2 × (Precision × Recall) / (Precision + Recall)

F1 ≈ 66.7%
```

### 🧠 Remember

> **F1 → Classification + balance between Precision and Recall**

---

# 2. BERTScore

## What is it used for?

BERTScore evaluates whether two pieces of text have **similar semantic meaning**, even if they use different words.

Useful for:

- LLM responses
- Paraphrasing
- Creative language
- Conversational AI
- Text generation
- Semantic similarity

## Example

### Reference

> The student was extremely tired after studying all night.

### Generated Response

> Bro was exhausted after pulling an all-nighter 💀

There isn't much exact word overlap.

However, the **meaning is extremely similar**.

BERTScore uses contextual embeddings to recognize relationships such as:

```text
"extremely tired" ≈ "exhausted"

"studying all night" ≈ "pulling an all-nighter"
```

Therefore, the response can receive a strong BERTScore despite using very different wording.

### 🧠 Remember

> **BERTScore → Semantic meaning**

### AWS Exam Clues

Think **BERTScore** when you see:

- Semantic similarity
- Paraphrasing
- Different wording with the same meaning
- Slang
- Creative spelling
- Conversational language
- LLM-generated responses

---

# 3. ROUGE

**ROUGE = Recall-Oriented Understudy for Gisting Evaluation**

## What is it used for?

ROUGE is primarily associated with evaluating **text summarization**.

It measures overlap between generated text and a reference text.

## Example

### Reference Summary

> Amazon announced a new AI service for developers.

### Generated Summary

> Amazon announced a new AI service.

There is substantial overlap:

```text
Amazon announced a new AI service
```

Therefore, ROUGE would likely give this summary a relatively strong score.

Now consider another generated summary:

> AWS unveiled another artificial intelligence offering.

The meaning may be similar, but there is much less direct word overlap.

Traditional ROUGE may therefore give this version a lower score despite the semantic similarity.

### 🧠 Remember

> **ROUGE → Summarization**

A useful mental model:

> **"How much of the reference did my summary capture?"**

---

# 4. BLEU

**BLEU = Bilingual Evaluation Understudy**

## What is it used for?

BLEU is traditionally associated with **machine translation**.

It evaluates generated text against one or more reference translations using **n-gram overlap**.

## Example

### Original Spanish

> El gato está sobre la mesa.

### Human Reference Translation

> The cat is on the table.

### AI Translation

> The cat is on the table.

This should receive a strong BLEU score because the generated translation closely matches the reference.

Now consider:

> On top of the table sits the cat.

This is still a reasonable translation.

However, BLEU may give it a lower score because the sequence of words and n-grams differs from the reference.

### 🧠 Remember

> **BLEU → Machine Translation**

---

# 🔥 BERTScore vs ROUGE vs BLEU

Suppose our reference sentence is:

> **The student is very tired.**

## Output A

> The student is very tired.

| Metric | Expected Result |
|---|---|
| BERTScore | ✅ High |
| ROUGE | ✅ High |
| BLEU | ✅ High |

Both the **meaning and wording match**.

---

## Output B

> The student is exhausted.

| Metric | Expected Result |
|---|---|
| BERTScore | ✅ Likely High |
| ROUGE | ⚠️ Lower |
| BLEU | ⚠️ Lower |

The **meaning is similar**, but the exact wording differs.

---

## Output C

> Bro is absolutely cooked 💀

| Metric | Expected Result |
|---|---|
| BERTScore | ✅ May recognize semantic similarity |
| ROUGE | ❌ Likely Low |
| BLEU | ❌ Likely Low |

There is very little direct word overlap, but the intended meaning may still be similar depending on context.

This demonstrates the major difference:

> **BERTScore cares more about semantic meaning.**

> **ROUGE and BLEU care more about textual/n-gram overlap.**

---

# 📝 AWS Exam Cheat Sheet

## 🎯 F1 Score

**Think: Classification**

Keywords:

- Precision
- Recall
- Classification
- False positives
- False negatives
- Imbalanced classes

---

## 🧠 BERTScore

**Think: Meaning**

Keywords:

- Semantic similarity
- Paraphrasing
- LLM responses
- Creative wording
- Slang
- Same meaning, different words

---

## 📝 ROUGE

**Think: Summarization**

Keywords:

- Summarization
- Reference summary
- Recall-oriented
- Content coverage
- N-gram overlap

---

## 🌎 BLEU

**Think: Translation**

Keywords:

- Machine translation
- Reference translation
- N-gram overlap
- Generated translation

---

# 🚀 One-Line Memory Trick

```text
🎯 F1        = Classification
🧠 BERTScore = Meaning
📝 ROUGE     = Summarization
🌎 BLEU      = Translation
```
