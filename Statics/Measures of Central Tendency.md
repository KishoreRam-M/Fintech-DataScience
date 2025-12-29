## What are Measures of Central Tendency?

**Measures of Central Tendency** are simple ways to answer one core question:

> **“What is a typical or central value in this data?”**

When you have **thousands or millions of numbers**, you need **one value** that represents the whole set in a meaningful way.
That’s what **mean, median, and mode** do—each in a different situation.

---

## Why we need a “central value” in data

In Data Science, raw data is too large to reason about directly.

Businesses don’t ask:

* “Show me every transaction”

They ask:

* “What is a normal transaction?”
* “What does a typical customer look like?”
* “Has behavior changed?”

A **central value**:

* Compresses large data into a **single understandable number**
* Helps compare time periods, users, or segments
* Supports fast decisions

---

## Why Central Tendency is Important in Data Science

### How it helps summarize large datasets

* Turns 1 lakh transactions into **one representative number**
* Makes dashboards readable
* Helps spot unusual behavior quickly

### Why businesses care about averages

* Pricing decisions
* Credit limits
* Fraud thresholds
* Customer segmentation

👉 In FinTech, **one wrong “average” can block users or lose money**.

---

## Mean (Average)

### What it represents (intuition only)

**Mean = total value spread evenly across everyone**

Think:

> “If all transaction amounts were shared equally, how much would each be?”

---

### When Data Scientists use mean

Use mean when:

* Data is **balanced**
* No extreme values
* You want an **overall level**

Common use:

* Average daily transaction value
* Average revenue per user
* Average account balance (only if stable)

---

### Real-world Data Science / FinTech example

**UPI transactions (₹):**

```
100, 200, 300, 400
```

Mean ≈ ₹250

This represents the **overall transaction level** well.

---

### When mean can be misleading

If data has **extreme values**.

Example:

```
100, 150, 200, 250, 1,00,000
```

Mean becomes very high, but:

* Most users are small spenders
* One big transaction distorts reality

👉 This can cause:

* Wrong fraud limits
* Wrong customer profiling

---

## Median

### What it represents (intuition only)

**Median = the middle value when data is ordered**

Think:

> “Half the values are below this, half are above”

---

### When Data Scientists prefer median

Use median when:

* Data has **outliers**
* Spending or income varies widely
* You want a **safer ‘typical’ value**

Median is very popular in FinTech.

---

### Real-world Data Science / FinTech example

Monthly customer spending (₹):

```
2,000, 3,000, 4,000, 5,000, 80,000
```

* Mean → looks very high
* Median → ₹4,000

Median shows:

> “Most customers spend around ₹4,000”

This is **business-relevant truth**.

---

### Why median is safer with extreme values

* One rich user
* One large transaction
* One fraud event

👉 Median **ignores extremes** and reflects majority behavior.

---

## Mode

### What it represents (intuition only)

**Mode = the most frequently occurring value**

Think:

> “What value happens the most?”

---

### When Data Scientists use mode

Use mode when:

* Data is **categorical**
* You want the **most common choice**

Very useful for:

* Payment method
* Transaction type
* Failure reason

---

### Real-world Data Science / FinTech example

Payment methods:

```
UPI, UPI, UPI, Card, Wallet
```

Mode = **UPI**

This tells:

> “Most users prefer UPI”

Great for product and business decisions.

---

### Limitations of mode

* Not useful for continuous numbers (like amounts)
* Can be misleading if frequencies are close
* Sometimes no clear mode exists

---

## Comparison of Mean vs Median vs Mode

| Measure | Best used when    | What it tells      |
| ------- | ----------------- | ------------------ |
| Mean    | Data is balanced  | Overall level      |
| Median  | Data has outliers | Typical user       |
| Mode    | Categories matter | Most common choice |

**Key thinking:**

* Mean → “overall”
* Median → “typical”
* Mode → “most common”

---

## How Data Scientists Choose the Right Measure

### Based on data type

* Amounts → Mean or Median
* Categories → Mode

### Based on business goal

* Revenue tracking → Mean
* User behavior → Median
* Popular features → Mode

### Based on outliers

* Many extreme values → Avoid mean
* Stable values → Mean is okay

---

## Real-Life FinTech Use Case (Mandatory)

![Image](https://cdn.statcdn.com/Statistic/1380000/1384088-blank-355.png)

![Image](https://assets-cms.globalxetfs.com/post-body-images/241125-FinTech2025_01.png)

![Image](https://www.inetco.com/wp-content/uploads/inetco-insight-analytics-mobile-online-trends-web.jpg)

![Image](https://prod-assets.cosmic.aws.dev/a/32fwOZAxwfCq8ckquY6Ebnwmba9/Scre.webp)

### Customer Spending Analysis (₹)

Transactions:

```
500, 700, 1,000, 1,200, 1,500, 50,000
```

* **Mean** → Looks very high (distorted by ₹50,000)
* **Median** → Around ₹1,000 (typical customer)
* **Mode** → If ₹1,000 appears most → common spend

**Insight:**

* Median → customer profiling
* Mean → revenue planning
* Mode → pricing or offers

All three together give **full understanding**.

---

## Common Beginner Mistakes

### ❌ Using mean everywhere

* Leads to false assumptions
* Especially dangerous in finance data

### ❌ Ignoring outliers

* Fraud and high-value users exist
* Must be handled carefully

### ❌ Misinterpreting “average”

* “Average” ≠ “most people”
* Often means **mean**, not median

---

## Final Mental Model (Remember This)

> **Mean shows overall level**
> **Median shows typical behavior**
> **Mode shows what’s most common**

A good Data Scientist:

* Never uses one blindly
* Always matches the measure to the business question

Once this intuition is clear, advanced statistics becomes **logical, not scary**.
