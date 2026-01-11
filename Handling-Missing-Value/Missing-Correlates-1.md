# What does **“Missing correlates with target”** ACTUALLY mean?

## Step 1: What is the **target**?

The **target** is what you are trying to predict.

Example targets:

* Exam_Score
* Loan_Default (Yes / No)
* Fraud (Yes / No)

---

## Step 2: What does **missing** mean?

A value is **missing** when it is:

* Not filled
* Not recorded
* Hidden

Shown as `NaN`.

---

## Step 3: Meaning of **correlates** (very simple)

**Correlates** means:

> When one thing changes, another thing also changes **in a pattern**

So:

> “Missing correlates with target” means
> **Missing happens more for certain target values**

---

# ONE SIMPLE EXAMPLE (Read slowly)

## Dataset: Exam Results

We want to predict **Pass or Fail**

```
Student | Study_Hours | Result
------------------------------
A       | 6           | Pass
B       | NaN         | Fail
C       | 5           | Pass
D       | NaN         | Fail
E       | 7           | Pass
```

---

## Step 4: Look ONLY at missing rows

```
Student | Study_Hours | Result
------------------------------
B       | NaN         | Fail
D       | NaN         | Fail
```

👉 **Every student with missing Study_Hours FAILED**

---

## Step 5: Look at non-missing rows

```
Student | Study_Hours | Result
------------------------------
A       | 6           | Pass
C       | 5           | Pass
E       | 7           | Pass
```

👉 **Every student with filled Study_Hours PASSED**

---

## Step 6: The KEY QUESTION

Ask yourself:

> “Is missing happening randomly?”

❌ NO

Because:

* Missing → Fail
* Not missing → Pass

---

## 🚨 This is what “Missing correlates with target” means

```
Missing Study_Hours  → Fail
Not Missing          → Pass
```

Missing itself is **predicting the result**.

---

# What happens if you DROP missing rows?

### You drop:

```
B and D
```

### Remaining data:

```
Student | Study_Hours | Result
------------------------------
A       | 6           | Pass
C       | 5           | Pass
E       | 7           | Pass
```

---

## 🔥 Catastrophic result

* Model sees **only Pass**
* Learns: “Everyone passes”
* Completely wrong model

---

# Why did this happen in real life?

Because:

* Students who failed **didn’t report study hours**
* Hiding data = poor outcome

👉 Missing is **meaningful**

---

# SIMPLE RULE (MEMORIZE THIS)

```
If missing rows mostly have the same target value
→ Missing correlates with target
```

---

# Another very common example (Loan Default)

```
Customer | Income | Default
---------------------------
A        | 70k    | No
B        | NaN    | Yes
C        | 65k    | No
D        | NaN    | Yes
```

Missing Income → Default = Yes

Same pattern.

---

# What SHOULD you do instead of dropping?

### Correct approach:

1. Create a missing flag:

```
Income_Missing = 1 if Income is NaN else 0
```

2. Fill missing with constant or median
3. Let model learn missing behavior

---

# Interview-style one-liner (exact)

> “Missing correlates with target when the probability of missing values depends on the outcome, so missingness itself becomes predictive.”

---

# 10-second self-check (DO THIS ALWAYS)

Look at missing rows and ask:

> “Do they mostly belong to one target class?”

If YES → **DO NOT DROP**

---

# One-picture mental model (in words)

Imagine:

* Red dots = missing
* Blue dots = not missing

If red dots cluster in one outcome → missing correlates with target.

---

## Final summary (very simple)

> **Missing correlates with target means:
> People with certain outcomes are more likely to have missing values.**

Dropping them deletes the most important signal.
