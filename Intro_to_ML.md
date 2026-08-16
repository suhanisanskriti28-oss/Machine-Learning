# Machine Learning — Session 1 Notes
## Introduction to Classical Machine Learning

---

# 1. What is Machine Learning?

### Simple definition

**Machine Learning (ML)** is a way of making computers learn patterns from data so that they can make predictions or decisions on new data **without us manually writing every rule**.

### Traditional Programming vs Machine Learning

### Traditional Programming

We give the computer:

```text
Rules + Data
    ↓
Program
    ↓
Answer
```

Example:

> If marks >= 40 → Pass  
> Else → Fail

We explicitly write the rule.

### Machine Learning

We give the computer:

```text
Data + Correct Answers
          ↓
   Learning Algorithm
          ↓
        Model
          ↓
    Prediction on new data
```

The computer learns a useful pattern from examples.

### Important

ML does **not** mean that we give the computer no instructions at all.

We still decide:
- what problem we want to solve
- what data to provide
- what type of ML problem it is
- which algorithm/model to use
- how to evaluate the result

What we avoid is manually writing every rule connecting input to output.

---

# 2. The Basic ML Vocabulary

These words will appear everywhere in Machine Learning.

## Data

The information we give to the ML system.

Example:

| Hours Studied | Attendance | Exam Score |
|---:|---:|---:|
| 2 | 60 | 45 |
| 4 | 75 | 60 |
| 6 | 85 | 75 |
| 8 | 90 | 88 |

---

## Features

**Features are the input pieces of information used by the model to make a prediction.**

In the example:

- Hours Studied
- Attendance

are features.

Usually represented by:

\[
X
\]

Think:

> **Features = What information do I give the model?**

---

## Target / Label

The **target** is the answer we want the model to predict.

In the example:

- Exam Score

is the target.

Usually represented by:

\[
y
\]

Think:

> **Target = What answer am I asking the model to predict?**

---

## X and y

A very common ML notation is:

\[
X = \text{input features}
\]

\[
y = \text{actual target}
\]

Later, we will see:

\[
\hat{y}
\]

which means:

> **the model's predicted value**

So:

```text
X → Model → ŷ
             ↓
       compare with y
```

Where:

- `X` = input
- `y` = actual answer
- `ŷ` = predicted answer

---

# 3. Example: Identifying X and y

Suppose:

| Age | Salary | Purchases |
|---:|---:|---:|
| 20 | 30000 | 5 |
| 25 | 50000 | 10 |
| 30 | 70000 | 15 |

If we want to predict **Purchases**:

```text
X = Age + Salary
y = Purchases
```

So:

- Age → feature
- Salary → feature
- Purchases → target

---

# 4. Types of Machine Learning

The three major learning types you should know initially are:

```text
Machine Learning
│
├── Supervised Learning
├── Unsupervised Learning
└── Reinforcement Learning
```

---

# 5. Supervised Learning

In **supervised learning**, the training data contains the correct answer/target.

Think:

> **Data + Answers are provided.**

Example:

| Hours | Attendance | Score |
|---:|---:|---:|
| 2 | 60 | 45 |
| 4 | 75 | 60 |
| 6 | 85 | 75 |

The model sees:

```text
Inputs → Correct Output
```

and learns the relationship.

Supervised Learning mainly includes:

```text
Supervised Learning
│
├── Regression
└── Classification
```

---

# 6. Regression

Regression is used when we want to predict a **numerical value**.

Examples:

- House price → ₹80 lakh
- Salary → ₹8.5 lakh
- Temperature → 31.5°C
- Exam score → 82
- Sales → 12,500 units

### Simple rule

> **If the output is a continuous/numerical quantity → think Regression.**

Example:

```text
Hours Studied + Attendance
             ↓
       Regression Model
             ↓
        Exam Score
```

---

# 7. Classification

Classification is used when we want to predict a **category/class**.

Examples:

```text
Spam / Not Spam
Pass / Fail
Fraud / Not Fraud
Cat / Dog
Disease / No Disease
```

The output belongs to a class rather than being a continuous numerical quantity.

### Simple rule

> **Regression → number**
>
> **Classification → category/class**

---

# 8. Unsupervised Learning

In **unsupervised learning**, we do **not** provide a target/label.

The model receives data and tries to discover useful patterns or structures on its own.

Example:

