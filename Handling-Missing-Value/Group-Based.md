# First: what is **Group-Based (Conditional) Imputation** in ONE LINE

> **Fill missing values using people/items that are similar in some known way (group).**

Instead of asking:

> “What is the average for everyone?”

You ask:

> **“What is the average for people like this?”**

---

## STEP 1: ONE SIMPLE DATASET (keep this fixed)

### Dataset: Employee Salary Prediction

Target: `Salary`
We have missing salaries.

```
Employee | Job_Role   | Experience | Salary
-------------------------------------------
A        | Developer  | 3          | 50k
B        | Developer  | 5          | 70k
C        | Tester     | 4          | 40k
D        | Tester     | 6          | NaN
E        | Developer  | 4          | NaN
```

---

# STEP 2: Why **normal (global) imputation is WRONG here**

### If you use **overall mean salary**

Known salaries: 50k, 70k, 40k
Mean ≈ **53k**

You fill:

* D (Tester) → 53k ❌
* E (Developer) → 53k ❌

But think like a human 👇
A **Tester** and a **Developer** do NOT earn the same.

This is the problem group-based imputation solves.

---

# STEP 3: What does **“Strong relationship between feature and group”** mean?

It means:

> **Salary strongly depends on Job_Role**

Let’s check:

| Job_Role  | Typical Salary |
| --------- | -------------- |
| Developer | High           |
| Tester    | Lower          |

👉 Salary ≠ random
👉 Salary depends on **group**

✅ **Strong relationship exists**

---

# STEP 4: Apply GROUP-BASED IMPUTATION (NOW IT MAKES SENSE)

We impute **within each group**.

### Developers only

```
A → 50k
B → 70k
Mean = 60k
```

### Testers only

```
C → 40k
Mean = 40k
```

---

### Now fill missing values

```
D (Tester)    → 40k
E (Developer) → 60k
```

✔ Realistic
✔ Business-correct
✔ Model learns properly

---

# NOW let’s decode EACH CONFUSING POINT YOU ASKED 👇

---

## ✅ “Demographics, geography, categories” — WHAT THIS MEANS

These are **natural group keys**.

Examples:

| Feature        | Depends on     |
| -------------- | -------------- |
| Salary         | Job role, city |
| House price    | Location       |
| Medical cost   | Age group      |
| Internet speed | Area           |
| Spending       | Income group   |

If the value **naturally changes across groups** → use group-based imputation.

---

## ✅ “Business logic depends on context” — VERY IMPORTANT

Ask this question:

> “Would a business person accept one global average?”

Salary example:

* CEO & Intern average salary ❌ nonsense

House price example:

* Village + City average ❌ nonsense

✔ Business reality demands grouping.

---

## ✅ “Enough data per group” — WHY THIS MATTERS

Now imagine this:

```
Employee | Job_Role | Salary
----------------------------
A        | Manager  | NaN
```

Only **ONE Manager**, and salary is missing.

❌ You cannot compute a group average
❌ Group has no information

### Rule (simple):

```
If a group has < 5–10 records → unreliable
```

---

# WHEN **NOT** TO USE GROUP-BASED IMPUTATION (CLEARLY)

---

## ❌ 1. Small or sparse groups

Example:

```
Job_Role = Astronaut (1 person)
```

No history → no imputation possible.

---

## ❌ 2. Unstable group distributions

Example:

* Job roles keep changing
* New categories appear often

Group statistics become unreliable.

---

## ❌ 3. Leakage risk (MOST IMPORTANT FOR INTERVIEWS)

### What is leakage? (very simple)

> Using information that would NOT be available at prediction time.

---

### BAD example (leakage)

```
Student | Final_Grade | Study_Hours
```

You group by **Final_Grade** to impute Study_Hours.

❌ Final_Grade is the TARGET
❌ You are cheating

---

### Rule (burn this in memory)

```
Never group by the target
Never group by future information
```

---

# INTERVIEW-READY ANSWERS (SHORT & CLEAN)

### Q: When do you use group-based imputation?

> “When the missing feature strongly depends on a known category like job role, location, or demographic, and there’s enough data per group.”

### Q: When do you avoid it?

> “When groups are small, unstable, or when grouping would cause data leakage.”

---

# ONE-PAGE MENTAL MODEL (VERY IMPORTANT)

```
Ask 3 questions:

1️⃣ Does the value depend on a category?
2️⃣ Do I have enough data per category?
3️⃣ Is this category available at prediction time?

YES to all → GROUP-BASED IMPUTATION
NO to any → DO NOT USE
```

---

## Final ultra-simple summary

> **Group-based imputation = fill missing values using people who are similar in a meaningful business way.**
