
1. **Basic ML concepts**
   Know the differences between:

   * **Supervised learning** → labeled data; classification/regression
   * **Unsupervised learning** → unlabeled data; clustering/pattern discovery
   * **Reinforcement learning** → rewards/actions
   * **Training vs. inference**
   * **Transfer learning** → adapt a pretrained model instead of starting over
   * Classification vs. regression vs. anomaly/object detection

   For example, your questions test **accuracy** for classification and **transfer learning** for adapting pretrained models. 

2. **Generative AI, LLMs & Foundation Models — VERY important**

   Be comfortable with:

   * **Foundation model (FM)** = large pretrained model adaptable to many tasks
   * **LLM** = FM focused primarily on language
   * Generative AI vs. traditional predictive ML
   * Summarization
   * Text generation
   * Image generation
   * Sentiment analysis
   * Multimodal models
   * Embeddings
   * Fine-tuning
   * Context windows

   One question, for example, directly tests that the **context window determines how much information can fit into a prompt**. 

3. **Prompt engineering**

   This comes up repeatedly in your PDF. Know:

   * **Zero-shot** → instructions without examples
   * **Few-shot** → give examples of input → desired output
   * Clear instructions/context
   * Prompt templates
   * Iteratively refining prompts
   * Temperature
   * Top-K
   * Token limits

   **Exam shortcut:** if the problem says *“make the model respond in a certain tone, language, style, or format”*, think **prompt engineering first**.

   Your questions explicitly use prompt refinement for company tone and examples with positive/negative labels for sentiment classification. 

4. **RAG, embeddings & vector databases**

   Know this flow:

   **Documents → embeddings → vector database → similarity search → relevant context → LLM**

   **RAG (Retrieval-Augmented Generation)** means retrieving relevant external/private information and supplying it to the model at inference time.

   Know the distinction:

   **RAG** → give the model relevant external knowledge
   **Fine-tuning** → change/customize the model's behavior using training data
   **Prompt engineering** → change the instructions/context in the request

   Your PDF specifically tests **Bedrock Knowledge Bases** as a cost-effective way to give an LLM context from PDFs. 

   Also know that vector search involves **nearest-neighbor search**. 

5. **Amazon Bedrock — probably your highest-priority AWS service**

   Think:

   **Bedrock = AWS managed platform for building generative AI applications with foundation models.**

   Know:

   * Foundation models
   * Knowledge Bases / RAG
   * Model customization/fine-tuning
   * On-Demand vs Provisioned Throughput
   * Model access
   * Security/IAM
   * Guarding against prompt attacks
   * Private connectivity
   * Embeddings

   Example: your material associates **On-Demand** with flexibility and no long-term commitment. 

6. **SageMaker and what its components do**

   Memorize these associations:

   | Service/feature            | Think                                 |
   | -------------------------- | ------------------------------------- |
   | **SageMaker**              | Build/train/deploy ML                 |
   | **Clarify**                | Bias + explainability                 |
   | **Feature Store**          | Store/share ML features               |
   | **Ground Truth**           | Data labeling                         |
   | **JumpStart**              | Pretrained models / quick deployment  |
   | **Serverless Inference**   | Predictions without managing servers  |
   | **Asynchronous Inference** | Large/long-running inference requests |

   Your material specifically associates **SageMaker Clarify** with identifying potential bias. 

7. **Responsible AI: bias, fairness, explainability**

   This is another recurring theme.

   Know:

   * Bias
   * Fairness
   * Transparency
   * Explainability
   * Human oversight
   * Detecting imbalanced datasets
   * Model evaluation
   * Benchmark datasets

   **Explainability** = understanding *why* a model produced an output.

   Decision trees are relatively interpretable, while neural networks are generally much harder to explain. Your first few questions explicitly test explainability techniques such as **partial dependence plots** and interpretable algorithms. 

   For responsible AI, your questions also emphasize **detecting disparities in data and evaluating model behavior for transparency**. 

8. **Security, governance & AWS services**

   Know the purpose of these:

   * **IAM** → permissions / least privilege
   * **CloudTrail** → records API activity; who did what
   * **PrivateLink** → private AWS service connectivity without public internet
   * **Artifact** → AWS compliance reports/documents
   * **S3** → object/data storage
   * Encryption → protect data
   * **Least privilege** → give only necessary permissions

   Your questions explicitly pair secure Bedrock usage with **clear prompts + IAM least privilege**.  They also test **CloudTrail** for identifying attempts to access Bedrock. 

### The high-yield mental cheat sheet

If you can instantly recognize these, you'll cover a large portion of this question set:

| When you see...                  | Think...                   |
| -------------------------------- | -------------------------- |
| Unlabeled data / grouping        | **Unsupervised learning**  |
| Labeled data                     | **Supervised learning**    |
| Model making predictions         | **Inference**              |
| Reuse pretrained model           | **Transfer learning**      |
| How many classifications correct | **Accuracy**               |
| Company tone/style/format        | **Prompt engineering**     |
| Examples inside prompt           | **Few-shot prompting**     |
| Creativity/randomness            | **Temperature**            |
| Amount model can read            | **Context window**         |
| Private docs + LLM               | **RAG / Knowledge Base**   |
| Semantic search                  | **Embeddings + vector DB** |
| Customize model using examples   | **Fine-tuning**            |
| Generative AI on AWS             | **Amazon Bedrock**         |
| Build/train/deploy ML            | **SageMaker**              |
| Bias/explainability              | **SageMaker Clarify**      |
| Share ML features                | **Feature Store**          |
| Human data labeling              | **Ground Truth**           |
| API/audit history                | **CloudTrail**             |
| Permissions                      | **IAM**                    |
| Private AWS connectivity         | **PrivateLink**            |
| Compliance documents             | **AWS Artifact**           |
| No infrastructure for inference  | **Serverless Inference**   |
| Large/long inference request     | **Async Inference**        |

If you master **Bedrock + prompt engineering/RAG + basic ML + SageMaker + responsible AI/security**, you'll cover the concepts that recur most heavily in the practice questions you uploaded.