| Age | Salary | Purchases |
|---:|---:|---:|
| 20 | 30000 | 5 |
| 22 | 32000 | 6 |
| 45 | 90000 | 20 |
| 48 | 95000 | 22 |

There is no column saying:

```text
Customer Group = ?
```

We ask the algorithm:

> "Find groups of similar customers."

This is **unsupervised learning**.

A major unsupervised learning task in your syllabus is:

### Clustering

And later you will learn:

- K-Means
- K-Means++
- Hierarchical Clustering

---

# 9. Reinforcement Learning — Basic Idea

In reinforcement learning, an **agent learns by interacting with an environment**.

It receives:

- rewards for desirable actions
- penalties/rewards for undesirable actions

Example:

```text
Agent → takes action
        ↓
Environment
        ↓
Reward / Penalty
        ↓
Agent learns
```

Examples include:
- game-playing agents
- robotics
- decision-making systems

For your Classical ML syllabus, this is mainly foundational background.

---

# 10. Algorithm vs Model vs Training

This distinction is extremely important.

## Algorithm

An **algorithm is the method/procedure used to learn from data.**

Examples:

- Linear Regression algorithm
- KNN algorithm
- Decision Tree algorithm
- K-Means algorithm

Think:

> **Algorithm = HOW the learning happens**

---

## Training

**Training is the process of applying the learning algorithm to the training data so that the model learns useful parameters/patterns.**

Think:

> **Training = the learning process**

---

## Model

The **model is the learned result** that can be used to make predictions on new data.

Think:

> **Model = WHAT was learned**

The relationship is:

```text
Training Data
     +
Learning Algorithm
     ↓
   Training
     ↓
 Learned Parameters
     ↓
    MODEL
     ↓
 Predictions on new data
```

### Easy analogy

Imagine a recipe:

- Recipe → Algorithm
- Cooking process → Training
- Finished dish → Model

The analogy isn't exact, but it helps remember the roles.

---

# 11. Parameters

**Parameters are values learned by the model during training.**

For a simple Linear Regression model:

\[
h_\theta(x)=\theta_0+\theta_1x
\]

The parameters are:

\[
\theta_0,\theta_1
\]

The algorithm learns suitable values for these parameters from the training data.

### Remember

> **Parameters are learned by the model.**

---

# 12. Hyperparameters

**Hyperparameters are settings chosen by us rather than learned directly from the training data.**

Examples you will encounter:

- Learning rate in Gradient Descent
- `k` in KNN
- Maximum tree depth in Decision Trees
- Number of trees in Random Forest

### Important distinction

```text
Parameters
→ learned during training

Hyperparameters
→ chosen/set by us
```

We will study this much more deeply later.

---

# 13. What is a Model Trying to Do?

Suppose we want to predict exam scores.

We give the model:

```text
Hours Studied
Attendance
```

The model produces:

```text
Predicted Score
```

For example:

```text
Actual score = 80
Predicted score = 75
```

There is an error.

The model needs some way of measuring how wrong it is.

That is where **Loss / Cost Function** comes in.

---

# 14. Loss Function / Cost Function

A **loss function measures how far the model's predictions are from the actual answers.**

Suppose:

```text
Actual = 80
Predicted = 78
```

The prediction is close.

So the loss should be relatively small.

But:

```text
Actual = 80
Predicted = 20
```

The prediction is far away.

So the loss should be large.

Conceptually:

```text
Good prediction
      ↓
Small error
      ↓
Small loss

Bad prediction
      ↓
Large error
      ↓
Large loss
```

The model's goal during training is generally to **minimize the loss**.

---

# 15. Loss vs Cost — Basic Understanding

You will hear both terms.

In many introductory ML contexts:

- **Loss** → error for an individual example
- **Cost** → aggregate/overall error over many examples

The exact terminology can vary between courses/resources, so focus first on the central idea:

> **They quantify how bad the predictions are.**

For example, Mean Squared Error (MSE):

\[
MSE=\frac{1}{n}\sum_{i=1}^{n}(y_i-\hat{y}_i)^2
\]

You do NOT need to memorize this formula yet.

Just understand:

\[
\text{Actual} - \text{Predicted}
\]

gives an error, and a cost function combines errors into a measure we can minimize.

---

# 16. Training Data and Test Data

A major ML mistake is evaluating a model only on the data it already saw during training.

