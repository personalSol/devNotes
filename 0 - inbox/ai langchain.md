---
status: newBorn
related-links:
created: 1970-01-01T05:30
updated: 2025-12-28T18:42
---
---

# LangChain Chains

LangChain introduces the concept of **Chains**, which are used to connect multiple steps (such as prompts and LLM calls) together. In a chain, the **output of one step becomes the input of the next step**.

Chains help when a single LLM call is not enough and we want structured, multi-step reasoning or generation.

---

## LLMs in LangChain

LangChain provides **wrapper classes for different LLM providers** such as OpenAI, Anthropic, etc.

* These models are imported from `langchain.llms` (or updated modules in newer versions)
* API keys are passed during initialization
* Each model takes an input (prompt) and returns an output (response)

On their own, LLMs work as:

```
Input → Model → Output
```

Chains extend this idea to multiple steps.

---

## Why Chains Are Needed

Chains are used when:

* The output of one LLM should be reused as input for another
* We want a **multi-step pipeline** instead of a single prompt
* We want structured control over intermediate results

Example flow:

```
Input → Step 1 → Output 1 → Step 2 → Output 2
```

---

## Types of Chains

#### SimpleSequentialChain

* Takes **one input**
* Produces **one final output**
* Internally runs multiple steps
* Only the **last output** is returned

Use this when:

* You only care about the final result
* Intermediate outputs are not needed

---

#### SequentialChain

* Can take **multiple inputs**
* Can return **multiple outputs**
* Preserves intermediate results

Use this when:

* You need access to outputs from earlier steps
* Later steps depend on multiple values

---

## Example: Restaurant Generator

We want to build:

1. A **restaurant name generator**
2. A **dish/cuisine generator** based on the restaurant name

#### Using SimpleSequentialChain

* Step 1: Generate restaurant name
* Step 2: Generate dishes using that name
* ❌ Only dishes are returned
* ❌ Restaurant name is lost

#### Using SequentialChain

* Step 1: Generate restaurant name
* Step 2: Generate dishes using that name
* ✅ Restaurant name is returned
* ✅ Dishes/cuisines are returned

This makes **SequentialChain** the better choice when intermediate outputs matter.

---

## Quick Mental Model

* **SimpleSequentialChain** → pipeline, final output only
* **SequentialChain** → pipeline + intermediate outputs


