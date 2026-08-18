
### High-yield concepts to remember

| When you see...                                     | Think...                              |
| --------------------------------------------------- | ------------------------------------- |
| Humans judging preferred response **style/quality** | **Human evaluation + custom prompts** |
| Copying AI-generated work                           | **Plagiarism**                        |
| Efficient AWS hardware for training                 | **EC2 Trn / AWS Trainium**            |
| Control harmful/inappropriate Bedrock output        | **Bedrock Guardrails**                |
| Generate **synthetic data**                         | **GAN**                               |
| No-code ML                                          | **SageMaker Canvas**                  |
| Learn using **rewards/feedback**                    | **Reinforcement learning**            |
| Classification performance                          | **Confusion matrix / F1**             |
| Filter inappropriate images/content                 | **Moderation**                        |

The first few questions directly test model evaluation, plagiarism, and training infrastructure. 

### Bedrock + GenAI concepts

**Bedrock invocation logging** → records model inputs/outputs.

**Embeddings** → numerical/vector representations of concepts.
**Tokens** → basic units the model processes (words/subwords/etc.). Don't confuse these two.

**Domain adaptation fine-tuning** → use when the model needs to understand specialized terminology/domain knowledge.

**Temperature ↓** → more deterministic/consistent answers.
**Temperature ↑** → more randomness/variation.

**Agents for Amazon Bedrock** → automate repetitive tasks and **orchestrate workflows**. 

**Hallucination** → output sounds believable but is factually incorrect. 

### RAG vs fine-tuning

This distinction is especially worth memorizing:

**RAG** = retrieve external/company knowledge and put it into the model's context.

Think:

> "I want the chatbot to answer using our company policies/knowledge base."

→ **RAG**, especially when you want a cost-effective way to provide contextual company information rather than retraining the model. 

**Fine-tuning/domain adaptation** = change the model's behavior or improve its ability in a specialized domain.

### Prompting

**Role prompting** → tell the model who it should act as / who the audience is.

Example from the page: changing explanations according to the user's age can be done by putting the target age/role into the prompt rather than fine-tuning. 

**Few-shot prompting** → provide a few examples.

For intent classification, examples should look like:

**user message → correct intent**

Also remember: **more prompt tokens = more cost**.

### Tokens and cost

This one is very testable:

**Bedrock inference cost → number of tokens consumed.** 

So:

**longer prompt + longer output → more tokens → higher inference cost**

### Model evaluation metrics

Memorize the purpose rather than just the acronym:

* **BLEU** → machine **translation**
* **ROUGE** → typically text **summarization**
* **F1** → classification; balances precision + recall
* **Confusion matrix** → classification performance
* **RMSE/MSE** → regression/numeric prediction

The page specifically associates **BLEU with evaluating translations**. 

### SageMaker

**Batch Transform** → large offline datasets where results are **not needed immediately**. 

**SageMaker Canvas** → no-code ML.

**DeepAR** → **time-series forecasting**. 

**Network Isolation** → SageMaker training/inference without internet access. 

**SageMaker Model Cards** → document/audit model details such as intended use, training, and inference information. 

### Responsible AI

Know these particularly well:

**Fairness** → avoid systematically disadvantaging groups.

**Bias mitigation** → check whether the training data has **class imbalance** and adjust accordingly. 

**Fairness metrics + mitigating bias in training data** are responsible-AI practices. 

A diverse dataset across demographics/geographies is associated with **fairness** on this page. 

### Security

**Jailbreak** → attempt to bypass an LLM's safety restrictions. 

**Prompt-template extraction** → attacker tries to expose the hidden/configured prompt. 

**Bedrock shared responsibility** → AWS protects the underlying infrastructure; the customer is responsible for things such as **securing their data**. 

### AWS services worth memorizing

**Textract** → documents/PDF/images → extract text
**Transcribe** → speech → text
**Comprehend** → NLP/text analysis
**Personalize** → recommendations
**Lex** → conversational/chatbot interfaces
**Amazon Q Developer** → developer/code/AWS assistance
**Amazon Q in QuickSight** → analytics, visualizations, business-data questions
**S3** → common dataset storage for Bedrock/SageMaker

### The 10 associations I'd memorize first

**Guardrails → safety**
**Canvas → no-code ML**
**Textract → document text extraction**
**DeepAR → time series**
**GAN → synthetic data**
**Embeddings → numerical representations**
**Tokens → model input/output units + inference cost**
**BLEU → translation**
**RAG → external/company knowledge**
**Agents → workflow/task orchestration**

Those relationships cover a large portion of what Questions 51–100 are testing.