Why?

Because the model may simply memorize the training examples.

Instead, we separate data.

```text
Complete Dataset
       │
       ├──────────────┐
       ↓              ↓
 Training Data     Test Data
       │              │
       ↓              ↓
    Learn          Evaluate
```

### Training Data

Used to teach/fit the model.

### Test Data

Data the model has not seen during training and is used to evaluate how well it works on unseen examples.

---

# 17. Why Can't We Just Test on Training Data?

Imagine an exam.

You memorize the exact answers to last year's paper.

Then your teacher gives you the same paper.

You score:

> 100%

Does that prove you understand the concepts?

No.

You may have memorized the questions.

ML has the same problem.

A model can perform extremely well on training data because it has already seen that data.

What we really care about is:

> **Can the model perform well on new, unseen data?**

This ability is called **generalisation**.

---

# 18. Generalisation

**Generalisation means the model can use what it learned from the training data to make good predictions on new, unseen data.**

The goal is NOT:

> Memorize training data.

The goal is:

> Learn useful underlying patterns that work on new data.

Think:

```text
Training Data
     ↓
Learn useful patterns
     ↓
Model
     ↓
New / Unseen Data
     ↓
Good Predictions
```

---

# 19. Overfitting

**Overfitting happens when a model learns the training data too specifically and therefore performs poorly on new/unseen data.**

Typical pattern:

```text
Training performance → Very good
Test performance     → Poor
```

### Easy analogy

You memorize the exact answers from practice questions.

On the same questions:

> 100%

On new questions:

> 40%

You memorized instead of understanding.

That is similar to overfitting.

---

# 20. Underfitting

Underfitting is the opposite problem.

The model is too simple or has not learned enough.

Typical pattern:

```text
Training performance → Poor
Test performance     → Poor
```

The model fails to capture the important patterns in the data.

Later, you will study the relationship between:

- Underfitting
- Good fit/generalisation
- Overfitting

under **Bias-Variance**.

---

# 21. The Big Picture

The entire basic supervised learning process can be visualised as:

```text
                 DATASET
                    │
                    ↓
             Features (X)
                    │
                    ↓
            Learning Algorithm
                    │
                    ↓
                 Training
                    │
                    ↓
                  MODEL
                    │
             New input X
                    │
                    ↓
              Prediction ŷ
                    │
                    ↓
       Compare with actual y
                    │
                    ↓
                  LOSS
                    │
                    ↓
        Improve model parameters
                    │
                    ↓
              Better Model
                    │
                    ↓
           Generalisation
                    │
                    ↓
       Good predictions on
          unseen data
```

---

# 22. The Two Major Supervised Learning Problems

```text
                    SUPERVISED
                        │
             ┌──────────┴──────────┐
             ↓                     ↓
         REGRESSION          CLASSIFICATION
             │                     │
          Number                 Class
             │                     │
      House Price             Spam / Not Spam
      Salary                  Pass / Fail
      Temperature             Cat / Dog
      Exam Score              Fraud / Not Fraud
```

---

# 23. Supervised vs Unsupervised

This is one of the most important distinctions.

| | Supervised | Unsupervised |
|---|---|---|
| Target/label available? | Yes | No |
| Learns from known answers? | Yes | No |
| Main goal | Predict | Discover patterns |
| Example | Predict salary | Find customer groups |
| Term 1 algorithms | Linear/Logistic Regression, KNN, Trees | K-Means, Hierarchical Clustering, PCA |

### Shortcut

Ask:

> **"Do I have the correct answer/target column?"**

If **YES** → Supervised

If **NO** → Unsupervised

---

# 24. Example: Classify the Problem

### Example 1

```text
Features:
Area
Bedrooms
Location

Target:
House Price
```

Output is a number.

→ **Regression**

---

### Example 2

```text
Features:
Age
Salary
Transactions

Target:
Fraud / Not Fraud
```

Output is a category.

→ **Classification**

---

### Example 3

```text
Features:
Age
Salary
Purchases

Target:
None
```

Goal:

> Find groups of similar customers.

→ **Unsupervised Learning → Clustering**

---

# 25. Dataset Representation — Important for NumPy

Suppose:

| Area | Bedrooms | Age |
|---:|---:|---:|
| 1000 | 2 | 10 |
| 1500 | 3 | 5 |
| 2000 | 4 | 2 |
| 1200 | 2 | 8 |

