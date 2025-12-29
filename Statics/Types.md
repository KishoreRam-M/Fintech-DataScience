## What are the Types of Statistics?

**Types of Statistics** are simply **two different ways of using data** to answer questions.

From a Data Science point of view:

* One type helps you **understand what has already happened**
* The other helps you **make decisions about what is likely to happen**

That’s it. No theory. No math fear.

---

## Why statistics is divided into types

Because **data questions come in two very different forms**:

1. “What is going on in my data right now?”
2. “Based on this data, what should I expect or decide?”

Trying to answer both with the same approach leads to **wrong business decisions**.
So statistics is divided into:

* **Descriptive Statistics**
* **Inferential Statistics**

---

## Descriptive Statistics

### What it means (in simple words)

**Descriptive Statistics = summarizing data you already have**

It does **not predict**.
It does **not guess the future**.

It only answers:

> “What does this data look like?”

---

### What kind of questions it answers

* What is the **average transaction amount**?
* How many transactions happened today?
* What is the **most common spending range**?
* Are most values small or large?
* Are there unusual transactions?

All questions about **current or past data**.

---

### How Data Scientists use it

Data Scientists use descriptive statistics to:

* Understand the dataset before modeling
* Spot errors or strange values
* Explain data clearly to business teams
* Decide what needs deeper analysis

It is always the **first step** in Data Science.

---

### Simple real-world example (FinTech)

**UPI Transactions (1 day):**

* 50,000 transactions
* Most payments are between ₹50 and ₹500
* Average transaction ≈ ₹320
* A few payments above ₹50,000

What descriptive statistics tells:

* Normal user behavior
* Typical spending amount
* Presence of extreme values

👉 No prediction yet. Just understanding reality.

---

## Inferential Statistics

### What it means (in simple words)

**Inferential Statistics = using data to make decisions or conclusions**

It helps answer:

> “Is this change real or just random?”
> “Can we trust this pattern?”
> “Will this likely continue?”

It goes **beyond the data you already saw**.

---

### What kind of questions it answers

* Is fraud actually increasing or was yesterday just a spike?
* Is this new payment feature really improving success rate?
* Can we approve loans for this customer group safely?
* Should we change transaction limits?

These are **decision-making questions**.

---

### How Data Scientists use it

Data Scientists use inferential statistics to:

* Validate patterns
* Compare two situations (before vs after)
* Support business decisions with confidence
* Reduce risk when acting on data

This is where **business impact** happens.

---

### Simple real-world example (FinTech)

A company notices:

* UPI failures increased today by 8%

Inferential statistics helps answer:

* Is this a real system issue?
* Or just normal daily fluctuation?

Based on this:

* Engineers decide whether to fix urgently
* Business decides whether to notify users

👉 Without inference, teams may panic or ignore real problems.

---

## Key Differences Between Descriptive and Inferential Statistics

| Aspect        | Descriptive Statistics | Inferential Statistics      |
| ------------- | ---------------------- | --------------------------- |
| Focus         | What has happened      | What it means for decisions |
| Time          | Past / current data    | Future or unseen situations |
| Purpose       | Understand data        | Decide and act              |
| Output        | Summaries & patterns   | Conclusions & confidence    |
| Business role | Reporting              | Decision-making             |

**Thinking difference:**

* Descriptive = “What do I see?”
* Inferential = “What should I do?”

---

## How These Two Types Fit into the Data Science Workflow

### 1. Data Understanding

* Descriptive statistics comes first
* Helps clean, explore, and understand data

### 2. Decision Making

* Inferential statistics checks if patterns are meaningful
* Prevents reacting to noise

### 3. Model Evaluation

* Descriptive → understand model behavior
* Inferential → trust model improvements

They are **not competitors**.
They work **together**.

---

## Real-Life FinTech Use Case (Mandatory)

![Image](https://www.mdpi.com/fintech/fintech-02-00009/article_deploy/html/images/fintech-02-00009-g001.png)

![Image](https://media.licdn.com/dms/image/v2/D5612AQE_Hd8rOlCbQA/article-cover_image-shrink_720_1280/B56ZeDn.IJHUAI-/0/1750259984696?e=2147483647\&t=vhL3VaIPO5Cq-6ajNgvqVnUP_jKXYrrat5WfH8eIYQU\&v=beta)

![Image](https://roopya.money/wp-content/themes/roopya-money/images/credit-risk-analytics.webp)

![Image](https://offload.media.kychub.com/wp-content/uploads/2024/08/14163135/Transaction-Monitoring-in-Banks.png)

### Fraud Detection in Digital Payments

**Step 1: Descriptive Statistics**

* Average daily fraud cases = 120
* Most fraud amounts < ₹10,000
* Fraud mostly happens late night

This answers:

> “What does fraud look like?”

---

**Step 2: Inferential Statistics**

* Today fraud count = 180
* Is this spike real or random?
* Should we tighten security rules?

This answers:

> “Should we take action?”

👉 Companies act **only after inference**, not just description.

---

## Common Beginner Confusions

### ❌ “Descriptive statistics is enough”

Reality:

* It only tells **what happened**
* It cannot justify decisions

---

### ❌ “Inferential statistics predicts perfectly”

Reality:

* It reduces uncertainty
* It does not guarantee outcomes

---

### ❌ Mixing both without clarity

Result:

* False fraud alerts
* Wrong credit decisions
* Loss of customer trust

---

### ❌ Skipping descriptive and jumping to decisions

Result:

* Decisions based on dirty or misunderstood data

---

## Final Mental Model (Remember This)

> **Descriptive statistics helps you understand data.**
> **Inferential statistics helps you decide using data.**

In Data Science and FinTech:

* First understand
* Then decide
* Then act safely

Once this clarity is strong, learning deeper topics becomes **easy and logical**, not scary.
