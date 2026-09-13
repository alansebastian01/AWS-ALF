For **Amazon Bedrock Guardrails**, think of guardrails as **safety rules around an LLM**. They can inspect both **user inputs** and **model responses**.

For AWS exam purposes, these are the major guardrail filter/check types to remember:

| Guardrail capability              | What it does                                             | Example                                                  |
| --------------------------------- | -------------------------------------------------------- | -------------------------------------------------------- |
| **Content filters**               | Filters harmful content categories                       | Hate, insults, sexual content, violence, misconduct      |
| **Denied topics**                 | Blocks entire topics/subjects                            | “Don't provide investment advice”                        |
| **Word filters**                  | Blocks specific words/phrases                            | Offensive terms or prohibited company terms              |
| **Sensitive information filters** | Detects/masks PII                                        | SSN, email, phone number                                 |
| **Contextual grounding checks**   | Checks whether answers are supported by provided context | Prevent unsupported RAG answers                          |
| **Automated reasoning checks**    | Helps validate responses against defined policies/rules  | Check whether an answer logically follows company policy |

### Content Filters specifically

If an exam question specifically says **Amazon Bedrock content filters**, remember the harmful-content categories:

**H – I – S – V – M**

* **H**ate
* **I**nsults
* **S**exual
* **V**iolence
* **M**isconduct

For example:

> “Generate instructions for committing a harmful illegal act.”

→ **Misconduct content filter**

Or:

> Content threatening physical harm.

→ **Violence content filter**

### Denied Topics

This is different from harmful-content filtering.

Suppose a financial company's chatbot should never discuss:

> “Which stock should I buy?”

The company can define **investment advice** as a denied topic.

Think:

> **Entire SUBJECT prohibited → Denied Topics**

### Word Filters

Suppose a company wants to prevent specific offensive/prohibited words.

> `specific prohibited word → BLOCK`

Think:

> **Specific WORD → Word Filter**

This can also include configured words/phrases.

### Sensitive Information / PII

Suppose a user enters:

> “My Social Security number is 123-45-6789.”

A sensitive-information filter can detect PII and configure actions such as masking it.

Think:

> **SSN / phone / email / personal data → Sensitive information filter**

### Contextual Grounding

This connects directly to the RAG questions you've been studying.

Source:

> “Customers can return products within 30 days.”

LLM says:

> “Customers can return products within 90 days.”

❌ The answer isn't supported by the source.

A **contextual grounding check** helps identify responses that aren't sufficiently grounded in the provided source/context.

Think:

> **SOURCE doesn't support ANSWER → Grounding**

---

### Best exam memory trick

Memorize:

> 🛡️ **Bad CONTENT → Content Filter**
> 🚫 **Bad TOPIC → Denied Topics**
> 🔤 **Bad WORD → Word Filter**
> 🔒 **Private DATA → Sensitive Information**
> 📚 **Unsupported ANSWER → Contextual Grounding**

And for the **content-filter categories specifically**:

> **HISVM = Hate, Insults, Sexual, Violence, Misconduct**

That distinction between **content filter**, **denied topic**, and **word filter** appears frequently in Bedrock Guardrails questions.