If we want to predict **House Price**, then:

```text
X = Area + Bedrooms + Age
y = House Price
```

In NumPy:

```python
X = np.array([
    [1000, 2, 10],
    [1500, 3, 5],
    [2000, 4, 2],
    [1200, 2, 8]
])

y = np.array([
    price_A,
    price_B,
    price_C,
    price_D
])
```

Here:

- Rows = examples/houses
- Columns = features

So:

\[
X.shape=(4,3)
\]

means:

> **4 examples, each with 3 features.**

### Golden Rule

> **Rows = examples**
>
> **Columns = features**

And:

> **X = input/features**
>
> **y = target/answer**

---

# 26. A Simple Mental Model for ML

Whenever you see an ML problem, ask these questions:

### Step 1 — What is my data?

What information do I have?

### Step 2 — What is X?

What information am I giving to the model?

### Step 3 — What is y?

What am I trying to predict?

### Step 4 — Is y numerical or categorical?

- Numerical → Regression
- Categorical → Classification

### Step 5 — Do I even have y?

- Yes → Supervised
- No → Unsupervised

### Step 6 — How will I know whether my model is good?

Use an appropriate evaluation/loss metric.

### Step 7 — Can it work on unseen data?

That's where generalisation and train/test evaluation matter.

---

# 27. Session 1 — Quick Revision Sheet

## Machine Learning

Learning useful patterns from data to make predictions/decisions without manually programming every rule.

## Feature

Input information used by the model.

\[
X = \text{features}
\]

## Target / Label

The answer we want the model to predict.

\[
y = \text{actual target}
\]

## Prediction

The model's predicted answer.

\[
\hat{y} = \text{prediction}
\]

## Algorithm

Method/procedure used for learning.

## Training

Process of applying the algorithm to training data.

## Model

Learned result used to make predictions.

## Parameter

Value learned during training.

## Hyperparameter

Setting chosen by us.

## Loss

Measures prediction error.

## Training Data

Used to learn.

## Test Data

Unseen data used to evaluate.

## Generalisation

Ability to perform well on unseen data.

## Overfitting

Very good training performance but poor unseen/test performance.

## Underfitting

Poor performance because the model has not learned enough.

---

# 28. The Most Important Things to Remember

If you remember only these for now, you're good:

```text
X → Inputs / Features
y → Actual Target
ŷ → Prediction
```

```text
Supervised
→ Target exists
```

```text
Unsupervised
→ Target does not exist
```

```text
Regression
→ Predict a number
```

```text
Classification
→ Predict a class/category
```

```text
Algorithm
→ How learning happens
```

```text
Training
→ Applying the learning process
```

```text
Model
→ What was learned
```

```text
Loss
→ How wrong are the predictions?
```

```text
Overfitting
→ Memorises training data too much
→ Poor on unseen data
```

```text
Goal
→ Generalise well
```

---

# 29. What Comes Next

Our Term 1 roadmap is:

```text
✅ Introduction to Classical ML
        ↓
🟡 Python for ML
        ↓
   NumPy
        ↓
   Pandas
        ↓
   Linear Regression
        ↓
   Gradient Descent
        ↓
   Data Preparation
        ↓
   Evaluation Metrics
        ↓
   ...
```

We have started **NumPy** now.

The NumPy concepts we'll cover are:

```text
Arrays
  ↓
Shape
  ↓
Rows & Columns
  ↓
Indexing & Slicing
  ↓
Vectorisation
  ↓
Broadcasting
  ↓
Dot Product
  ↓
Matrix Operations
  ↓
Axis / Reshape
```

These aren't random NumPy topics — they directly prepare you for the mathematics and implementation of ML models.

---

# 🧪 Mini Self-Test

Before moving on, try answering these without looking above:

### Q1
You have 1,000 students and 5 features per student.

What is the shape of `X`?

### Q2
You want to predict salary from age, education and experience.

What are X and y?

### Q3
You have customer data but no target column and want to find customer groups.

Supervised or unsupervised?

### Q4
You predict house price.

Regression or classification?

### Q5
A model gets 99% accuracy on training data but 60% on unseen test data.

What is likely happening?

### Q6
What is the difference between `y` and `ŷ`?

### Q7
What is the difference between a parameter and a hyperparameter?


